# Basic Filters in Wireshark - Lab

In this lab, I used Wireshark on Ubuntu Server 20.04 to analyze network traffic. I learned how to apply basic filters, understand Wireshark's color codes, and distinguish between key data and background noise, gaining hands-on experience with packet analysis.

## Tools and Technologies Used 
| Used                                    | Description                                                                                       |
|-----------------------------------------|---------------------------------------------------------------------------------------------------|
| ubuntu server 20.04  | A Linux OS for server management and networking tasks.    |
| Wireshark                                 | A network protocol analyzer for capturing and inspecting traffic.           |
| PCAP file                                 | A binary file format that stores network traffic data in a structured manner.          |

## Table of Contents
1. Task 1: [Identifying Color Codes](https://github.com/fabiancruzcs/Using-Basic-Filters-in-Wireshark/edit/main/README.md#task-1-identifying-color-codes)
2. Task 2: Analyzing Traffic by Protocol
3. Task 3: Applying Basic Filters
4. Task 4: Filtering Important Data vs. Noise

## Task 1: Identifying Color Codes

<p align="center">
1. The packets highlighted in black, usually indicate malformed packets or potential issues like checksum errors. </p>
<p align="center">
<img src="https://imgur.com/ogXBYsm.png" height="50%" width="70%" alt="PCAP data"/>

### Key learnings:
- **Checksum errors -** The packet’s data integrity check failed, meaning it might be corrupted or altered.
- **Malformed data -** The packet’s structure doesn’t match protocol standards, possibly due to corruption or improper construction.
- **Reassembly issues -** The packet is part of a fragmented message, and Wireshark couldn’t reassemble all the pieces correctly.

In this case, I received an ICMP error message from the network stating "Destination/Port unreachable" which means the network or host informs you that the packet could not be delivered to the destination IP or port. This is normal behavior when there's a **routing issue**, a **firewall blocking the traffic**, or the service at the destination **port isn't available**.
