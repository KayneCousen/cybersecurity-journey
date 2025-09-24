# Room: Networking Essentials (TryHackMe)

**Date:** 18 Sept 2025
**Path:** Cyber Security 101
**Goal:** Learn core networking protocols and tools such as DHCP, ARP, ICMP, and NAT.

## 1. Key Concepts Learned

* **DHCP (Dynamic Host Configuration Protocol)**: Automates IP configuration for devices.

  * Process: **DORA** → Discover, Offer, Request, Acknowledge.
* **ARP (Address Resolution Protocol)**: Maps IP addresses (Layer 3) to MAC addresses (Layer 2).
* **ICMP (Internet Control Message Protocol)**: Used for troubleshooting and diagnostics.

  * Common tools: `ping`, `traceroute`/`tracert`.
* **NAT (Network Address Translation)**: Maps private IP addresses to a public IP for Internet access.

## 2. Commands / Tools Practiced

* `ping [host]` to test connectivity.
* `traceroute [host]` (Linux) / `tracert [host]` (Windows) to trace network paths.
* Observed DHCP lease process (DORA sequence).
* Understood ARP operation through examples.

## 3. Takeaways

* DHCP makes network setup seamless — without it, every host would need manual configuration.
* ARP is essential for communication inside a LAN; attackers sometimes exploit it (e.g., ARP spoofing).
* ICMP is a simple but powerful tool for diagnosing network issues.
* NAT allows many private devices to share a single public IP, a key part of modern networking.

## 4. Next Steps

* Experiment with `arp -a` to view ARP tables on Windows/Linux.
* Capture DHCP and ARP traffic in Wireshark to visualize how they work.
* Explore security considerations of NAT and ARP (e.g., spoofing attacks, port forwarding).
