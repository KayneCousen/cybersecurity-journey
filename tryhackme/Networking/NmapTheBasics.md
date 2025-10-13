# Room: Nmap: The Basics (TryHackMe)

**Date:** 4 Oct 2025  
**Path:** Cyber Security 101  
**Goal:** Learn how to discover live hosts, scan ports and services, detect OS and versions, and optimize scan performance using Nmap.  

## 1. Key Concepts Learned

* **Host Discovery (`-sn`)**:  

  * Used to find live hosts on a network without scanning ports.  
  * On **local networks**, Nmap sends ARP requests and detects MAC addresses.  
  * On **remote networks**, Nmap sends ICMP echo requests and TCP/UDP probes.  
  * Example: `sudo nmap -sn 192.168.1.0/24`.  

* **Target Specification**:  

  * Define targets using IP ranges (`192.168.0.1-10`), subnets (`192.168.0.0/24`), or hostnames (`example.thm`).  
  * Use `-sL` to list targets without scanning.  

* **Port Scanning Techniques**:  

  * **TCP Connect Scan (`-sT`)**: completes a full handshake (less stealthy).  
  * **SYN Scan (`-sS`)**: sends SYN packets only (stealthier, requires root).  
  * **UDP Scan (`-sU`)**: sends UDP packets to discover open UDP ports.  

* **Service and Version Detection (`-sV`)**:  

  * Identifies running services and their versions on open ports.  
  * Example: `sudo nmap -sS -sV 192.168.1.5`.  

* **OS Detection (`-O`)**:  

  * Analyzes network responses to infer the target’s operating system.  
  * Often combined with version detection and traceroute using `-A`.  

* **Timing and Performance**:  

  * Adjust scan speed using `-T0` to `-T5` (from paranoid to insane).  
  * Example: `nmap -T4 -sS 192.168.1.5` for faster scans.  

* **Verbosity and Debugging**:  

  * `-v`, `-vv` increase output detail; `-d` adds debugging information.  
  * Helpful for understanding scan progress and troubleshooting.  

* **Output and Reporting**:  

  * Save scans in multiple formats:  
    * `-oN` (normal)  
    * `-oX` (XML)  
    * `-oG` (grepable)  
    * `-oA` (all formats).  
  * Example: `nmap -sS -oA myscan 192.168.1.0/24`.  

* **Privilege Importance**:  

  * Running as root allows low-level packet access for accurate results (ARP, SYN, OS detection).  
  * Non-root users are limited to basic connect scans.  

## 2. Commands / Tools Practiced

* `sudo nmap -sn 192.168.66.0/24` — discover live hosts.  
* `nmap -sL 192.168.0.0/24` — list scan targets.  
* `sudo nmap -sS TARGET` — SYN stealth scan.  
* `nmap -sT TARGET` — TCP connect scan (non-root).  
* `sudo nmap -sU TARGET` — UDP scan.  
* `nmap -p22,80,443 TARGET` — scan specific ports.  
* `nmap -p- TARGET` — scan all 65,535 ports.  
* `sudo nmap -sV -O TARGET` — detect services and OS.  
* `nmap -A TARGET` — aggressive all-in-one scan.  
* `nmap -Pn TARGET` — skip host discovery.  
* `nmap -T4 -v TARGET` — faster, more verbose scan.  
* `nmap -sS -oA scan_results TARGET` — save output in all formats.  

## 3. Takeaways

* `-sn` scans are ideal for quick, low-noise host discovery.  
* SYN scans are stealthier and faster but need root privileges.  
* Use `-sV` and `-O` for deeper information about targets.  
* Adjusting timing templates (`-T0`–`-T5`) balances stealth and speed.  
* Saving results with `-oA` is crucial for documentation and automation.  
* Verbose and debug options help understand Nmap behavior and troubleshoot issues.  

## 4. Next Steps

* Combine discovery, service detection, and script scans (`-sC`) for more detailed enumeration.  
* Practice analyzing captured Nmap traffic in Wireshark to understand how scan types appear on the wire.  
* Automate repetitive scans using Bash or Python scripts and parse results with grep or XML tools.  
* Explore advanced features like NSE (Nmap Scripting Engine) and custom script usage.  
