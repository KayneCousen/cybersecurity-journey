# Room: Hashing Basics (TryHackMe)

**Date:** 5 Oct 2025  
**Path:** Cyber Security 101  
**Goal:** Learn what hashing is, how hash functions work, secure password storage, recognising hashes, cracking basics, and using hashing for integrity checks.

## 1. Key Concepts Learned

* **Hash Functions**:

  * A hash function maps input data of any size to a fixed-size output (the digest).  
  * Important properties: deterministic, fast to compute, **pre-image resistance**, **second pre-image resistance**, **collision resistance**, and the **avalanche effect** (small input changes drastically change the digest).  
  * Examples: MD5, SHA-1 (deprecated), SHA-256, SHA-3, plus password-specific functions like bcrypt, scrypt, Argon2.

* **Insecure Password Storage for Authentication**:

  * Storing plaintext passwords or reversible encrypted passwords is unsafe.  
  * Unsalted, fast hashes (MD5/SHA1) are vulnerable to rainbow tables and fast GPU cracking.  
  * Reusing the same salt or using weak salts still exposes users to risks.

* **Using Hashing for Secure Password Storage**:

  * Use a unique **salt** per password to defeat rainbow tables.  
  * Use slow, memory-hard functions designed for passwords: **bcrypt**, **scrypt**, **Argon2**, or PBKDF2 with many iterations.  
  * Consider adding a **pepper** (server-side secret) for extra protection.  
  * Store: `user | salt | hashed(password+salt)` and use a secure comparison method to verify.

* **Recognising Password Hashes**:

  * Hash formats often give clues:  
    * MD5: 32 hex chars.  
    * SHA-1: 40 hex chars.  
    * SHA-256: 64 hex chars.  
    * bcrypt: `$2b$12$...` prefix with cost factor.  
    * Argon2: `$argon2id$v=19$m=65536,t=3,p=4$...` style.  
  * Recognising the format helps pick cracking strategies (GPU-friendly vs slow KDFs).

* **Password Cracking**:

  * Attack methods: brute force, dictionary attacks, rule-based mutations, rainbow tables (defeated by salts), and hybrid attacks.  
  * Tools: **hashcat**, **John the Ripper**. GPU acceleration dramatically speeds up cracking for fast hashes.  
  * Defensive controls: enforce strong passwords, rate-limiting, account lockouts, multi-factor authentication, and use of slow KDFs.

* **Hashing for Integrity Checking**:

  * Hashes verify data integrity (e.g., checksums for downloads, file verification).  
  * HMAC (hash-based message authentication code) combines hashing with a secret key to provide integrity + authenticity.  
  * Hashes alone do **not** provide non-repudiation or authentication — pair with signatures (e.g., RSA/ECDSA) when needed.

## 2. Commands / Tools Practiced (or likely to practice)

* `openssl dgst -sha256 file.bin` — compute SHA-256 digest.  
* `python` scripts to demo simple hashes (`hashlib.sha256(b"data").hexdigest()`).  
* `john` / `hashcat` for cracking hashes (use with appropriate wordlists like `rockyou.txt`).  
* `bcrypt`/`argon2` libraries in application languages to hash & verify passwords.  
* `sha256sum` / `md5sum` for quick integrity checks on Unix systems.

## 3. Takeaways

* Hashing is a core primitive for both security and attacks — used for integrity, password storage, and more.  
* Never store plaintext or unsalted fast hashes for passwords; prefer slow, memory-hard KDFs (Argon2/bcrypt/scrypt).  
* Recognising hash formats helps choose the right defensive or offensive approach.  
* Use HMAC when you need keyed integrity/authenticity; use digital signatures when you need non-repudiation.

## 4. Next Steps

* Practice implementing secure password storage in a small web app using Argon2 or bcrypt.  
* Use `hashcat` on intentionally weak hashes in a lab to understand cracking speeds and the impact of salts/cost factors.  
* Learn about password storage best practices: rotation, breach detection, and secure reset flows.  
* Study HMAC vs digital signatures and where each is appropriate in protocols (TLS, JWTs, code signing).  
