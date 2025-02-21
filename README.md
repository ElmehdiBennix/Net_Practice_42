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
  - [How Data Flows Through the OSI Model](#how-data-flows-through-the-osi-model)
    - [Data Flow Process](#data-flow-process)
- [Understanding TCP/IP and OSI Models](#understanding-tcpip-and-osi-models)
    - [Layer 1 - Network Access Layer (Link Layer)](#layer-1---network-access-layer-link-layer)
    - [Layer 2 - Internet Layer](#layer-2---internet-layer)
    - [Layer 3 - Transport Layer](#layer-3---transport-layer)
    - [Layer 4 - Application Layer](#layer-4---application-layer)
  - [How Data Flows Through TCP/IP](#how-data-flows-through-tcpip)
  - [TCP/IP vs OSI Model Comparison](#tcpip-vs-osi-model-comparison)
      - [Structure](#structure)
      - [Key Differences](#key-differences)
        - [Flexibility and Practical Use](#flexibility-and-practical-use)
        - [Layer Independence](#layer-independence)
        - [Historical Context](#historical-context)
        - [Implementation](#implementation)
- [IP Addressing](#ip-addressing)
  - [IPv4 vs IPv6](#ipv4-vs-ipv6)
- [Understanding IPv4 Addresses and Subnet Masks](#understanding-ipv4-addresses-and-subnet-masks)
  - [IPv4 Address Fundamentals](#ipv4-address-fundamentals)
  - [Understanding Network and Host Portions](#understanding-network-and-host-portions)
  - [Subnet Masks](#subnet-masks)
    - [Example Calculation](#example-calculation)
  - [CIDR Notation](#cidr-notation)
  - [Network Ranges and Host Addresses](#network-ranges-and-host-addresses)
- [Network Devices](#network-devices)
    - [Switches: Local Network Connection](#switches-local-network-connection)
    - [Routers: Inter-network Communication](#routers-inter-network-communication)
  - [Routing and Routing Tables](#routing-and-routing-tables)
    - [Destination Field](#destination-field)
    - [Next Hop Field](#next-hop-field)
- [Understanding Public vs Private IP Addresses](#understanding-public-vs-private-ip-addresses)
  - [The Apartment Building Analogy](#the-apartment-building-analogy)
  - [Public IP Addresses (rework)](#public-ip-addresses-rework)
  - [Private IP Addresses (rework)](#private-ip-addresses-rework)
  - [How They Work Together](#how-they-work-together)
  - [Advantages of This System](#advantages-of-this-system)
- [Understanding DHCP and Network Address Translation (NAT)](#understanding-dhcp-and-network-address-translation-nat)
  - [DHCP Basics](#dhcp-basics)
  - [The DHCP Process](#the-dhcp-process)
    - [1. DHCP Discovery](#1-dhcp-discovery)
    - [2. DHCP Offer](#2-dhcp-offer)
    - [3. Address Assignment and Configuration](#3-address-assignment-and-configuration)
  - [Network Address Translation (NAT)](#network-address-translation-nat)
    - [How NAT Actually Works](#how-nat-actually-works)
    - [Types of NAT](#types-of-nat)
      - [Static NAT](#static-nat)
      - [Dynamic NAT](#dynamic-nat)
      - [Port Address Translation (PAT)](#port-address-translation-pat)
    - [Why NAT is Important](#why-nat-is-important)
      - [Security](#security)
      - [IP Address Conservation](#ip-address-conservation)
      - [Network Flexibility](#network-flexibility)
    - [Real-World Example](#real-world-example)
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
- [Ressources](#ressources)
- [Contributing](#contributing)


# Basic Networking Concepts

## What is a Network?

A computer network is a collection of interconnected devices that can communicate and share resources with each other. Think of it like a postal system where instead of letters, we're sending digital data packets between computers.

## Types of Networks

#### 1. Based on Size & Coverage

 - **Personal Area Network (PAN)** – Small-scale network for personal devices (e.g., Bluetooth, Wi-Fi).
 - **Local Area Network (LAN)** – Covers a small area like a home, office, or building (e.g., Ethernet, Wi-Fi).
 - **Metropolitan Area Network (MAN)** – Covers a city or large campus (e.g., municipal Wi-Fi, cable TV networks).
 - **Wide Area Network (WAN)** – Covers large geographical areas (e.g., the Internet, corporate networks).
 - **Global Area Network (GAN)** – Connects multiple WANs worldwide (e.g., satellite networks, the Internet).

#### 2. Based on Communication Method

 - **Wired Network** – Uses cables (e.g., Ethernet, Fiber optics).
 - **Wireless Network** – Uses radio waves or infrared (e.g., Wi-Fi, cellular networks, satellite).

#### 3. Based on Architecture

 - **Client-Server Network** – A central server manages clients (e.g., web services, databases).
 - **Peer-to-Peer (P2P) Network** – Devices communicate directly without a central server (e.g., file-sharing networks like BitTorrent).

# The OSI Model: Understanding Network Layers

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
The Session layer manages the connections between applications, much like a phone operator managing calls.
it uses the ports defined in layer 4 to create sockets and sessions between communicating devices/programs/etc It:
- Establishes, maintains, and terminates connections
- Handles authentication and authorization
- Manages dialogue control between systems
- Provides synchronization points for long data transfers

### Layer 4 - Transport Layer
The Transport layer ensures complete data transfer via ports, like a postal service's tracking system. Here we find:
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

## How Data Flows Through the OSI Model

Let me walk you through how data travels through each layer of the OSI model, focusing on what happens when you send and receive data. I'll use the example of sending an email to make it more concrete.

### Data Flow Process

```plaintext
Sending Process (Data Encapsulation):

7. Application Layer: Creates email content and commands
   (Your email text + SMTP commands)
↓
6. Presentation Layer: Formats and encrypts if needed
   (Converts to ASCII, compresses, encrypts)
↓
5. Session Layer: Establishes communication session
   (Opens and maintains dialog between computers)
↓
4. Transport Layer: Segments data and ensures reliability
   (Breaks message into manageable chunks, adds sequence numbers)
↓
3. Network Layer: Adds logical addressing and routing
   (Adds source and destination IP addresses)
↓
2. Data Link Layer: Frames data for transmission
   (Adds MAC addresses, error checking)
↓
1. Physical Layer: Converts to binary signals
   (Transmits as electrical, light, or radio signals)

Receiving Process (Data De-encapsulation):

1. Physical Layer: Receives binary signals
   (Converts signals back to digital data)
↓
2. Data Link Layer: Checks for transmission errors
   (Verifies frame integrity, removes MAC addresses)
↓
3. Network Layer: Processes IP addresses
   (Confirms correct destination, removes IP headers)
↓
4. Transport Layer: Reassembles segments
   (Orders segments, requests retransmission if needed)
↓
5. Session Layer: Manages dialog control
   (Maintains and closes communication session)
↓
6. Presentation Layer: Decrypts and formats
   (Decrypts data, converts to usable format)
↓
7. Application Layer: Delivers to email application
   (Final data presented to user's email client)
```

Each layer adds its own header during encapsulation (sending), and these headers are removed in reverse order during de-encapsulation (receiving).

# Understanding TCP/IP and OSI Models

###  Layer 1 - Network Access Layer (Link Layer)
This is like the local postal worker who physically delivers mail to your doorstep. It handles the physical transmission of data, including:
- Converting data into electrical signals, light, or radio waves
- Managing physical addressing (MAC addresses)
- Coordinating when devices can transmit on shared media
- Error detection at the hardware level

###  Layer 2 - Internet Layer
Think of this as the national sorting centers that determine the best route for packages. This layer:
- Handles logical addressing (IP addresses)
- Routes packets between networks
- Fragments large messages into smaller packets when needed
- Implements the Internet Protocol (IP)

###  Layer 3 - Transport Layer
This layer acts like the tracking and delivery confirmation system. It provides:
- End-to-end communication management
- Reliable data delivery (TCP) or faster, less reliable delivery (UDP)
- Flow control to prevent overwhelming receivers
- Error checking and recovery at the protocol level

###  Layer 4 - Application Layer
This is like the various types of mail services available (regular mail, certified mail, express delivery). It includes:
- Protocols for specific services (HTTP, FTP, SMTP, etc.)
- User interfaces and applications
- Data formatting and encryption

## How Data Flows Through TCP/IP

When you send data (like loading a webpage):

```plaintext
Sending Process:
Application Layer: Your browser requests a webpage (HTTP)
↓
Transport Layer: TCP establishes connection, breaks data into segments
↓
Internet Layer: IP adds addressing, determines routing
↓
Network Access Layer: Converts to physical signals and transmits

Receiving Process:
Network Access Layer: Receives signals, converts to digital data
↓
Internet Layer: Verifies addressing, reassembles packets
↓
Transport Layer: Ensures all segments arrived, orders them correctly
↓
Application Layer: Presents webpage to user
```

## TCP/IP vs OSI Model Comparison

Let's compare these two important networking models:

#### Structure
```plaintext
OSI Model (7 Layers)     TCP/IP Model (4 Layers)
7. Application    →      4. Application
6. Presentation   →
5. Session        →
4. Transport      →      3. Transport
3. Network        →      2. Internet
2. Data Link      →      1. Network Access
1. Physical       →
```

#### Key Differences

##### Flexibility and Practical Use
- TCP/IP is more practical and widely implemented
- OSI is more theoretical and helps in understanding network concepts
- TCP/IP combines several OSI layers for efficiency

##### Layer Independence
- OSI has clear, separate functions for each layer
- TCP/IP has some overlapping functions between layers
- OSI is more rigid, while TCP/IP is more flexible

##### Historical Context
- TCP/IP was developed first and drove internet development
- OSI was developed later as a more comprehensive, theoretical model
- TCP/IP evolved from practical needs, while OSI was designed as an ideal standard

##### Implementation
- TCP/IP is the actual protocol used on the internet
- OSI serves primarily as a reference model for understanding networking
- TCP/IP protocols are more widely used and supported

# IP Addressing

IP addressing operates at the network layer and provides the fundamental addressing scheme for all internet communications.

## IPv4 vs IPv6

IPv4 uses 32-bit addresses, written as four octets **(e.g., 192.168.1.1)**. While IPv4 is still widely used, its approximately 4.3 billion possible addresses are insufficient for modern needs. This led to the development of IPv6 **(e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334)**, which uses 128-bit addresses and provides an effectively unlimited address space.

# Understanding IPv4 Addresses and Subnet Masks

## IPv4 Address Fundamentals
An IP address is a 32-bit number typically written in four octets (groups of 8 bits), separated by dots. For example: `192.168.1.100`

Each number in the address can range from 0 to 255, representing one byte (8 bits) of the address. When we work with IP addresses, we often need to think about them in binary form:

```
192.168.1.100 in binary:
11000000.10101000.00000001.01100100
```

## Understanding Network and Host Portions
- The network portion - identifies which network the device belongs to
- The host portion - identifies the specific device on that network

But how do we know where the network portion ends and the host portion begins? This is where subnet masks come in.

## Subnet Masks
A subnet mask is a 32-bit number that acts like a template, showing us which parts of an IP address belong to the network and which parts identify the host. Here's how it works:

- Bits set to 1 in the subnet mask indicate "network portion"
- Bits set to 0 in the subnet mask indicate "host portion"

### Example Calculation
Let's work through calculating a network address:

```
IP Address:  192.168.1.100
Subnet Mask: 255.255.255.0

In binary:
IP:   11000000.10101000.00000001.01100100
Mask: 11111111.11111111.11111111.00000000
```

To find the network address, we perform a bitwise AND operation between the IP and the mask:

```
IP:      11000000.10101000.00000001.01100100
Mask:    11111111.11111111.11111111.00000000
Network: 11000000.10101000.00000001.00000000 = 192.168.1.0
```

In this example:
- Network portion: 192.168.1
- Host portion: The last number (100)
- Network address: 192.168.1.0

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

# Network Devices

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

# Understanding Public vs Private IP Addresses

Let me explain the key differences between public and private IP addresses using an analogy that might help make this clearer.

## The Apartment Building Analogy

Think of the internet like a city, and each building has its own unique street address (public IP). Inside an apartment building, each apartment has its own internal unit number (private IP). This helps illustrate how our networks work.

## Public IP Addresses (rework)

Public IP addresses are like the building's street address - they must be globally unique and visible to everyone. These addresses have several key characteristics:

```plaintext
Key Properties of Public IPs:
- Must be unique across the entire internet
- Assigned by Internet Service Providers (ISPs)
- Directly accessible from the internet
- Limited in quantity
- Can be static (fixed) or dynamic (changing)
```

## Private IP Addresses (rework)

Private IP addresses are like apartment numbers within a building. They can be reused in different buildings because they're only meaningful within their own network. The Internet Assigned Numbers Authority (IANA) has reserved specific ranges for private use:

```plaintext
Private IP Ranges:
192.168.0.0 - 192.168.255.255  (65,536 addresses)
172.16.0.0 - 172.31.255.255    (1,048,576 addresses)
10.0.0.0 - 10.255.255.255      (16,777,216 addresses)
```

## How They Work Together

When you're at home, your devices (phones, laptops, smart TVs) each get a private IP address from your router. Your router has one public IP address assigned by your ISP. When your devices need to access the internet, the router performs Network Address Translation (NAT):

1. Your device (private IP: 192.168.1.100) wants to visit a website
2. The request goes to your router
3. The router replaces your private IP with its public IP
4. The website responds to your router's public IP
5. Your router remembers which device made the request and forwards the response

## Advantages of This System

This dual-address system provides several benefits:

1. **Security**: Your devices' private IP addresses are hidden from the internet, adding a layer of protection
2. **Address Conservation**: Multiple devices can share one public IP address
3. **Network Management**: Organizations can use consistent internal addressing across different locations
4. **Flexibility**: You can change your ISP (and public IP) without reconfiguring internal devices

# Understanding DHCP and Network Address Translation (NAT)

## DHCP Basics
DHCP (Dynamic Host Configuration Protocol) plays a crucial role in managing private networks by automatically assigning IP addresses to devices. This process ensures efficient network organization and connectivity.

## The DHCP Process

### 1. DHCP Discovery
When a new device connects to your network, it initiates what's known as the DHCP discovery process. The device broadcasts a special message called a "DHCP DISCOVER" packet across the network. This is similar to walking into a hotel and requesting a room - you're essentially announcing "I need an address to stay at!"

### 2. DHCP Offer
The network's DHCP server (typically running on your router) receives this discovery message and responds with a "DHCP OFFER." This offer includes:
- A proposed private IP address (e.g., 192.168.1.100)
- Lease duration (how long the device can use this address)
- Additional network configuration details (subnet mask, default gateway, DNS servers)

### 3. Address Assignment and Configuration
After the device accepts the offer, the DHCP server confirms the assignment and records it in its lease table. The device now has all the information it needs to communicate on the local network.

## Network Address Translation (NAT)

### How NAT Actually Works

When a device on your private network wants to communicate with the internet, NAT performs a sophisticated translation process:

```plaintext
Step 1: Internal Request
Your Computer (192.168.1.100) → Makes web request to Google.com

Step 2: NAT Translation
Router creates a NAT table entry:
Source IP: 192.168.1.100:3333 → Public IP 203.0.113.1:5555

Step 3: Packet Modification
Router changes the packet header:
- Original: From 192.168.1.100:3333
- Modified: From 203.0.113.1:5555

Step 4: Response Handling
When Google responds to 203.0.113.1:5555
Router checks NAT table and forwards to 192.168.1.100:3333
```

### Types of NAT

Different situations call for different types of NAT:

#### Static NAT
Like having a dedicated receptionist for each person. It creates a one-to-one mapping between a private and public IP address. This is often used for servers that need consistent public access.

#### Dynamic NAT
Like having a pool of receptionists who can handle calls as they come in. It maintains a pool of public IP addresses and assigns them as needed to internal devices.

#### Port Address Translation (PAT)
The most common type in home networks. Think of it as one very efficient receptionist who can handle multiple calls by keeping track of both IP addresses and port numbers. This allows many internal devices to share a single public IP address.

### Why NAT is Important

NAT serves several crucial functions in modern networking:

#### Security
By hiding internal IP addresses, NAT creates a natural firewall. Outside systems can't directly initiate connections to internal devices unless specifically configured.

#### IP Address Conservation
Without NAT, we would have run out of IPv4 addresses long ago. By allowing multiple devices to share one public IP, NAT dramatically reduces the number of public IP addresses needed.

#### Network Flexibility
Organizations can merge or restructure their internal networks without having to change their public IP addressing scheme.

### Real-World Example

Let's say you're at home with multiple devices:
1. Your laptop (192.168.1.100) loads a website
2. Your phone (192.168.1.101) checks email
3. Your smart TV (192.168.1.102) streams video

Your router's NAT system might handle this like:
```plaintext
Device          Private IP:Port     →  Public IP:Port
Laptop          192.168.1.100:3333 →  203.0.113.1:5555
Phone           192.168.1.101:4444 →  203.0.113.1:6666
Smart TV        192.168.1.102:5555 →  203.0.113.1:7777
```

Each device appears to have direct internet access, but NAT is quietly managing all these connections behind the scenes.

# DNS and Domain Names: The Internet's Phone Book

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

# Network Security: Protecting Your Data

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

# Common Network Tools

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


# Ressources

- Youtube Video: [How We Made the Internet - NationSquid](https://www.youtube.com/watch?v=VPToE8vwKew&t=833s)
- Youtube Video: [How Does the Internet Work? - Vox](https://www.youtube.com/watch?v=TNQsmPf24go)
- Youtube Video: [How the Internet Works in 9 Minutes - ByteByteGo](https://www.youtube.com/watch?v=sMHzfigUxz4)
- Youtube Playlist: [How The Internet Works - Code.org](https://www.youtube.com/playlist?list=PLzdnOPI1iJNfMRZm5DDxco3UdsFegvuB7)
- Youtube Video: [Computer Networking in 100 Seconds - FireShip](https://www.youtube.com/watch?v=keeqnciDVOo)
- Stackexchange Question: [OSI Model and Networking Protocols Relationship](https://networkengineering.stackexchange.com/questions/6380/osi-model-and-networking-protocols-relationship/6381#6381)
- Youtube Playlist: [TCP & UDP Masterclass - Practical Networking](https://www.youtube.com/playlist?list=PLIFyRwBY_4bS-PQZoF0UySdG0sH9VA0bn)
- Youtube Playlist: [Networking Fundamentals - Practical Networking](https://www.youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi)
- Youtube Playlist: [Subnetting Mastery - Practical Networking](https://www.youtube.com/playlist?list=PLIFyRwBY_4bQUE4IB5c4VPRyDoLgOdExE)
- Youtube Video: [Every Networking Concept Explained In 8 Minutes - Privacy Matters](https://www.youtube.com/watch?v=vtUHgkTKju0)
- Youtube Playlist: [PowerCert Animated Videos - Networking Animated Videos](https://www.youtube.com/playlist?list=PL7zRJGi6nMRzg0LdsR7F3olyLGoBcIvvg)
- Youtube Video: [Networking For Hackers! (Common Network Protocols) - Hacker Joe](https://www.youtube.com/watch?v=p3vaaD9pn9I)
- Youtube Video: [Computer Networking Course - Network Engineering [CompTIA Network+ Exam Prep] - freeCodeCamp.org](https://www.youtube.com/watch?v=qiQR5rTSshw)

# Contributing

Feel free to contribute to this guide by submitting pull requests or opening issues for any corrections or additions.
