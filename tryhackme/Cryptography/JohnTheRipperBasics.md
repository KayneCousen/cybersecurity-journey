# Room: John the Ripper: The Basics (TryHackMe)

**Date:** 5 Oct 2025  
**Path:** Cyber Security 101  
**Goal:** Learn how to set up and use John the Ripper to crack different types of password hashes and encrypted files, and how to customize cracking with rules and modes.

## 1. Key Concepts Learned

* **Basic Terms**:

  * **Hash**: fixed-size digest representing input data (passwords).  
  * **Wordlist**: file with candidate passwords used for dictionary attacks.  
  * **Rule**: transformation applied to wordlist entries to generate variants.  
  * **Mask**: pattern-based brute force (e.g., ?l?l?d?d for two letters and two digits).  
  * **Mode**: John supports different cracking modes (single, wordlist, incremental, etc.).

* **Setting Up Your System**:

  * Install John the Ripper (community or jumbo builds) for extended format support.  
  * Prepare wordlists (`rockyou.txt`, custom lists) and ensure proper permissions for hash files.  
  * Use `john --test` to verify build and performance.

* **Cracking Basic Hashes**:

  * Use `john --wordlist=wordlist.txt hashfile` for dictionary attacks.  
  * Identify hash types (John can auto-detect some formats, or use `--format=`).  
  * Use `john --show hashfile` to reveal cracked passwords.

* **Cracking Windows Authentication Hashes**:

  * Work with NTLM/LM hashes extracted from SAM/NTDS dumps.  
  * Use tools like `impacket` or `secretsdump.py` to extract hashes in a lab environment.  
  * John supports NTLM; cracking speeds benefit from GPU-accelerated tools like Hashcat for large-scale work.

* **Cracking /etc/shadow Hashes**:

  * Shadow file contains salted password hashes (bcrypt, SHA-512, etc.).  
  * Use `unshadow` to combine `/etc/passwd` and `/etc/shadow` for offline cracking of local accounts.  
  * Target slow KDFs (bcrypt, Argon2) are intentionally expensive to slow attackers.

* **Single Crack Mode**:

  * `john --single hashfile` uses username-based mangling rules and is effective when password choices relate to username or other fields.  
  * Fast and often successful on weak/default passwords.

* **Custom Rules**:

  * Rules extend dictionary attacks by mangling words (append numbers, capitalization, leet substitutions).  
  * John’s rule syntax allows complex transformations; start with builtin rulesets (e.g., `--rules=single` or `--rules=Wordlist`).

* **Cracking Password-Protected Zip & RAR Files**:

  * John supports many archive formats via jumbo build or through `zip2john`/`rar2john` helpers to extract hash blobs.  
  * Workflow: `zip2john file.zip > zip.hash` then `john --wordlist=rockyou.txt zip.hash`.

* **Cracking SSH Keys with John**:

  * Use `ssh2john` to extract the hash from an encrypted private key, then crack with John.  
  * Modern OpenSSH formats may be slow; prefer targeted wordlists and rules.

## 2. Commands / Tools Practiced

* `john --test` — benchmark John.  
* `john --wordlist=rockyou.txt hashes.txt` — dictionary attack.  
* `john --format=nt --wordlist=rockyou.txt nt_hashes.txt` — specify format.  
* `john --single hashes.txt` — single crack mode.  
* `zip2john secret.zip > zip.hash` and `john zip.hash` — crack ZIP.  
* `ssh2john id_rsa > ssh.hash` and `john ssh.hash` — crack SSH key passphrases.  
* `john --rules --wordlist=wordlist.txt hashes.txt` — apply rules.  
* `john --show hashes.txt` — view cracked passwords.

## 3. Takeaways

* John is a versatile offline password cracking tool with many modes and rule options.  
* Properly salted and slow hash algorithms (bcrypt, Argon2) significantly increase cracking cost.  
* Combining wordlists with rules and masks yields the best results for realistic password cracking.  
* For large-scale or GPU-accelerated cracking, Hashcat often outperforms John, but John remains essential for many formats and workflows.

## 4. Next Steps

* Practice extracting different hash types (SAM/NTDS, /etc/shadow, archives, SSH keys) in a lab environment.  
* Build or curate wordlists tailored to target profiles and practice rule creation.  
* Learn mask attacks and incremental (brute-force) mode for targeted cracking.  
* Explore John jumbo features and integrate with Hashcat for hybrid workflows.  
