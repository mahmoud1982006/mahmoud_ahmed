# 🔎 TCPDump Network Traffic Capture & Analysis

![tcpdump](https://img.shields.io/badge/Tool-tcpdump-blue?style=for-the-badge&logo=linux)
![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-red?style=for-the-badge)
![Network Analysis](https://img.shields.io/badge/Focus-Network%20Traffic%20Capture-green?style=for-the-badge)

> Hands-on Packet Capture & Network Interface Analysis

## 📌 Overview

This project documents a hands-on network traffic capture exercise using **tcpdump** on a Linux virtual machine.

The objective was to identify available network interfaces, capture live network traffic, save the captured data to a `.pcap` file, and filter/inspect the saved packet data.

The analysis focused on **network interfaces, live traffic inspection, packet capture to file, and header/payload filtering**.

---

## 🎯 Objectives

- Identify available network interfaces
- Inspect live network traffic with tcpdump
- Capture network traffic into a `.pcap` file
- Generate HTTP traffic using `curl`
- Filter and inspect captured packet header data
- Analyze packet data in hexadecimal and ASCII format

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **tcpdump** | Command-line network packet capture and analysis |
| **ifconfig** | Network interface identification |
| **curl** | Generating HTTP traffic for capture |
| **PCAP** | Captured network traffic file format |
| **TCP/IP** | Network communication analysis |
| **HTTP** | Web traffic analysis |
| **Linux Bash** | Command-line lab environment |

---

## 💻 Lab Environment

- **OS:** Linux (Bash shell)
- **User:** `analyst`
- **Tools:** `tcpdump`, `ifconfig`, `curl`
- **Capture File:** `capture.pcap`
- **Platform:** Google Cloud Skills Boost

---

# 🔬 Investigation

## 1. 🖧 Identify Network Interfaces

To identify the available network interfaces, I used:

```
sudo ifconfig
```

The `eth0` interface was identified as the active Ethernet interface, with IP address `172.17.0.2`.

![Network Interfaces - ifconfig](images/01-network-interfaces-ifconfig.png)

I then confirmed the available capture interfaces directly through tcpdump:

```
sudo tcpdump -D
```

This listed `eth0`, `any`, `lo`, and several other pseudo-interfaces available for packet capture.

![tcpdump Interface List](images/02-tcpdump-interface-list.png)

**🧠 Security Relevance**
Identifying the correct network interface is the first step in any packet capture investigation — capturing on the wrong interface means missing the traffic of interest entirely.

---

## 2. 📡 Inspect Live Network Traffic

Live traffic on the `eth0` interface was inspected using:

```
sudo tcpdump -i eth0 -v -c5
```

- `-i eth0`: capture from the eth0 interface
- `-v`: display detailed (verbose) packet data
- `-c5`: capture 5 packets and then stop

The output showed TCP and UDP packets, including source/destination hosts, ports, TTL, flags, and sequence/acknowledgment numbers.

![tcpdump Live Traffic Inspection](images/03-tcpdump-live-traffic.png)

**🧠 Security Relevance**
Live traffic inspection lets an analyst quickly get a sense of what a host is communicating with in real time, before deciding whether a full capture is needed.

---

## 3. 💾 Capture Network Traffic to a File

A background capture was started, filtered to HTTP (port 80) traffic only, and written to `capture.pcap`:

```
sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &
```

- `-i eth0`: capture from the eth0 interface
- `-nn`: disable IP/port name resolution (best practice — prevents alerting a threat actor and avoids unreliable lookups)
- `-c9`: capture 9 packets and then stop
- `port 80`: filter to HTTP traffic only
- `-w capture.pcap`: write the capture to a file
- `&`: run the capture in the background

![Starting Background Packet Capture](images/04-tcpdump-background-capture-start.png)

HTTP traffic was then generated for the capture using:

```
curl opensource.google.com
```

The request returned a `301 Moved Permanently` response redirecting to `https://opensource.google/`, and the background capture completed after 9 packets were captured.

![curl HTTP Traffic Capture](images/05-curl-http-traffic-capture.png)

**🧠 Security Relevance**
Filtering a capture to a specific port at collection time (rather than capturing everything) keeps `.pcap` files focused and manageable, which matters when working with high-volume production traffic.

---

## 4. 🔍 Filter the Captured Packet Data

The saved capture file was read back and its packet headers inspected using:

```
sudo tcpdump -nn -r capture.pcap -v
```

- `-nn`: disable port and protocol name lookup
- `-r`: read capture data from the named file
- `-v`: display detailed packet data

The output showed the full TCP three-way handshake (SYN, SYN-ACK, ACK) with `172.17.0.2`, followed by the HTTP `GET / HTTP/1.1` request to `opensource.google.com` and the server's `301 Moved Permanently` response.

![Filtering Captured Packet Data](images/06-tcpdump-filter-capture-file.png)

For deeper inspection, the same file can also be read in hex/ASCII form:

```
sudo tcpdump -nn -r capture.pcap -X
```

- `-X`: display hexadecimal and ASCII packet data, useful for detecting patterns or anomalies during malware or forensic analysis

**🧠 Security Relevance**
Reading back a saved capture with `-nn` and `-X` allows an analyst to reconstruct exactly what was sent and received — including plaintext HTTP headers and content — which is often the first step in confirming or ruling out a security incident.

---

## 🔎 Important tcpdump Commands

| Command | Purpose |
|---|---|
| `sudo ifconfig` | List network interfaces and their addresses |
| `sudo tcpdump -D` | List interfaces available for packet capture |
| `sudo tcpdump -i eth0 -v -c5` | Capture 5 verbose packets on eth0 |
| `sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap` | Capture 9 HTTP packets to a file, without name resolution |
| `sudo tcpdump -nn -r capture.pcap -v` | Read and display verbose packet headers from a file |
| `sudo tcpdump -nn -r capture.pcap -X` | Display hex/ASCII payload data from a file |

---

## 📊 Key Findings

- **Interface:** `eth0` (IP `172.17.0.2`) identified as the active capture interface
- **Live Traffic:** TCP and UDP packets observed during live inspection
- **HTTP Capture:** A `curl` request to `opensource.google.com` generated 9 captured packets over TCP port 80
- **HTTP Response:** Server returned `301 Moved Permanently`, redirecting to `https://opensource.google/`
- **TCP Handshake:** Full SYN → SYN-ACK → ACK sequence observed in the capture
- **Packet Headers:** TTL, flags, sequence/acknowledgment numbers, and checksums were inspected for each packet

---

## 🧠 Skills Demonstrated

- Linux network interface identification
- Live network traffic inspection with tcpdump
- Filtered packet capture to a `.pcap` file (BPF filter: `port 80`)
- HTTP traffic generation and analysis
- TCP packet header interpretation (flags, TTL, sequence/ack numbers)
- Reading and filtering saved `.pcap` capture files
- Hex/ASCII payload inspection

---

## 🎓 Learning Outcomes

This practical exercise strengthened my understanding of command-line packet capture and its application to security investigations.

It provided hands-on experience with:

- Network interface identification
- Live traffic inspection with tcpdump
- Capturing traffic to a `.pcap` file with BPF filters
- Generating and analyzing HTTP traffic
- Reading and filtering saved packet captures
- Hex/ASCII payload inspection

These skills provide a foundation for SOC Analysis, Network Security, and Incident Response.

---

## 📚 Lab Information

- **Lab:** Exemplar: Capture your first packet
- **Platform:** Google Cloud Skills Boost
- **Tool:** tcpdump
- **Capture:** `capture.pcap`

---

## 👨‍💻 Author

**Mahmoud Ahmed Fathy**
Computer Science Student | Aspiring SOC Analyst
Focus: Cybersecurity • SOC Analysis • Network Security • Incident Response
