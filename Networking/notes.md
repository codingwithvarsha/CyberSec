### NETWORKING CONCEPTS -- 1

-- This module covers the foundational models used to describe network communication — the **OSI Model** and the **TCP/IP Model**.
-- The OSI Model is Open Source Interconnection model developed by International Organisation for standards (ISO).

## OSI model
-- It describes how communication occurs in a computer network.
-- It consists of 7 layers :
1. Physical layer
2. Datalink layer
3. Network layer
4. Transport layer
5. Session layer
6. Presentation layer
7. Application layer

1. Physical layer : deals with physical connection between devices. It runs based on binary digits like 0,1. Data can be transmitted using electrical, optical or wireless signals. EX - Ethernet cable.
2. Datalink layer : It represents the protocol that enables data transfer between nodes on the same network segment. It means the physical addressing of the transmission. It  focuses on sending data between two nodes on the same network segment.
3. Network layer : It helps in sending data between different network. It is used in logical addressing and routing.It also determines the most optimal path in which these chunks of data could be sent.
4. Transport layer : Helps to enable end-to-end communication.It includs 2 types- TCP(Transmission control protocol) and UDP(User datagram protocol).
5. Session layer : Helps in creating and maintaining the connections. EX - are Network File System (NFS) and Remote Procedure Call (RPC).
6. Presentation layer : It helps in data encoding, compression, and encryption.And also acts as translator for data to and from the application layer.EX - ASCII and Unicode
7. Application layer : This layer provides network services directly to end-user applications. EX- HTTP,FTP,POP3,etc.

## TCP/IP model.
--It is same as the OSI model but it only has 5 layer:
1. Physical layer
2. Link layer 
3. Internet layer
4. Transport layer
5. Application layer - It contains 5,6,7 layers of OSI model

1. Physical layer: Signal transmission.
2. link layer: MAC addressing and same-segment transfer.
3. Internet layer: Routing with IP.
4. Transport layer: TCP,UDP and port numbers.
5. Application layer : interfaces for services like http and dns.

# Notes & Reflections

- OSI is more conceptual; TCP/IP is more practical and implemented.
- Understanding the layers helps in troubleshooting (e.g., is DNS failing due to transport or application layer issues?).
- TryHackMe’s “Intro to Networking” room provided visual scenarios to reinforce layer behavior — especially packet inspection tools like Wireshark.

--------------------------------------------------------------------------------------------------------------

## IP addresses and subnets

An IP address (Internet Protocol address) is a unique identifier assigned to each device connected to a network. It’s like a digital home address that allows devices to send and receive data across the internet or a local network.

-IP address can be categorised into 2 types:
1. IPv4
2. IPv6

-IP address composess of 4 octets which is 32 bits.An octet reprents number between 0-255.
* But 0 and 255 are registerd for the network and broadcast address. Ex- 192.168.1.0 is the network address while 192.168.1.255 is the broadcast address.
* There are only 4 billion ipv4 address.
* if we do maths it will be 2^32.
* subnet : 255.255.255.0 can be written as /24.

-IP address are of two types:

1. public
2. private

-RFC 1918 defines the following three ranges of private IP addresses:

* 10.0.0.0 - 10.255.255.255 (10/8)
* 172.16.0.0 - 172.31.255.255 (172.16/12)
* 192.168.0.0 - 192.168.255.255 (192.168/16)

-How IP Addresses Work
* Routing: Routers use IP addresses to forward packets to the correct destination.
* Identification: Each packet includes source and destination IPs to ensure proper delivery.
* NAT (Network Address Translation): Converts private IPs to a public IP for internet access.

--------------------------------------------------------------------------------------------------------------

### TCP and UDP

The ip address are transferred using transport protocols : TCP and UDP

# TCP
 - Transmission Control Protocol.
 - it is a connect-oriented protocol.
 - It uses various mechanisms to ensure reliable data delivery sent by the different processes on the networked hosts.
 - Needs to establish TCP connection.
 - In TCP, each data byte has a sequence number, helping track loss or duplication. The receiver sends back an acknowledgement number for the last byte received.
 - TCP connection is established using the Three way handshake:
      - SYN: Client sends initial sequence number.  
      - SYN-ACK: Server responds with its own sequence number.  
      - ACK: Client confirms, and the connection is established.  

# UDP
 - User Datagram Protocol.
 - It is a connectionless protocol operates at layer 4(transport layer).
 - It doesnt provide any info if the packet is deliverd or not.
 - Real world example - a mail service with no delivery confirmation.
 - It has better speed. 
 - Doesnot need to establish connections.
--------------------------------------------------------------------------------------------------------------
### TELNET

Objective: Use Telnet to connect with servers on different TCP ports and observe service responses.

# Steps & Observations:

* Echo Server (Port 7):
    Reflected every sent message back.
    Used telnet MACHINE_IP 7
    Closed with CTRL + ], then quit.

* Daytime Server (Port 13):
    Returned current UTC time, then auto-closed.
    Command: telnet MACHINE_IP 13

* HTTP Server (Port 80):
    Issued GET / HTTP/1.1 followed by Host: telnet.thm and a blank line.
    Received HTML response with status HTTP/1.1 200 OK.

Note: Echo and daytime services are deprecated due to security risks—enabled here purely for learning. Telnet highlights how raw communication works across TCP ports.
 