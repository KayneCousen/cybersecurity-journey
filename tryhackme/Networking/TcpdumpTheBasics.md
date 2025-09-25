# Room: Tcpdump: The Basics (TryHackMe)

**Date:** 20 Sept 2025
**Path:** Cyber Security 101
**Goal:** Learn how to capture, filter, and display packets using the `tcpdump` command-line tool.

## 1. Key Concepts Learned

* **Basic Packet Capture**:

  * `tcpdump` is a command-line tool for capturing network traffic.
  * Captures can be written to `.pcap` files and analyzed later in Wireshark.
* **Filtering Expressions**:

  * Capture only what’s needed using expressions like host, port, and protocol.
  * Example: `tcpdump host 10.10.10.10` or `tcpdump port 80`.
* **Advanced Filtering**:

  * Combine filters with logical operators (`and`, `or`, `not`).
  * Example: `tcpdump tcp and port 443 and not host 192.168.1.1`.
* **Displaying Packets**:

  * Options for how packets are displayed:

    * `-n` avoids DNS resolution.
    * `-A` shows ASCII.
    * `-X` shows both hex and ASCII.
    * `-c` limits the number of packets captured.

## 2. Commands / Tools Practiced

* `tcpdump -i any` to capture traffic on all interfaces.
* `tcpdump -w capture.pcap` to save packets for later analysis.
* Used filters: `host`, `port`, `src`, `dst`.
* Played with display options like `-A`, `-XX`, and `-q`.

## 3. Takeaways

* `tcpdump` is lightweight and powerful, especially useful on headless servers without GUIs.
* Filtering at the capture stage reduces noise and makes analysis more efficient.
* Understanding display options helps tailor output for quick investigations or detailed analysis.

## 4. Next Steps

* Practice building complex filters for real-world traffic scenarios.
* Use `tcpdump` in combination with Wireshark: capture with tcpdump, analyze with Wireshark.
* Explore advanced flags (`-vvv`, `-s`, `-tttt`) for deeper inspection.
