# Computer Networks Project  
## TCP/IP Packet Encapsulation and Capture

## Overview
This project demonstrates a practical implementation of TCP/IP communication by manually constructing, sending, capturing, and analyzing network packets.  
The goal is to gain an in-depth understanding of the encapsulation process across the TCP/IP layers and to observe real network traffic using Wireshark.

The project focuses on the HTTP protocol running over TCP and simulates real traffic on the local loopback interface. Packets are generated programmatically, sent through the network stack, captured in real time, and analyzed to verify correctness and protocol compliance.

---

## Project Goals
- Demonstrate the TCP/IP encapsulation process in practice  
- Manually construct a CSV file containing application-layer messages.
- Description and analysis of the packet encapsulation process.
- Capture and analyze traffic using Wireshark.  
- Validate analysis and explanation of the network traffic captured using Wireshark, including supporting screenshots. 

---

## Technologies and Tools
- **Operating System:** macOS  
- **Programming Language:** Python  
- **Development Environment:** Jupyter Notebook  
- **Network Analysis Tool:** Wireshark  
- **Network Interface:** Loopback (`lo`)  
- **Packet Handling:** Scapy  
- **Data Management:** Pandas (CSV files)

---
## Stage 1: CSV File Preparation and Data Source-

## Dataset (CSV Input)
The input data is based on real HTTP traffic captured on the loopback interface.

### Data Preparation
1. Network traffic was captured using Wireshark on the loopback interface.
2. An HTTP filter was applied to isolate relevant packets.
3. Selected fields were exported to a CSV file.
4. Column names were adjusted to match the project’s code requirements.
5. The CSV file was loaded and validated in Jupyter Notebook.

<p align="center">
  <img src="images/csv_table_overview.png" width="800">
</p>

*Figure 1: Overview of the CSV file structure after export from Wireshark.*

### Main Fields
- **msg_id** – Unique identifier for each packet  
- **timestamp** – Capture time relative to session start  
- **Source / Destination** – Source and destination IP addresses  
- **src_port / dst_port** – Source and destination ports  
- **Length** – Total packet length  
- **TCP payload** – Payload size at the TCP layer  
- **Flags** – TCP flags (SYN, ACK, FIN, PSH)  
- **Request Method** – HTTP method (if applicable)  
- **message** – Payload content  

---

## Packet Encapsulation Process
The encapsulation logic is implemented manually and maps application data to the TCP/IP layers.

### Key Components
- **Checksum calculation**  
  A custom checksum function is implemented to validate IP and TCP headers.

- **Hexdump utility**  
  Displays packet data in hexadecimal and ASCII format for inspection.

- **IP Header Construction**  
  Fields include version, header length, total length, TTL, protocol, checksum, source IP, and destination IP.

- **TCP Header Construction**  
  Fields include source port, destination port, sequence number, acknowledgment number, flags, window size, and checksum.

### Encapsulation Flow
1. Application data is prepared as payload.
2. TCP header is constructed using source/destination ports and flags.
3. IP header is constructed using source/destination IP addresses.
4. Final packet is assembled as:  
   **IP Header + TCP Header + Payload**

---
