# Room: Networking Concepts (TryHackMe)

**Date:** 18 Sept 2025
**Path:** Cyber Security 101
**Goal:** Learn the fundamentals of networking, including the OSI model, IP addressing, subnets, and transport protocols.

## 1. Key Concepts Learned

* **OSI Model**: 7 layers (Physical → Application) explaining how data travels across networks.
* **TCP/IP Model**: Simplified 4-layer model mapping to real-world protocols.
* **IP Addresses**:

  * Two types: **Private** (internal networks) and **Public** (Internet-facing).
  * Private ranges: `10.0.0.0 – 10.255.255.255`, `172.16.0.0 – 172.31.255.255`, `192.168.0.0 – 192.168.255.255`.
* **Subnets**: Divide networks into smaller segments to organize and manage IPs.
* **Protocols**:

  * **TCP**: Reliable, connection-oriented, ensures delivery (e.g., HTTP, SSH).
  * **UDP**: Unreliable, faster, connectionless (e.g., DNS, streaming).
* **Encapsulation**: Wrapping data in headers as it moves down the layers (application → transport → network → data link → physical).

## 2. Commands / Tools Practiced

* **Telnet** used to test connections to ports/services.
* Practiced identifying private vs. public IPs in exercises.
* Worked with subnet examples to understand how hosts fit into ranges.

## 3. Takeaways

* Networking is built in **layers**, and each has a clear role in moving data.
* Understanding private vs. public IPs is critical for both networking and security.
* TCP and UDP have different strengths, and attackers/defenders must know when each is in use.
* Encapsulation explains why packets carry multiple headers (IP, TCP/UDP, data).

## 4. Next Steps

* Dive deeper into practical networking tools (Wireshark, tcpdump).
* Learn subnetting calculations in more detail (CIDR notation).
* Practice identifying services using `nmap` instead of just Telnet.
