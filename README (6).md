# Foundations of Computer Networks & DevOps

A comprehensive reference guide and documentation repository covering essential foundations of **Computer Networks for DevOps, Cloud Engineering, and Backend Systems**. Grounded in the *Chai aur DevOps / Chai aur Code* networking boot camp led by Akash and Hitesh Choudhary.

---

## 📋 Table of Contents

- [Overview & Learning Objectives](#overview--learning-objectives)
- [Chapter 1: Networking Fundamentals](#chapter-1-networking-fundamentals)
  - [History of the Internet](#history-of-the-internet)
  - [Core Terminology & Submarine Cables](#core-terminology--submarine-cables)
  - [Internet vs. World Wide Web (WWW)](#internet-vs-world-wide-web-www)
  - [Client-Server Architecture](#client-server-architecture)
  - [Types of Networks](#types-of-networks)
  - [Network Topologies](#network-topologies)
- [Chapter 2: Network Models](#chapter-2-network-models)
  - [The OSI 7-Layer Model](#the-osi-7-layer-model)
  - [TCP/IP Model (4/5 Layers)](#tcpip-model-45-layers)
  - [Encapsulation, Decapsulation & PDUs](#encapsulation-decapsulation--pdus)
  - [Message Delivery Types](#message-delivery-types)
- [Chapter 3: Network Devices & Hardware](#chapter-3-network-devices--hardware)
  - [Network Interface Card (NIC) & MAC Address](#network-interface-card-nic--mac-address)
  - [Hub, Bridge, Switch, and Router](#hub-bridge-switch-and-router)
  - [Modem, Gateways, and ISP Tiers](#modem-gateways-and-isp-tiers)
  - [Firewalls & Host-to-Host Communication](#firewalls--host-to-host-communication)
- [Chapter 4: Network Layer, IP Addressing & Subnetting](#chapter-4-network-layer-ip-addressing--subnetting)
  - [IPv4 vs. IPv6](#ipv4-vs-ipv6)
  - [Private vs. Public vs. Loopback IP Addresses](#private-vs-public-vs-loopback-ip-addresses)
  - [Static vs. Dynamic IP (DHCP)](#static-vs-dynamic-ip-dhcp)
  - [Subnetting: Classful vs. Classless (CIDR)](#subnetting-classful-vs-classless-cidr)
  - [Anatomy of an IP Packet](#anatomy-of-an-ip-packet)
  - [Network Address Translation (NAT) & Port Forwarding](#network-address-translation-nat--port-forwarding)
  - [ICMP, Ping, and Traceroute](#icmp-ping-and-traceroute)
- [Chapter 5: Transport Layer (TCP & UDP)](#chapter-5-transport-layer-tcp--udp)
  - [Port Numbers & Multiplexing](#port-numbers--multiplexing)
  - [User Datagram Protocol (UDP)](#user-datagram-protocol-udp)
  - [Transmission Control Protocol (TCP)](#transmission-control-protocol-tcp)
  - [TCP 3-Way Handshake & 4-Way Connection Teardown](#tcp-3-way-handshake--4-way-connection-teardown)
  - [Flow Control (Sliding Window) & Congestion Control](#flow-control-sliding-window--congestion-control)
  - [Head-of-Line (HoL) Blocking](#head-of-line-hol-blocking)
- [Chapter 6: Application Layer Protocols](#chapter-6-application-layer-protocols)
  - [DNS (Domain Name System) & Record Types](#dns-domain-name-system--record-types)
  - [SSL / TLS & Digital Certificates](#ssl--tls--digital-certificates)
  - [Server Name Indication (SNI)](#server-name-indication-sni)
  - [HTTP Evolution: HTTP/1.1, HTTP/2, and HTTP/3 (QUIC)](#http-evolution-http11-http2-and-http3-quic)
  - [WebSockets & Real-Time Communication](#websockets--real-time-communication)
- [Chapter 7: Proxies & Load Balancers](#chapter-7-proxies--load-balancers)
  - [Forward Proxy vs. Reverse Proxy](#forward-proxy-vs-reverse-proxy)
  - [Layer 4 (L4) vs. Layer 7 (L7) Load Balancing](#layer-4-l4-vs-layer-7-l7-load-balancing)
- [Chapter 8: Applied Networking for DevOps & AWS Cloud](#chapter-8-applied-networking-for-devops--aws-cloud)
  - [SSH Remote Management & Agent Forwarding](#ssh-remote-management--agent-forwarding)
  - [AWS VPC, Regions, and Availability Zones](#aws-vpc-regions-and-availability-zones)
  - [Public & Private Subnets](#public--private-subnets)
  - [Internet Gateways (IGW) & NAT Gateways](#internet-gateways-igw--nat-gateways)
  - [Security Groups vs. Network ACLs (NACLs)](#security-groups-vs-network-acls-nacls)
  - [AWS Load Balancers (ALB vs. NLB)](#aws-load-balancers-alb-vs-nlb)
  - [VPC Peering & AWS Transit Gateway](#vpc-peering--aws-transit-gateway)
- [🛠️ CLI & Terminal Cheatsheet](#️-cli--terminal-cheatsheet)
- [📜 License](#-license)

---

## Overview & Learning Objectives

DevOps and Cloud Engineering require a rock-solid understanding of networking fundamentals. While theoretical computer networking covers textbook definitions, **DevOps-centric networking** filters these concepts down to what is directly applicable in real-world infrastructure, modern application deployment, microservices architecture, and cloud management.

### Key Takeaways
1. Understand end-to-end data flow across local networks, submarine infrastructure, and the internet.
2. Master the OSI 7-Layer and TCP/IP reference models with practical protocol mappings.
3. Perform subnetting, CIDR calculations, NAT configuration, and IP routing troubleshooting.
4. Distinguish between L4 and L7 proxies, reverse proxies, and load balancers.
5. Build production-grade cloud network infrastructure on AWS using VPCs, Subnets, Gateways, Security Groups, NACLs, and VPC Peering/Transit Gateways.

---

## Chapter 1: Networking Fundamentals

### History of the Internet
- **ARPANET (1969)**: Funded by the US Department of Defense (DARPA) during the Cold War to build a decentralized communications network resistant to single-node failures.
- **First Message**: Transmitted on October 29, 1969, between UCLA and Stanford. The intended message was , but the system crashed after delivering the first two letters: .
- **TCP/IP Adoption (1983)**: ARPANET adopted TCP/IP as its standard protocol suite, giving birth to the universal language of the modern global internet.

### Core Terminology & Submarine Cables
- **Computer Network**: A digital communications medium allowing distinct nodes to communicate and share data/resources.
- **Node / Host**: Any computing device assigned an IP address (PC, server, smartphone, router, IoT device).
- **Physical Internet Infrastructure**: The internet is not purely virtual; it relies on physical data centers, optical fiber lines, and thousands of kilometers of **Submarine Optical Fiber Cables** laid across ocean beds connecting continents.

### Internet vs. World Wide Web (WWW)
| Metric | Internet | World Wide Web (WWW) |
| :--- | :--- | :--- |
| **Definition** | The underlying global physical infrastructure and transport system. | An application/service operating *on top* of the internet infrastructure. |
| **Invention** | 1969 (ARPANET) / 1983 (TCP/IP). | 1991 by Sir Tim Berners-Lee. |
| **Core Components** | Cables, routers, switches, IP addresses, TCP/UDP. | HTML (structure), HTTP (protocol), URL (location). |

### Client-Server Architecture
- **Client**: Any software/hardware initiating requests (browser, mobile app, CLI terminal via ).
- **Server**: Software process listening on a specific IP and port, processing incoming client requests, and returning responses.
- Single modern servers can efficiently process thousands or millions of concurrent requests.

### Types of Networks
- **PAN (Personal Area Network)**: Ultra-short range around a single individual (e.g., Bluetooth connection between phone and wireless earbuds / smartwatch).
- **LAN (Local Area Network)**: Private network spanning a small physical area (home, office, campus). Excellent for high-speed local file/printer sharing.
- **MAN (Metropolitan Area Network)**: Covers a larger geographical region like a city. Used by regional businesses, government networks, and AWS Availability Zone data center interconnects.
- **WAN (Wide Area Network)**: Connects nodes across broad geographic areas, countries, or continents. The global internet is the largest public WAN.

### Network Topologies
- **Bus**: All nodes connected to a single central backbone cable.
- **Ring**: Circular arrangement; data passes sequentially through each node.
- **Star**: All nodes connect to a central hub or switch. Most common topology in modern LANs.
- **Mesh**: Every node connects directly to multiple or all other nodes. Highly resilient with zero single-point-of-failure, but expensive and complex to wire.
- **Tree**: Hierarchical combination of Bus and Star topologies.

---

## Chapter 2: Network Models

### The OSI 7-Layer Model
The Open Systems Interconnection (OSI) conceptual model divides network communication into seven distinct layers, ensuring interoperability between diverse vendors and systems.

| Layer # | Layer Name | Primary Function | Protocol / Data Unit |
| :---: | :--- | :--- | :--- |
| **7** | **Application** | Human-network interaction & application APIs | HTTP, HTTPS, SSH, DNS, FTP (Data) |
| **6** | **Presentation** | Formatting, Data Translation, Compression, Encryption | SSL/TLS, ASCII, JPEG, JSON (Data) |
| **5** | **Session** | Session setup, authentication, authorization, teardown | RPC, NetBIOS, Sockets (Data) |
| **4** | **Transport** | End-to-end process communication, error & flow control | TCP, UDP (Segment / Datagram) |
| **3** | **Network** | Logical addressing & optimal path selection (routing) | IP, ICMP, IPsec (Packet) |
| **2** | **Data Link** | Physical addressing (MAC), framing, hop-to-hop transfer | Ethernet, Wi-Fi, Switches (Frame) |
| **1** | **Physical** | Bit transmission over physical wire/radio medium | Cables, Fiber, NIC, Hubs (Bits) |

#### Memory Mnemonics
- **Top-to-Bottom (7 -> 1)**: *"All People Seem To Need Data Processing"*
- **Bottom-to-Top (1 -> 7)**: *"Please Do Not Tell Stupid People Anything"*

### TCP/IP Model (4/5 Layers)
The practical, implemented model powering the internet simplifies OSI's upper layers:

1. **Application Layer**: Merges OSI Layers 7, 6, and 5 (Application, Presentation, Session).
2. **Transport Layer**: Corresponds to OSI Layer 4 (TCP, UDP).
3. **Internet / Network Layer**: Corresponds to OSI Layer 3 (IP, ICMP).
4. **Data Link Layer**: Corresponds to OSI Layer 2.
5. **Physical Layer**: Corresponds to OSI Layer 1.

### Encapsulation, Decapsulation & PDUs
As data travels down the stack at the sender, each layer wraps incoming data with its own header (**Encapsulation**). At the receiver, headers are stripped off layer by layer (**Decapsulation**).



### Message Delivery Types
- **Unicast (1:1)**: Direct communication between one sender and one specific receiver (e.g., SSH session, web browsing).
- **Broadcast (1:All)**: Sender transmits data to all nodes on the network segment (e.g., ARP requests).
- **Multicast (1:Group)**: Transmission to a specific subset of interested hosts.
- **Anycast (1:Nearest)**: Single IP address assigned to multiple geographically distributed servers. Requests are routed to the topologically nearest server (e.g., Cloudflare DNS , Google DNS ).

---

## Chapter 3: Network Devices & Hardware

### Network Interface Card (NIC) & MAC Address
- **NIC**: Hardware component enabling a host to connect to the network (available as Wired Ethernet or Wireless Wi-Fi adapters).
- **MAC Address (Media Access Control)**: Hardware-embedded, globally unique 12-digit hexadecimal address (48-bit) assigned to every NIC. Used for local Layer 2 communications.
- **Checking MAC Address**:
  - Linux/macOS: 
  - Windows:  or 

### Hub, Bridge, Switch, and Router
- **Hub (Layer 1)**: Legacy device that blindly re-transmits incoming bits on one port to all other connected ports (pure broadcast, high collision domain).
- **Bridge (Layer 2)**: Connects two local network segments and uses MAC address learning to filter traffic.
- **Switch (Layer 2 / Layer 3)**: Successor to bridges with high port density (8 to 96+ ports). Maintains a MAC address table () to forward frames directly to the target destination port.
- **Router (Layer 3)**: Connects distinct, independent IP networks. Examines destination IP addresses and uses an internal **Routing Table** to forward packets hop-by-hop toward the target network.

### Modem, Gateways, and ISP Tiers
- **Modem (Modulator-Demodulator)**: Converts analog signals from ISP lines into digital signals (s and s) readable by routers and host computers. Modern consumer gateways integrate Router + Switch + Wi-Fi AP + Modem into one device.
- **Gateway / Default Gateway**: The entry and exit router IP of a local network leading toward the external internet.
- **ISP Tiers**:
  - **Tier 1**: Global telecom giants (e.g., Tata Communications, AT&T, NTT) owning vast ocean cables and international backbones.
  - **Tier 2**: Regional providers (e.g., Jio, Airtel, Vodafone) purchasing wholesale bandwidth from Tier 1 ISPs.
  - **Tier 3**: Local ISPs distributing connectivity to end-user homes and small businesses.

### Firewalls & Host-to-Host Communication
- **Network Firewall**: Dedicated hardware appliance inspecting and filtering traffic entering or leaving network perimeters.
- **Host-Based Firewall**: Software running directly on host operating systems (e.g., , ).
- **Complete Addressing Matrix**:
  - **Layer 2 (Local Link)**: MAC Address
  - **Layer 3 (Network Routing)**: IP Address
  - **Layer 4 (Process Mapping)**: Port Number

---

## Chapter 4: Network Layer, IP Addressing & Subnetting

### IPv4 vs. IPv6
- **IPv4**: 32-bit address split into 4 octets separated by dots (). Total space: ~.3 	imes 10^9$ addresses (^{32}$).
- **IPv6**: 128-bit address split into 8 hexadecimal blocks separated by colons (). Total space: ~.4 	imes 10^{38}$ addresses (^{128}$). Built-in security, no NAT required.

### Private vs. Public vs. Loopback IP Addresses
- **Loopback Address**:  (), routes traffic back to the local device internally without hitting the external network.
- **Private IP Ranges (RFC 1918)**: Reserved for internal local networks; non-routable over the public internet.
  - **Class A**:  to  (~16 Million hosts)
  - **Class B**:  to  (~1 Million hosts)
  - **Class C**:  to  (~65,000 hosts)
- **Public IP**: Globally unique IP routable across the public internet, managed by Regional Internet Registries (RIRs like ARIN, APNIC, RIPE).

### Static vs. Dynamic IP (DHCP)
- **Dynamic IP**: Assigned automatically by a **DHCP** (Dynamic Host Configuration Protocol) server. IPs can change upon lease renewal/reconnection.
- **Static IP**: Fixed IP configured manually. Mandatory for public servers, databases, DNS resolvers, and default gateways.

### Subnetting: Classful vs. Classless (CIDR)
Subnetting is the logical division of a large physical IP network into smaller, isolated subnetworks to improve security and performance.

#### CIDR Notation (Classless Inter-Domain Routing)
CIDR replaces rigid Class A/B/C networks with prefix notation (), specifying how many bits are allocated for the Network ID:

11	ext{Usable Hosts} = 2^{(32 - N)} - 211

*(Subtracting 2 for Network Address and Broadcast Address).*

| CIDR Prefix | Subnet Mask | Total IPs | Usable Hosts | Common Usage |
| :---: | :--- | :---: | :---: | :--- |
|  |  | 256 | 254 | Standard LAN / AWS Subnet |
|  |  | 128 | 126 | Medium Subnet |
|  |  | 64 | 62 | Small Subnet |
|  |  | 16 | 14 | Small microservice group |
|  |  | 1 | 1 | Single host / Security Rule |

### Anatomy of an IP Packet
An IPv4 header requires a minimum of **20 bytes** (up to 60 bytes with options).

Key Header Fields:
- **Version**: 4 (IPv4) or 6 (IPv6).
- **TTL (Time to Live)**: Hop counter decremented by each router. Prevents packets from circulating indefinitely; packet is dropped when TTL reaches 0.
- **Protocol**: Identifies Layer 4 payload ( for TCP,  for UDP,  for ICMP).
- **Source & Destination IP Addresses**: 32-bit IPv4 addresses for sender and receiver.
- **MTU (Maximum Transmission Unit)**: Maximum size of a packet on Ethernet (typically **1500 bytes**). Packets exceeding MTU undergo IP fragmentation.

### Network Address Translation (NAT) & Port Forwarding
NAT allows multiple devices on a private network to share a single public IP address when accessing the external internet, conserving IPv4 space.

- **PAT (Port Address Translation / NAT Overload)**: Router modifies outgoing IP packets, replacing internal Private IP + Private Port with its Public IP + dynamic external port. Maintains a **NAT Translation Table** to route returning packets back to the correct private host.
- **Port Forwarding**: Rule on a gateway forwarding incoming external traffic on a specific public port to a specific internal private IP and port.

### ICMP, Ping, and Traceroute
- **ICMP (Internet Control Message Protocol)**: Layer 3 operational/diagnostic protocol.
- **Ping**: Sends ICMP  packets to a target IP and measures round-trip time ().
- **Traceroute** ( / ): Discovers the full router path to a destination by sending packets with incrementally increasing TTL values (, 2, 3 \dots$) and listening for ICMP  responses.

---

## Chapter 5: Transport Layer (TCP & UDP)

### Port Numbers & Multiplexing
Port numbers (16-bit, values  to ) identify specific application processes running on a host.

- **Well-Known Ports ()**: Reserved for system services (FTP: , SSH: , SMTP: , DNS: , HTTP: , NTP: , HTTPS: ).
- **Registered Ports ()**: Used by database systems and applications (MySQL: , PostgreSQL: , Redis: , MongoDB: ).
- **Dynamic / Ephemeral Ports ()**: Assigned dynamically by OS for client-side outgoing connections.
- **Multiplexing / Demultiplexing**: Combining multiple application data streams into a single network stream at the sender, and separating them back by port numbers at the receiver.

### User Datagram Protocol (UDP)
- **Characteristics**: Connectionless, stateless, low overhead (8-byte header), no handshake, no delivery guarantees, no retransmission, no flow/congestion control.
- **Primary Use Cases**: High-speed, real-time streaming, online gaming, VoIP, DNS queries, WebRTC.

### Transmission Control Protocol (TCP)
- **Characteristics**: Connection-oriented, stateful, highly reliable, ordered packet delivery, error checking, flow control, and congestion control. Header size: 20–60 bytes.

### TCP 3-Way Handshake & 4-Way Connection Teardown



#### Connection Teardown (4-Way Handshake)
1. Sender sends .
2. Receiver sends  (enters ).
3. Receiver sends its own .
4. Sender sends final  (enters  for  	imes 	ext{MSL} pprox 4	ext{ mins}$ to flush lingering packets).

### Flow Control (Sliding Window) & Congestion Control
- **Flow Control**: Protects the *receiver* from being overwhelmed. Receiver advertises its available buffer space (**Receiver Window / RWIN**). Sender uses a **Sliding Window Protocol** to transmit up to RWIN bytes before pausing for acknowledgments.
- **Congestion Control**: Protects the *intermediate network/routers* from saturation.
  - **TCP Slow Start**: Begins conservatively with Congestion Window $	ext{CWND} = 1 	ext{ MSS}$ (460	ext{ bytes}$) and doubles CWND exponentially every round trip.
  - **Congestion Avoidance**: Once CWND hits  (Slow Start Threshold), growth shifts from exponential to linear ($+1 	ext{ MSS}$ per RTT).
  - **ECN (Explicit Congestion Notification)**: Routers mark IP headers when buffers near capacity, prompting TCP senders to slow down before packet loss occurs.

### Head-of-Line (HoL) Blocking
If a single packet in a TCP stream is dropped, all subsequent in-order packets are held in receiver memory buffers until the missing packet is retransmitted and acknowledged. This introduces latency bottlenecks for multi-stream applications over a single TCP connection.

---

## Chapter 6: Application Layer Protocols

### DNS (Domain Name System) & Record Types
DNS operates over UDP (Port 53) to translate human-readable domain names into machine-routable IP addresses.



#### Essential DNS Record Types
- **A Record**: Maps domain name to an IPv4 address ().
- **AAAA Record**: Maps domain name to an IPv6 address.
- **CNAME (Canonical Name)**: Alias pointing one domain name to another domain name ().
- **MX (Mail Exchange)**: Points to email servers handling mail for the domain.
- **TXT Record**: Holds arbitrary text data (used for SPF, DKIM, and domain ownership verification).
- **NS (Name Server)**: Specifies authoritative DNS servers for the zone.
- **PTR (Pointer)**: Reverse DNS lookup (maps IP address to domain name).

### SSL / TLS & Digital Certificates
- **TLS (Transport Layer Security)**: Modern successor to broken/deprecated SSL. Provides Encryption, Authentication, and Data Integrity for HTTPS.
- **TLS Handshake**: Uses Asymmetric Encryption (RSA, ECDHE) for secure key exchange, establishing a shared symmetric session key used for high-speed data encryption.
- **Forward Secrecy**: Ephemeral key exchange algorithms (like ECDHE) ensure past encrypted communications cannot be decrypted even if the server's private key is compromised in the future.

### Server Name Indication (SNI)
SNI extends the TLS handshake by adding the target hostname in the initial  message. This allows a single server/IP address to host multiple distinct TLS certificates for different domains.

### HTTP Evolution: HTTP/1.1, HTTP/2, and HTTP/3 (QUIC)



| Feature | HTTP/1.1 | HTTP/2 | HTTP/3 |
| :--- | :--- | :--- | :--- |
| **Transport Protocol** | TCP | TCP | **QUIC (UDP)** |
| **Format** | Plain Text | Binary Frames | Binary Frames |
| **Multiplexing** | No (Sequential / HoL) | Yes (Single TCP stream) | **Yes (Independent streams)** |
| **Header Compression** | None | HPACK | **QPACK** |
| **HoL Blocking** | Severe (HTTP level) | Partial (TCP level) | **Eliminated completely** |
| **Connection Migration** | No | No | **Yes (Survives IP changes)** |

### WebSockets & Real-Time Communication
WebSockets provide full-duplex, persistent, bidirectional communication between client and server over a single TCP connection.

- **Handshake**: Begins as a standard HTTP/1.1 request containing headers  and . Server responds with .
- **API (JavaScript)**:
  

---

## Chapter 7: Proxies & Load Balancers

### Forward Proxy vs. Reverse Proxy



- **Forward Proxy**: Sits in front of clients. Protects client identity (anonymity), enforces corporate content filtering, caches outbound requests, and logs client activity.
- **Reverse Proxy**: Sits in front of servers. Masks server infrastructure, performs SSL/TLS termination, provides HTTP caching, acts as API Gateway (path-based routing), and distributes traffic.

### Layer 4 (L4) vs. Layer 7 (L7) Load Balancing

| Feature | Layer 4 (L4) Load Balancer | Layer 7 (L7) Load Balancer |
| :--- | :--- | :--- |
| **OSI Operating Layer** | Transport Layer (IP + Port) | Application Layer (HTTP/HTTPS/Headers) |
| **Inspection Depth** | High-level (Packet headers only) | Deep (HTTP URLs, Cookies, Headers, Body) |
| **Performance / Speed** | Ultra-fast, lightweight, low latency | Higher CPU overhead (Parses full payload) |
| **Routing Capability** | IP & Port based routing | Smart URL pathing (, ), Header rules |
| **SSL Termination** | Passes encrypted TCP through | Terminates TLS, decrypts & inspects payload |

---

## Chapter 8: Applied Networking for DevOps & AWS Cloud

### SSH Remote Management & Agent Forwarding
- **SSH (Secure Shell)**: Operates on Port 22. Key-based authentication uses an asymmetric pair: Public Key stored in remote server's , Private Key kept strictly secure in local .
- **SSH Agent Forwarding ()**: Allows authenticating through a Bastion host to private internal servers without copying private keys to intermediate jump hosts.

### AWS VPC, Regions, and Availability Zones
- **AWS Region**: Isolated geographical location worldwide (e.g.,  Mumbai) containing multiple Availability Zones.
- **Availability Zone (AZ)**: One or more physically distinct data centers within a region with independent power and network infrastructure, linked via low-latency fiber.
- **VPC (Virtual Private Cloud)**: Logically isolated virtual network dedicated to an AWS account within a single region. Spans across multiple AZs.

### Public & Private Subnets
- **Public Subnet**: Subnet whose route table directs default outbound traffic () to an **Internet Gateway (IGW)**. EC2 instances receive Public IPs.
- **Private Subnet**: Subnet with no direct route to an IGW. Instances receive only Private IPs and cannot be directly accessed from the internet.

### Internet Gateways (IGW) & NAT Gateways
- **Internet Gateway (IGW)**: Dual-purpose VPC component providing internet access for public subnets and performing 1:1 NAT for public IP instances.
- **NAT Gateway**: Deployed in a **Public Subnet** with a Static Elastic IP (EIP). Enables private subnet instances to make *outbound-only* connections to the internet (for patch updates, downloads) while preventing external internet hosts from initiating inbound connections.



### Security Groups vs. Network ACLs (NACLs)

| Feature | Security Group (SG) | Network Access Control List (NACL) |
| :--- | :--- | :--- |
| **Operating Level** | Instance / ENI level | Subnet level |
| **Statefulness** | **Stateful** (Inbound approval auto-allows outbound response) | **Stateless** (Inbound & Outbound rules explicitly required) |
| **Rules Allowed** |  rules only (Default deny) |  and  rules (Evaluated in numerical order) |
| **Evaluation** | Evaluates all rules before deciding | Evaluates rules sequentially by rule number |

### AWS Load Balancers (ALB vs. NLB)
- **ALB (Application Load Balancer - Layer 7)**: Ideal for HTTP/HTTPS traffic, microservices, containerized apps (ECS/EKS), path-based routing ( vs ), and host-based routing.
- **NLB (Network Load Balancer - Layer 4)**: Designed for ultra-high performance, extreme low-latency TCP/UDP/TLS traffic, handling millions of requests per second, and static/Elastic IP requirements.

### VPC Peering & AWS Transit Gateway
- **VPC Peering**: Direct network connection between two VPCs via private IPv4/IPv6 addresses. **Non-transitive**: If VPC A peers with VPC B, and VPC B peers with VPC C, VPC A cannot talk to VPC C through VPC B.
- **AWS Transit Gateway**: Centralized regional hub (Star topology) connecting hundreds of VPCs and on-premises networks with transitive routing support.



---

## 🛠️ CLI & Terminal Cheatsheet

### Network Discovery & Diagnostics


### HTTP & Curl Diagnostics
DNS: 0.000000s | Connect: 0.000000s | TTFB: 0.000000s | Total: 0.000280s

### SSH Key Setup & Configuration


---

## 📜 License

Distributed under the MIT License. See  for more information.
