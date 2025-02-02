# Networking Notes

## OSI Model and Functions

| Layer          | Function                                                                            |
| -------------- | ----------------------------------------------------------------------------------- |
| Application    | end user applications. i.e. HTTP, DNS, FTP                                          |
| Presentation   | Defining data formats and converting data. E.g ASCII, Binary, Encryption, JPEG etc. |
| Session        | app session coordination, setup, maintenance, termination                           |
| Transport      | end to end data transfer. TCP/UDP unicast vs multicast                              |
| Network        | packet forwarding, routing, subnet masking                                          |
| Data Link      | error correct, node to node data transfer (e.g. switches, hubs)                     |
| Physical Layer | cables, ethernet, bandwidth                                                         |

`NOTE`: TCP/IP is the same but Application, presentation, sessions are combined into application.

---

## Physical Layer

#### Responsible for trasnmitting individual bits from one node to another

- Transmission medium between sender and receiver
- can be air or cable
- point to point vs multipoint connection (direct vs branch out to multiple devices)
- bit encoding
- synchronisation of clocks
- cable types (simplex, half-duplex, duplex)

## Data Link Layer

#### Responsible for transmitting frames between network and physical layer

- Framing
- Physical addressing
- flow control
- Error control
- Access control (control collisions)

### DLC (data link control layer)

- Framing (fixed sized vs variable)
- Parity checking

## Network Layer

#### Responsible for source to destination delivery of packets

- logical addressing (e.g. 192.168.1.0)
- routing (between `networks`)

## Transport Layer

- Service point addressing
- segmentation and reassembly
- connection control (connection oriented or connectionless)
- flow control (end to end)
- error control (process to process)

#### Common ports

- 8080 (http), 21 (FTP), 22 (SSH), 53 (DNS)

## Session Layer

#### Responsible for dialog control and synchronisation

## Presentation Layer

#### Responsible for translation, compression and encryption between session and application layers

## Application Layer

#### Responsible for providing services to the end user

----
### 1. Explain the difference between a hub, switch, and router.
- **Hub**: A basic networking device that broadcasts data to all connected devices. It doesn’t filter traffic.
- **Switch**: More intelligent than a hub, it forwards data only to the device it’s intended for, based on MAC addresses.
- **Router**: Routes data between different networks, typically between a local network and the internet. It uses IP addresses to direct traffic.

### 2. What is the difference between IPv4 and IPv6?
- **IPv4**: 32-bit address format (e.g., 192.168.1.1), supports about 4.3 billion addresses. It’s widely used but has limited address space.
- **IPv6**: 128-bit address format (e.g., 2001:0db8::), supports a much larger address space, resolving IPv4 address exhaustion issues.

### 3. What is subnetting, and why is it useful?
- **Subnetting**: Dividing a network into smaller sub-networks (subnets). It improves network management, security, and efficiency by isolating traffic within subnets.

### 4. How does ARP (Address Resolution Protocol) work?
- **ARP** maps an IP address to a MAC address. When a device needs to communicate with another on the same local network, ARP sends a broadcast to resolve the MAC address of the destination IP.

### 5. What is NAT (Network Address Translation), and why is it used?
- **NAT** allows multiple devices on a private network to share a single public IP address. It helps conserve public IP addresses and adds a layer of security by hiding internal IPs.

### 6. What are VLANs, and how do they improve network security and efficiency?
- **VLANs** (Virtual LANs) divide a physical network into multiple logical networks. They improve security by isolating broadcast traffic and enhancing network efficiency by segmenting traffic based on departments or roles.

### 7. What is the difference between a broadcast domain and a collision domain?
- **Broadcast Domain**: A network segment where all devices receive broadcast packets. Routers separate broadcast domains.
- **Collision Domain**: A network segment where data packets can collide. Switches and bridges reduce collision domains by creating separate collision domains for each port.

### 8. Explain the purpose of DNS and how it works.
- **DNS** (Domain Name System) translates human-readable domain names (like example.com) into IP addresses. It works by querying DNS servers to resolve domain names to IP addresses for communication.

### 9. What is DHCP, and how does it assign IP addresses?
- **DHCP** (Dynamic Host Configuration Protocol) automatically assigns IP addresses to devices on a network. It assigns addresses from a predefined pool and leases them for a set period.

### 10. What is the difference between static and dynamic routing?
- **Static Routing**: Fixed routes manually configured by the network administrator. It doesn’t adapt to network changes.
- **Dynamic Routing**: Routes that automatically adjust based on network conditions, using protocols like OSPF or BGP to discover the best paths.

### 11. What is port forwarding?
- **Port Forwarding**: Allows you to forward traffic from your local machine to another server via an intermediary (usually an SSH tunnel).

### 12. What is a MAC address and how is it used in networking?

A **MAC address** (Media Access Control address) is a unique identifier assigned to a network interface card (NIC) for use in network communications at the Data Link Layer (Layer 2) of the OSI model.

- **Format**: A MAC address is typically written as six pairs of hexadecimal digits (e.g., `00:14:22:01:23:45`).
- **Purpose**: It ensures that devices on a local network can identify and communicate with each other directly.
- **Usage**: MAC addresses are used by Ethernet and Wi-Fi networks to direct data frames to specific devices on the same physical network.
  
### 13. What are the most important QoS measures?

- **Bandwidth**: The amount of data that can be transmitted in a given period, usually measured in bits per second (bps). Higher bandwidth ensures more data can be transferred simultaneously.
- **Latency**: The time it takes for data to travel from the source to the destination. Lower latency is crucial for real-time applications like VoIP and online gaming.
- **Jitter**: The variation in latency over time. High jitter can cause delays and issues in voice or video communication, making it essential to maintain stable latency.
- **Packet Loss**: The percentage of packets lost during transmission. Packet loss can degrade performance, especially for real-time applications, and should be minimized.
- **Throughput**: The actual rate of data transfer achieved over a network, accounting for factors like congestion, protocol overhead, and transmission errors.
- **Error Rate**: The rate at which errors occur in data transmission. A low error rate ensures reliable communication and fewer retransmissions.
- **Priority/Traffic Shaping**: The ability to prioritise certain types of traffic (e.g., VoIP, streaming) over others (e.g., file downloads) to ensure critical applications perform well under heavy load.

### 14. What is FTP?
- **FTP**: FTP (File Transfer Protocol) is a standard network protocol used for the transfer of files from one host to another over a TCP-based network, such as the Internet. FTP works by opening two connections that link the computers trying to communicate with each other.
