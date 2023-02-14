# **CCNA 200-301 Notes:**
## *Notes written by Param Mehta*


LAN = Local Area Network
WAN = Wide Area Network (When 2 seperate LANs are connected)

## OSI Model:

### Layers:
- Layer 7: Application | Data
- Layer 6: Presentation | Data
- Layer 5: Session | Data
- Layer 4: Transport | TCP/UDP, Port | Segments
- Layer 3: Network | IP Address | Packets
- Layer 2: Data-Link | Ethernet MAC Address | Frames
- Layer 1: Physical | Signals, Binary | Bits  

## TCP/IP Model:
- Layer 4: Application | Data
- Layer 3: Transport | Segments
- Layer 2: Internet | Packets
- Layer 1: Network Access | Frames and Bits  

## Encapsulation/Decapsulation
Encapsulation will go down from layers 7 to 1
Deencapsulation will go up from layers 1 to 7

## Cisco IOS Config Process
1. IOS operating system image is stored in Flash
2. The startup config is stored in NVRAM
3. Running config is stored in RAM (Loaded into RAM from the startup config when the device boots up)

## TCP (Transport Control Protocol) - Connection oriented Protocol
- Ensures that all packets are processed in correct order
- reliable traffic
- receiving host sends aknowledgements back to sender
- lost segments are resent
- TCP performs flow Control

### TCP Three-Way Handshake:
1. Sender sends a SYN to receiver
2. Receiver will send SYN-ACK to sender
3. Sender sends a ACK to receiver

## UDP (User Datagram Protocol)
- Sends traffic for best effort
- is not connectio oriented, no handshake connection established
- does not carry out sequencing to ensure segments are in correct order
- not reliable, no aknowledgement between sender and receiver
- no flow control
- if error detection and recovery is required, it is up to the upper layers to provide it

## Unicast, Broadcast, and Multicast Traffic:
- Unicast traffic goes to a single host
- Broadcast traffic is to all hosts on the subnet 
- Multicast traffic is to multiple interested hosts

### Broadcast v.s. Multicast
- Broadcast is sent out to all hosts no matter if the host had requested it 
- Multicast is sent out to multiple hosts that have requested that same data

## IPv4 Address
- a ipv4 address is 32 bits long
- written as 4 'octets' in dotted decimal format
- example: *192.168.10.15*
- each octet is 8 bits long (4 x 8 = 32)

## DHCP Server
- Automatically configures host ip addresses

## Public/Private IPv4 Address Range:

### Class A IP Addresses: (1.0.0.0 to 127.0.0.0/8)
- Assigned to networks with a very large number of hosts
- high-order (first) bit in a class A address is always set to zero! (01111111)
- The default subnet mask is /8
- valid network addresses range from 1.0.0.0 to 127.0.0.0/8

- Public IP Range: 1.0.0.0 to 127.0.0.0
- Private IP Range: 10.0.0.0 to 10.255.255.255

### Class B IP Addresses: (128.0.0.0 to 191.255.0.0/16)
- Class B are assigned to medium-sized to large-sized networks
- two high-order bits in class B are always set to binary 1 0. (10111111)
- default subnet mask is /16
- valid network addresses range from 128.0.0.0 to 191.255.0.0/16

- Public IP Range: 128.0.0.0 to 191.255.0.0
- Private IP Range: 172.16.0.0 to 172.31.255.255

### Class C IP Addresses: (192.0.0.0 to 223.255.255.0/24)
- Class C are assigned to small networks
- 3 high-order bits in class C address are always set to binary 1 1 0. (11011111)
- default subnet mask is /24
- valid network addresses range from 128.0.0.0 to 191.255.0.0/16

- Public IP Range: 192.0.0.0 to 223.255.255.0
- Private IP Range: 192.168.0.0 to 192.168.255.255 

### Class D IP Addresses: (224.0.0.0 to 239.255.255.255)
- Reserved for IP Multicast Addresses
- 4 high-order bits are always set to binary 1 1 1 0 (11101111)
- not allocated to hosts and no default subnet mask

