# Room: Wireshark: The Basics (TryHackMe)

**Date:** 20 Sept 2025
**Path:** Cyber Security 101
**Goal:** Learn the fundamentals of using Wireshark to capture, inspect, and filter network traffic.

## 1. Key Concepts Learned

* **Tool Overview**:

  * Wireshark is a packet capture and analysis tool widely used in networking and cybersecurity.
  * Displays packets in real time and allows dissection of protocols at each OSI layer.
* **Packet Dissection**:

  * Captured packets can be expanded into sections (Ethernet, IP, TCP/UDP, Data).
  * Helps visualize encapsulation and how data moves across layers.
* **Packet Navigation**:

  * Each capture consists of many packets — navigation tools make it possible to follow streams or jump between related packets.
* **Packet Filtering**:

  * Display filters allow narrowing results (e.g., `ip.addr == 192.168.1.1`, `tcp.port == 80`).
  * Capture filters (applied before capturing) vs Display filters (applied after capture).

## 2. Commands / Tools Practiced

* Applied display filters to isolate packets by IP, protocol, or port.
* Used “Follow TCP Stream” to reconstruct conversations.
* Navigated through different protocol layers in the packet dissection pane.

## 3. Takeaways

* Wireshark is essential for both defensive and offensive security work.
* Dissecting packets shows exactly how protocols behave — making concepts like encapsulation tangible.
* Filtering is the key skill to avoid drowning in packet noise.

## 4. Next Steps

* Practice writing advanced display filters (logical operators, multiple conditions).
* Capture traffic for specific protocols (HTTP, DNS, ICMP) and analyze in detail.
* Explore Wireshark profiles to customize layouts for different investigations.
