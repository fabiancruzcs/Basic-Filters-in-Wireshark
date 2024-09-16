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
2. Task 2: [Packet Search](https://github.com/fabiancruzcs/Basic-Filters-in-Wireshark/edit/main/README.md#task-2-packet-search)
3. Task 3: [Packet Lengths](https://github.com/fabiancruzcs/Basic-Filters-in-Wireshark/edit/main/README.md#task-3-packet-lengths)
4. Task 4: [Capturing traffic from an IP address](https://github.com/fabiancruzcs/Basic-Filters-in-Wireshark/edit/main/README.md#task-4-capturing-traffic-from-an-ip-address)

## Task 1: Identifying Color Codes

<p align="center">
The packets highlighted in black, usually indicate malformed packets or potential issues like checksum errors. </p>
<p align="center">
<img src="https://imgur.com/ogXBYsm.png" height="70%" width="90%" alt="PCAP data"/>

- **Checksum errors -** The packet’s data integrity check failed, meaning it might be corrupted or altered.
- **Malformed data -** The packet’s structure doesn’t match protocol standards, possibly due to corruption or improper construction.
- **Reassembly issues -** The packet is part of a fragmented message, and Wireshark couldn’t reassemble all the pieces correctly.

In this case, I received an ICMP error message from the network stating "Destination/Port unreachable" which means the network or host informs you that the packet could not be delivered to the destination IP or port. This is normal behavior when there's a **routing issue**, a **firewall blocking the traffic**, or the service at the destination **port isn't available**.

## Task 2: Packet Search

Used `Ctrl + F` to search for packets filtered by **string category**, such as host information.

<p align="center">
Zenoss.services.dom host </p>
<p align="center">
<img src="https://imgur.com/9SifcbB.png" height="70%" width="90%" alt="search"/>

## Task 3: Packet Lengths

Average packet length of the entire pcap file.

<p align="center">
Found under the "Statistics" tab on "Packet Lengths" </p>
<p align="center">
<img src="https://imgur.com/VjHHbwC.png" height="70%" width="90%" alt="avg"/>

<p align="center">
AVG </p>
<p align="center">
<img src="https://imgur.com/kypLWRF.png" height="70%" width="90%" alt="avg"/>


## Task 4: Capturing traffic from an IP address

To capture all traffic associated with the IPv4 address **192.168.66.20**, I applied the following filter in Wireshark:

```
ip.addr == 192.168.66.20
```

This will display all packets where **192.168.66.20** is either the source or destination. The number of displayed packets is shown in the status bar at the bottom of the Wireshark window.

<p align="center">
Traffic capture </p>
<p align="center">
<img src="https://imgur.com/7DV6s2G.png" height="70%" width="90%" alt="traffic"/>