### Class E IP Addresses: (240.0.0.0 to 255.255.255.255)
- Reserved for future use and experimental
- high-order bits are set to 1 1 1 1. (11110000) 
- not allocated to hosts and no default subnet mask
- 255.255.255.255 is the broadcast address for "this network"

### Private IP Address Ranges:
- 10.0.0.0/8 (Class A)
- 172.16.0.0/12 (Class B)
- 192.168.0.0/16 (Class C)

## Data-Link Layer (L2)
- Ethernet Layer, Frames
- Ethernet Header: Preamble (8 bytes) | Dest. Address (6 bytes) | Source Address (6 bytes) | Length/Ethertype (46-1500 bytes) | FCS (4 Bytes) 
- FCS = Frame Check Sequence
- MAC address is 48-bit hexadecimal
- first 24 bits of mac is OUI (Organizationally Unique Identifier) - unique to manufacturer of ethernet port
- last 24 bits is vendor assigned
- burned in MAC address on every NIC port in the world is globally unique!

Commands to find MAC address:
- ipconfig /all = to find the MAC address on Windows OS
- ifconfig = to find the MAC address on Linux OS
- show interface = to find MAC address on Cisco device

## Straight-Through vs Crossover UTP Cables
- Like devices will require crossover cables (rotuer to router, swithc to switch, pc to pc)
- Unlike devices will require straight-through cables
- most modern devices will have Auto-MDIX enabled, which does not require the use of crossover cable since the device can detect the cable and convert it accordingly

## Fiber Optic Cables
- used for longer distances
- single mode, supports higher badnwidth and longer distance, more expensive 
- multi mode, cheaper, shorter distance

## PoE (Power over Ethernet)
- Ethernet switch that sends power through the network cable, doesn't require a power supply for end devices

## Hubs and Switches
### Hubs
- operate in half-duplex mode
- cannot send and receive data at same time, only one at a time
- all hosts share the same collision domain, only one device can transmit at a time
- Hosts use CSMA/CD to detect collisions and resend
- operate in layer 1, they are not MAC address aware!

### Switches
- operate in either full-duplex or half-duplex mode
- typically set up in full-duplex
- attached hosts can send and receive data at same time
- all hosts have their own dedicated collision domain
- collision detection is not required
- operate at layer 2, are MAC address aware!
- MAC address table to keep a cached table of hosts MACs with corresponding ports
- more ports available than routers

## Routers
- Ability to route traffic between different IP subnets on a network
- required to send traffic from one subnet to another
- operate at layer 3
- less ports available than switches

## Layer 3 Switch
- Operates on the layer 3 and route traffic between IP Subnets like a router

## Domain Name System (DNS)
- resolves a fully qualified domain name (FQDN) such as www.cisco.com to an IP Address
- hosts will send their DNS queries to this server
- Enterprises will typically have an internal DNS server which can resolve the ip addresses of the internal hosts
- if the internal DNS server cannot resolve a query, it will forward the request out to the public DNS servers on the internet
- DNS requests are sent using UDP port 53 (and can fail over to TCP)

### DNS Commands:
DNS Client:
- `ip domain-lookup`
- `ip name-server 172.23.4.1`
- `ip domain-name flackboxA.lab` (primary domain name)
- `ip domain-list flackboxB.lab` (additional DNS suffixes to search)

Additional DNS Server Commands:
- `ip dns server`
- `ip host LinuxA 172.23.4.2`

## Address Resolution Protocol (ARP)
- ARP is used to map the IP Address to MAC address
- sender will send ARP request will flood out all ports except ingress, destination host will reply with MAC address, sender will send the frames successfully, destination host will reply with aknowledgement back to sender (LAN envrionment)
- sender will send ARP request to router, router will reply, sender will reply with sending the frames, destination host will reply with aknowledgement back to sender (WAN environment)
-  `show arp` (view the arp table)
- `clear arp-cache` (clears the cached arp table)

## Cisco Troubleshotting Methodology
1. Define the Problem
2. Gather Information
3. Analyze Information
4. Eliminate Potential Causes
5. Propose Hypothesis
6. Test Hypothesis
7. Solve Problem and Document Solution










