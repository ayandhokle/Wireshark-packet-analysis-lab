# Wireshark Packet Capture & Analysis

## Author: **Ayan Dhokle** 

## Project Overview
This project demonstrates hands-on network traffic analysis using **Wireshark** in a controlled **Host-Only virtual lab**. The goal is to capture, analyze, and understand common network protocols and identify normal versus suspicious traffic patterns.

---

## Objectives
- Capture live network traffic using Wireshark
- Analyze **ICMP**, **TCP**, and **HTTP** traffic
- Observe the **TCP 3-way handshake**
- Understand client-server communication
- Identify reconnaissance and abnormal traffic patterns

---

## Lab Environment

 Component:<br>
  Attacker / Analyzer: Kali Linux <br>
  Target / Client: Ubuntu Linux <br>
  Network Mode: Host-Only Adapter<br>
  Tools: Wireshark, Nmap, Apache2 <br>

---

## Network Topology
```
Kali Linux (Wireshark)
   |
   |  Host-Only Network
   |
Ubuntu Linux (Web Server)
```

---

## Steps Performed

### Network Configuration
- Configured both Kali and Ubuntu VMs with **Host-Only Adapter**
- Verified IP addressing using `ip a`

### Traffic Capture
- Started Wireshark on Kali Linux
- Selected the active Host-Only network interface

### ICMP Analysis
- Generated traffic using `ping`
- Captured ICMP Echo Request and Reply packets

### TCP 3-Way Handshake
- Installed and started Apache2 on Ubuntu
- Connected from Kali using `curl`
- Observed SYN, SYN-ACK, and ACK packets

### HTTP Analysis
- Analyzed HTTP GET requests and responses on port 80
- Verified client-server communication

### Reconnaissance Detection
- Performed Nmap scan against Ubuntu
- Identified multiple SYN packets indicating port scanning activity

---

## Wireshark Display Filters Used
```text
icmp

tcp

http

tcp.flags.syn == 1 && tcp.flags.ack == 0
```
---

## Key Concepts Learned
- Packet capture and protocol analysis
- TCP vs UDP behavior
- ICMP troubleshooting
- HTTP communication basics
- Identifying suspicious network activity
  
---

## Future Improvements
- Add HTTPS traffic analysis
- Integrate IDS tools (Snort/Suricata)
- Analyze DNS traffic using local DNS server

---

