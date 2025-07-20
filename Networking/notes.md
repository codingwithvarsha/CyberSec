## NETWORKING CONCEPTS -- 1

-- This module covers the foundational models used to describe network communication — the **OSI Model** and the **TCP/IP Model**.
-- The OSI Model is Open Source Interconnection model developed by International Organisation for standards (ISO).
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

--next the TCP/IP model.
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

###  Notes & Reflections

- OSI is more conceptual; TCP/IP is more practical and implemented.
- Understanding the layers helps in troubleshooting (e.g., is DNS failing due to transport or application layer issues?).
- TryHackMe’s “Intro to Networking” room provided visual scenarios to reinforce layer behavior — especially packet inspection tools like Wireshark.

