# TCPDump Network Analysis

## Overview

This project demonstrates the analysis of network-layer communication using **tcpdump**. The objective was to investigate network traffic, identify the protocols involved, and determine the root cause of a connectivity issue affecting a web service.

---

## Scenario

Users reported that they were unable to access a website and received a **"Destination Port Unreachable"** error.

Network traffic was captured using **tcpdump** to investigate the issue.

---

## Objectives

- Analyze captured network traffic.
- Identify the network protocols involved.
- Interpret ICMP error messages.
- Determine the suspected root cause.
- Document the findings in a cybersecurity incident report.

---

## Investigation Summary

During the analysis, I observed that:

- The client sent **UDP** packets to the DNS server.
- The DNS requests targeted **port 53**.
- The DNS server responded with **ICMP "Destination Port Unreachable"** messages.
- As a result, the domain name could not be resolved, preventing access to the website.



##Cybersecurity Incident Report: 
##Network Traffic Analysis
### 1-

The UDP protocol reveals that: it cannot reach the port 53

This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message: "udp port 53 unreachable" 

The port noted in the error message is used for: Port 53 is a port for DNS service. 

The most likely issue is: attack on the DNS server



### 3-
Time incident occurred:13:24:32.192571. =1:24 p.m., 32.192571 seconds. 

Explain how the IT team became aware of the incidenSeveral customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load.  

Explain the actions taken by the IT department to investigate the incident:network analyzer tool, tcpdump 

Note key findings of the IT department's investigation (i.e., details related to the port affected, DNS server, etc.): domain 35084 +A

Note a likely cause of the incident: attack on the DNS server





---

## Lessons Learned

Through this activity, I improved my ability to analyze packet captures, interpret network protocols, identify communication failures, and document technical findings in a structured incident report.
