# Room: Cryptography Basics (TryHackMe)

**Date:** 4 Oct 2025  
**Path:** Cyber Security 101  
**Goal:** Learn foundational cryptography concepts: why cryptography matters, how plaintext → ciphertext works, historical ciphers, symmetric/asymmetric encryption, and basic math operations used in crypto.

## 1. Key Concepts Learned

* **Importance of Cryptography**:

  * Cryptography ensures confidentiality, integrity, and authenticity of data in the presence of adversaries.  
  * Used widely: HTTPS, SSH, file integrity checks (hashes), and compliance standards like PCI DSS for card data.  

* **Plaintext → Ciphertext**:

  * **Plaintext** is readable data; **ciphertext** is the encrypted output after applying a cipher and a key.  
  * A **cipher** is the algorithm; a **key** is the secret input that makes encryption/decryption unique.  

* **Historical Ciphers**:

  * **Caesar Cipher**: shifts letters by a fixed amount (e.g., shift 3: A→D). Insecure today due to small keyspace.  
  * Other historical examples: **Vigenère**, **Enigma**, **One-Time Pad**.

* **Types of Encryption**:

  * **Symmetric Encryption**: same key for encryption and decryption (e.g., DES, 3DES, AES).  
    * DES: 56-bit key (broken in practice).  
    * 3DES: applied DES three times; now deprecated in many contexts.  
    * AES: modern standard (128/192/256-bit keys).
  * **Asymmetric Encryption**: key pairs (public/private) where data encrypted with the public key is decrypted with the private key (e.g., RSA, Diffie-Hellman, ECC).  
    * Asymmetric is slower and uses larger keys; ECC provides similar security with shorter keys.

* **Basic Math**:

  * **XOR (⊕)**: returns 1 when bits differ, 0 when same — heavily used in symmetric ciphers and stream ciphers.  
  * **Modulo arithmetic**: fundamental to algorithms like RSA and Diffie-Hellman.

## 2. Commands / Tools Practiced

* No specific CLI tools required; room focuses on concepts and small practical exercises (cipher examples, brute-force Caesar).  
* You may use Python (or Bash) to script Caesar cipher brute force and XOR examples locally.
* Recommended follow-ups: practice with `openssl` commands for symmetric/asymmetric operations and `python` scripts for demonstrating XOR/modulo.

## 3. Takeaways

* Cryptography underpins secure communications — it’s everywhere (web, SSH, email).  
* Symmetric encryption is efficient for bulk data; asymmetric encryption solves secure key exchange and authentication problems.  
* Historical ciphers are educational but insecure by modern standards; modern crypto relies on strong math assumptions and sufficiently large key sizes.  
* Understand basic math primitives (XOR, modulo) to follow how crypto algorithms operate.

## 4. Next Steps

* Continue to **Public Key Cryptography Basics** and **Hashing Basics** rooms.  
* Practice implementing simple ciphers in Python (Caesar, XOR stream) and then use `openssl` to encrypt/decrypt files with AES.  
* Learn about real-world crypto: TLS handshakes, certificate authorities, and key management best practices.
