# Networking Fundamentals Guide

Welcome to this comprehensive guide on networking fundamentals! This guide aims to help you understand the core concepts of computer networking, drawing from practical experience with projects like Docker networking and infrastructure setup.

## Table of Contents

- [Networking Fundamentals Guide](#networking-fundamentals-guide)
  - [Table of Contents](#table-of-contents)
  - [Basic Networking Concepts](#basic-networking-concepts)
    - [What is a Network?](#what-is-a-network)
    - [Types of Networks](#types-of-networks)
        - [1. Based on Size \& Coverage](#1-based-on-size--coverage)
        - [2. Based on Communication Method](#2-based-on-communication-method)
        - [3. Based on Architecture](#3-based-on-architecture)
  - [The OSI Model: Understanding Network Layers](#the-osi-model-understanding-network-layers)
    - [Layer 7 - Application Layer](#layer-7---application-layer)
    - [Layer 6 - Presentation Layer](#layer-6---presentation-layer)
    - [Layer 5 - Session Layer](#layer-5---session-layer)
    - [Layer 4 - Transport Layer](#layer-4---transport-layer)
    - [Layer 3 - Network Layer](#layer-3---network-layer)
    - [Layer 2 - Data Link Layer](#layer-2---data-link-layer)
    - [Layer 1 - Physical Layer](#layer-1---physical-layer)
  - [mac adress](#mac-adress)
  - [ip adress](#ip-adress)
  - [ports](#ports)
  - [sockets](#sockets)
  - [TCP (Transmission Control Protocol)](#tcp-transmission-control-protocol)
  - [UDP](#udp)
  - [IP Addressing and Network Layer](#ip-addressing-and-network-layer)
    - [IPv4 vs IPv6](#ipv4-vs-ipv6)
    - [Public vs Private Addressing](#public-vs-private-addressing)
  - [Understanding Subnet Masks](#understanding-subnet-masks)
  - [Network Devices](#network-devices)
    - [Switches: Local Network Connection](#switches-local-network-connection)
    - [Routers: Inter-network Communication](#routers-inter-network-communication)
  - [Routing and Routing Tables](#routing-and-routing-tables)
    - [Destination Field](#destination-field)
    - [Next Hop Field](#next-hop-field)
  - [Network Address Calculation](#network-address-calculation)
  - [CIDR Notation](#cidr-notation)
  - [Network Ranges and Host Addresses](#network-ranges-and-host-addresses)
  - [DNS and Domain Names: The Internet's Phone Book](#dns-and-domain-names-the-internets-phone-book)
    - [Domain Name System](#domain-name-system)
    - [DNS Hierarchy](#dns-hierarchy)
    - [DNS Record Types](#dns-record-types)
    - [DNS Resolution Process](#dns-resolution-process)
  - [Network Security: Protecting Your Data](#network-security-protecting-your-data)
    - [Encryption and Authentication](#encryption-and-authentication)
    - [Firewalls and Access Control](#firewalls-and-access-control)
    - [Security Best Practices](#security-best-practices)
    - [Common Security Threats](#common-security-threats)
  - [Common Network Tools](#common-network-tools)
      - [Diagnostic Tools](#diagnostic-tools)
      - [Monitoring Tools](#monitoring-tools)
  - [Contributing](#contributing)


## Basic Networking Concepts

### What is a Network?

A computer network is a collection of interconnected devices that can communicate and share resources with each other. Think of it like a postal system where instead of letters, we're sending digital data packets between computers.

### Types of Networks

##### 1. Based on Size & Coverage

 - **Personal Area Network (PAN)** – Small-scale network for personal devices (e.g., Bluetooth, Wi-Fi).
 - **Local Area Network (LAN)** – Covers a small area like a home, office, or building (e.g., Ethernet, Wi-Fi).
 - **Metropolitan Area Network (MAN)** – Covers a city or large campus (e.g., municipal Wi-Fi, cable TV networks).
 - **Wide Area Network (WAN)** – Covers large geographical areas (e.g., the Internet, corporate networks).
 - **Global Area Network (GAN)** – Connects multiple WANs worldwide (e.g., satellite networks, the Internet).

##### 2. Based on Communication Method

 - **Wired Network** – Uses cables (e.g., Ethernet, Fiber optics).
 - **Wireless Network** – Uses radio waves or infrared (e.g., Wi-Fi, cellular networks, satellite).

##### 3. Based on Architecture

 - **Client-Server Network** – A central server manages clients (e.g., web services, databases).
 - **Peer-to-Peer (P2P) Network** – Devices communicate directly without a central server (e.g., file-sharing networks like BitTorrent).

## The OSI Model: Understanding Network Layers

The OSI (Open Systems Interconnection) model provides a conceptual framework that helps us understand how network communications work. Think of it as a seven-layer cake, where each layer has a specific role in handling network communications.

### Layer 7 - Application Layer
The Application layer is what end-users interact with directly. When you open a web browser or email client, you're working at this layer. It provides networking options to programs running on a computer. Protocols at this layer include:
- HTTP for web browsing
- SMTP for email transmission
- FTP for file transfers
- SSH for secure remote access

### Layer 6 - Presentation Layer
Think of the Presentation layer as a translator. It takes data from the Application layer and converts it into a standardized format for transmission. This layer handles:
- Data encryption and decryption
- Character code translation (like ASCII to EBCDIC)
- Data compression
- Data formatting

### Layer 5 - Session Layer
The Session layer manages the connections between applications, much like a phone operator managing calls. It:
- Establishes, maintains, and terminates connections
- Handles authentication and authorization
- Manages dialogue control between systems
- Provides synchronization points for long data transfers

### Layer 4 - Transport Layer
The Transport layer ensures complete data transfer, like a postal service's tracking system. Here we find:
- TCP (Transmission Control Protocol)
  - Connection-oriented
  - Guarantees delivery
  - Handles flow control
- UDP (User Datagram Protocol)
  - Connectionless
  - Faster but unreliable
  - Used for streaming and gaming

### Layer 3 - Network Layer
The Network layer handles routing between different networks, like a mail sorting facility. This is where IP (Internet Protocol) operates, managing:
- Logical addressing (IP addresses)
- Route determination between networks
- Packet forwarding
- Traffic control

### Layer 2 - Data Link Layer
The Data Link layer manages direct point-to-point data delivery, like a local courier service. It handles:
- Physical addressing (MAC addresses)
- Error detection and correction
- Flow control between adjacent nodes
- Access to the physical medium

### Layer 1 - Physical Layer
The Physical layer deals with the actual physical transmission of data, like the roads and vehicles in our postal service analogy. It manages:
- Electrical signals
- Cable types and specifications
- Pin layouts
- Physical network designs


## mac adress

## ip adress

## ports

## sockets

## TCP (Transmission Control Protocol)

TCP operates at the transport layer of the network stack. To understand its role, let's look at how data moves through the network:

TCP provides critical features for reliable data transmission:
- Establishes a connection before data transfer begins
- Breaks large data into manageable packets
- Ensures packets arrive in the correct order
- Verifies data integrity
- Handles retransmission of lost packets

This reliability makes TCP ideal for applications where accuracy is crucial, like web browsing, email, and file transfers.

## UDP







## IP Addressing and Network Layer

IP addressing operates at the network layer and provides the fundamental addressing scheme for all internet communications.

### IPv4 vs IPv6

IPv4 uses 32-bit addresses, written as four octets (e.g., 192.168.1.1). While IPv4 is still widely used, its approximately 4.3 billion possible addresses are insufficient for modern needs. This led to the development of IPv6, which uses 128-bit addresses and provides an effectively unlimited address space.

### Public vs Private Addressing

Networks use two types of IP addresses:

Private IP ranges (reserved for internal networks):
```
192.168.0.0 - 192.168.255.255 (65,536 addresses)
172.16.0.0 - 172.31.255.255   (1,048,576 addresses)
10.0.0.0 - 10.255.255.255     (16,777,216 addresses)
```

Public IP addresses are globally routable and must be unique across the internet. Any device directly accessible from the internet must have a public IP address.

## Understanding Subnet Masks

A subnet mask is a 32-bit number that separates the network portion from the host portion of an IP address. Let's work through an example to understand this concept:

Consider this IP address and subnet mask:
```
IP:   104.198.241.125
Mask: 255.255.255.128
```

In binary:
```
IP:   01101000.11000110.11110001.01111101
Mask: 11111111.11111111.11111111.10000000
```

When we apply the mask (using a bitwise AND operation):
```
IP:      01101000.11000110.11110001.01111101
Mask:    11111111.11111111.11111111.10000000
Network: 01101000.11000110.11110001.00000000
```

This gives us a network address of 104.198.241.0

## Network Devices

### Switches: Local Network Connection

A switch operates at the data link layer and connects devices within the same network. Key characteristics:
- No IP address of its own
- Forwards traffic based on MAC addresses
- Only communicates within its local network
- Cannot route between different networks

### Routers: Inter-network Communication

Routers are more sophisticated devices that connect different networks. Important features:
- Has multiple interfaces, each with its own IP address
- Each interface must be on a different network
- Makes routing decisions based on IP addresses
- Maintains routing tables for packet forwarding

## Routing and Routing Tables

Routing tables contain essential information for packet forwarding:

### Destination Field
- Specifies the target network for packets
- Can be a specific network address or a default route
- Default route (0.0.0.0/0) matches any destination

### Next Hop Field
- IP address of the next router in the path
- Must be directly reachable (on the same network)
- Determines the physical path packets will take

## Network Address Calculation

To find a network address, follow these steps:

1. Convert IP address and subnet mask to binary
2. Perform a bitwise AND operation
3. Convert the result back to decimal

Example with IP 192.168.1.100 and mask 255.255.255.0:
```
IP:      11000000.10101000.00000001.01100100
Mask:    11111111.11111111.11111111.00000000
Network: 11000000.10101000.00000001.00000000 = 192.168.1.0
```

## CIDR Notation

CIDR (Classless Inter-Domain Routing) provides a more concise way to express subnet masks:
- Written as a forward slash followed by the number of network bits
- Example: /24 is equivalent to 255.255.255.0
- Example: /16 is equivalent to 255.255.0.0

```plaintext
+----------------+------------------+----------------+--------------+
|  CIDR Notation |  Subnet Mask     |  # of Hosts    |  Block Size  |
+----------------+------------------+----------------+--------------+
|     /30       |  255.255.255.252  |        2       |       4      |
|     /29       |  255.255.255.248  |        6       |       8      |
|     /28       |  255.255.255.240  |       14       |      16      |
|     /27       |  255.255.255.224  |       30       |      32      |
|     /26       |  255.255.255.192  |       62       |      64      |
|     /25       |  255.255.255.128  |      126       |     128      |
|     /24       |  255.255.255.0    |      254       |     256      |
|     /23       |  255.255.254.0    |      510       |     512      |
|     /22       |  255.255.252.0    |     1022       |    1024      |
|     /21       |  255.255.248.0    |     2046       |    2048      |
|     /20       |  255.255.240.0    |     4094       |    4096      |
|     /19       |  255.255.224.0    |     8190       |    8192      |
|     /18       |  255.255.192.0    |    16382       |   16384      |
|     /17       |  255.255.128.0    |    32766       |   32768      |
|     /16       |  255.255.0.0      |    65534       |   65536      |
|     /15       |  255.254.0.0      |   131070       |  131072      |
|     /14       |  255.252.0.0      |   262142       |  262144      |
|     /13       |  255.248.0.0      |   524286       |  524288      |
|     /12       |  255.240.0.0      |  1048574       | 1048576      |
|     /11       |  255.224.0.0      |  2097150       | 2097152      |
|     /10       |  255.192.0.0      |  4194302       | 4194304      |
|     /9        |  255.128.0.0      |  8388606       | 8388608      |
|     /8        |  255.0.0.0        | 16777214       | 16777216     |
+----------------+------------------+----------------+--------------+

Legend:
- CIDR Notation: The /X format for subnetting.
- Subnet Mask: The decimal form of the subnet mask.
- # of Hosts: Usable IPs (total - 2 for network & broadcast).
- Block Size: Number of total IPs in each subnet.

Quick Tip:
  Block Size = 2^(32 - CIDR)
  Hosts = Block Size - 2 (for network & broadcast)
```

## Network Ranges and Host Addresses

When working with networks, remember:
- Network address (all host bits 0) cannot be assigned to hosts
- Broadcast address (all host bits 1) cannot be assigned to hosts
- Valid host addresses fall between these two numbers

Example for network 192.168.1.0/24:
- Network address: 192.168.1.0
- Broadcast address: 192.168.1.255
- Valid host range: 192.168.1.1 - 192.168.1.254

Remember these key points when designing networks:
- Networks connected to different router interfaces must not overlap
- All devices on the same network must use addresses from the same range
- When connecting to the internet, avoid using private IP addresses















## DNS and Domain Names: The Internet's Phone Book

The Domain Name System (DNS) converts human-readable domain names into IP addresses, similar to how a phone book converts names into phone numbers.

### Domain Name System
- Translates domain names to IP addresses
- Hierarchical naming system
- Distributed database
- Essential for web browsing

### DNS Hierarchy
The DNS system is organized in a hierarchical structure:
- Root Domain (.)
- Top-Level Domains (com, org, net, etc.)
- Second-Level Domains (google.com, microsoft.com)
- Subdomains (mail.google.com)

### DNS Record Types
Different DNS records serve different purposes:
- A Record: Maps hostname to IPv4 address
- AAAA Record: Maps hostname to IPv6 address
- CNAME Record: Creates an alias for another domain
- MX Record: Specifies mail servers
- TXT Record: Holds text information
- NS Record: Identifies authoritative name servers

### DNS Resolution Process
When you type a URL in your browser, here's what happens:
1. Browser checks its cache for the IP address
2. If not found, asks the operating system
3. OS checks its DNS cache
4. If not found, queries the configured DNS server
5. DNS server either returns the IP or forwards the request
6. Once found, the IP is returned and cached

## Network Security: Protecting Your Data

Network security is crucial in today's interconnected world. Let's explore key security concepts and practices.

### Encryption and Authentication
- SSL/TLS
  - Encrypts data in transit
  - Provides authentication
  - Uses digital certificates
  - Essential for secure web traffic

- Public Key Infrastructure (PKI)
  - Manages digital certificates
  - Enables secure communication
  - Uses public/private key pairs
  - Verifies identity of parties

### Firewalls and Access Control
Firewalls protect networks by:
- Filtering traffic based on rules
- Blocking unauthorized access
- Monitoring network activity
- Preventing malicious attacks

Types of firewalls:
- Packet filtering firewalls
- Stateful inspection firewalls
- Application layer firewalls
- Next-generation firewalls

### Security Best Practices
To maintain network security:
- Regular security updates and patches
- Strong authentication mechanisms
- Network segmentation
- Regular security audits
- Intrusion detection systems
- Security policies and procedures
- Employee security training

### Common Security Threats
Understanding common threats helps in protection:
- DDoS attacks: Overwhelming servers with traffic
- Man-in-the-middle attacks: Intercepting communications
- SQL injection: Attacking databases through web applications
- Phishing: Social engineering attacks
- Malware: Malicious software infiltration

## Common Network Tools

#### Diagnostic Tools
- ping: Test connectivity
- traceroute: Show packet path
- nslookup/dig: DNS query tools
- netstat: Network statistics

#### Monitoring Tools
- tcpdump: Packet analyzer
- Wireshark: Network protocol analyzer
- iftop: Bandwidth monitoring
- nmap: Network scanning

## Contributing

Feel free to contribute to this guide by submitting pull requests or opening issues for any corrections or additions.

- https://www.youtube.com/watch?v=VPToE8vwKew&t=833s
- https://www.youtube.com/watch?v=TNQsmPf24go
- https://www.youtube.com/playlist?list=PLzdnOPI1iJNfMRZm5DDxco3UdsFegvuB7
- https://www.youtube.com/watch?v=keeqnciDVOo
- https://www.youtube.com/watch?v=sMHzfigUxz4
- https://www.youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi
- https://www.youtube.com/playlist?list=PLIFyRwBY_4bQUE4IB5c4VPRyDoLgOdExE
- https://www.youtube.com/watch?v=vtUHgkTKju0
- https://www.youtube.com/playlist?list=PL7zRJGi6nMRzg0LdsR7F3olyLGoBcIvvg
- https://www.youtube.com/watch?v=p3vaaD9pn9I
- https://www.youtube.com/watch?v=qiQR5rTSshw
