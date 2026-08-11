# 🔎 Wireshark Network Traffic Analysis

> Hands-on Packet Analysis & Network Investigation

## 📌 Overview

This project documents a hands-on network traffic analysis exercise using **Wireshark**.

The objective was to analyze a provided `.pcap` packet capture, inspect network packets and protocol layers, and use Wireshark display filters to identify and investigate relevant network traffic.

The analysis focused on **IP communication, TCP, DNS, HTTP traffic, and packet payloads**.

---

## 🎯 Objectives

- Analyze a `.pcap` network capture.
- Identify source and destination IP addresses.
- Inspect different network protocol layers.
- Analyze TCP communication and packet details.
- Investigate DNS queries and responses.
- Analyze HTTP traffic.
- Use Wireshark display filters to isolate relevant packets.
- Search packet payloads for specific text.

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Wireshark** | Network packet capture and analysis |
| **PCAP** | Network traffic capture used for investigation |
| **TCP/IP** | Network communication analysis |
| **DNS** | Domain name resolution analysis |
| **HTTP** | Web traffic analysis |
| **TCP** | Transport-layer traffic analysis |
| **ICMP** | Network connectivity traffic analysis |

---

## 💻 Lab Environment

- **Operating System:** Windows
- **Network Analysis Tool:** Wireshark
- **Capture File:** `sample.pcap`
- **Lab Platform:** Google Cloud Skills Boost

## 🔬 Investigation Methodology

The packet analysis was performed through a structured investigation workflow:

1. **Packet Capture Inspection**  
   Opened the provided `sample.pcap` file and reviewed the captured network traffic.

2. **IP Traffic Analysis**  
   Applied IP-based filters to identify communication involving specific hosts.

3. **Protocol Layer Inspection**  
   Examined packet layers including Ethernet II, IPv4, and TCP.

4. **MAC Address Analysis**  
   Used MAC-based filtering to investigate Ethernet-level communication.

5. **DNS Investigation**  
   Filtered DNS traffic and analyzed queries and responses to identify domain resolution activity.

6. **TCP & HTTP Analysis**  
   Investigated TCP port 80 traffic and inspected packet-level information.

7. **Payload Investigation**  
   Used content-based filtering to identify packets containing specific text within TCP payloads.

   
