# Room: Networking Core Protocols (TryHackMe)

**Date:** 19 Sept 2025
**Path:** Cyber Security 101
**Goal:** Understand key networking protocols used on the Internet such as DNS, HTTP(S), FTP, and email protocols.

## 1. Key Concepts Learned

* **DNS (Domain Name System)**: Translates domain names into IP addresses.

  * Common record types:

    * **A** → IPv4 address
    * **AAAA** → IPv6 address
    * **CNAME** → Canonical name (alias)
    * **MX** → Mail exchange server
* **WHOIS**: Lookup tool for domain registration details.
* **Domain Registration**: Process of reserving domain names tied to registrars and IPs.
* **HTTP(S)**: Protocols for web communication.

  * Key methods: **GET**, **POST**, **PUT**, **DELETE**.
  * HTTPS adds encryption with TLS/SSL.
* **FTP (File Transfer Protocol)**: Transfers files between client and server (unencrypted by default).
* **SMTP (Simple Mail Transfer Protocol)**: Protocol for sending emails.
* **POP3 (Post Office Protocol v3)**: Downloads emails from the server (removes them from server).
* **IMAP (Internet Message Access Protocol)**: Synchronizes email across multiple devices (keeps copies on server).

## 2. Commands / Tools Practiced

* `nslookup www.example.com` to query DNS records.
* `whois example.com` to view domain registration data.
* Practiced understanding HTTP request methods (GET, POST, etc.).

## 3. Takeaways

* DNS is like the Internet’s phonebook — attackers often target it for redirection or poisoning.
* WHOIS can be used to gather reconnaissance information on domains.
* HTTPS is essential for securing data; HTTP should be avoided in modern networks.
* FTP is outdated and insecure unless wrapped in FTPS/SFTP.
* Understanding email protocols (SMTP, POP3, IMAP) is vital for both sysadmins and penetration testers.

## 4. Next Steps

* Explore DNS enumeration with tools like `dig` and `dnsenum`.
* Capture HTTP/FTP/SMTP traffic in Wireshark to analyze requests.
* Practice sending requests with `curl` to see how HTTP methods work.
* Look deeper into email security (SPF, DKIM, DMARC).
