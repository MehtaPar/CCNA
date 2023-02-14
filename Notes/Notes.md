# **CCNA 200-301 Notes:**


LAN = Local Area Network
WAN = Wide Area Network (When 2 seperate LANs are connected)
---

## OSI Model:

### Layers:
7. Application | Data
6. Presentation | Data
5. Session | Data
4. Transport | TCP/UDP, Port | Segments
3. Network | IP Address | Packets
2. Data-Link | Ethernet MAC Address | Frames
1. Physical | Signals, Binary | Bits
--- 

## TCP/IP Model:
4. Application | Data
3. Transport | Segments
2. Internet | Packets
1. Network Access | Frames and Bits
--- 

## Encapsulation/Decapsulation
Encapsulation will go down from layers 7 to 1
Deencapsulation will go up from layers 1 to 7
---

## Cisco IOS Config Process
1. IOS operating system image is stored in Flash
2. The startup config is stored in NVRAM
3. Running config is stored in RAM (Loaded into RAM from the startup config when the device boots up)
---

## TCP (Transport Control Protocol) - Connection oriented Protocol
- Ensures that all packets are processed in correct order
- reliable traffic
- receiving host sends aknowledgements back to sender
- lost segments are resent
- TCP performs flow Control

### TCP Three-Way Handshake:
1: Sender sends a SYN to receiver
2: Receiver will send SYN-ACK to sender
3: Sender sends a ACK to receiver
---

## UDP (User Datagram Protocol)
- Sends traffic for best effort
- is not connectio oriented, no handshake connection established
- does not carry out sequencing to ensure segments are in correct order
- not reliable, no aknowledgement between sender and receiver
- no flow control
- if error detection and recovery is required, it is up to the upper layers to provide it
---





























