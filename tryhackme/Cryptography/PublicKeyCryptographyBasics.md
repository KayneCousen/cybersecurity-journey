# Room: Public Key Cryptography Basics  (TryHackMe)

**Date:** 5 Oct 2025  
**Path:** Cyber Security 101  
**Goal:** Learn how asymmetric cryptography works in practice — RSA, Diffie‑Hellman, digital signatures, certificates, SSH, and tools like PGP/GPG.

## 1. Key Concepts Learned

* **Common Uses of Asymmetric Encryption**  

  * Key exchange (securely establish symmetric keys).  
  * Digital signatures (verify message authenticity and integrity).  
  * Certificate-based trust (SSL/TLS, PKI).  
  * Secure email, secure shell (SSH), and code signing.

* **RSA (Rivest–Shamir–Adleman)**  

  * Public/private key pair algorithm based on large prime factorization.  
  * Encryption with public key, decryption with private key.  
  * Key generation involves choosing two primes, computing modulus *n*, totient, and public/private exponents.  
  * Vulnerable to weak primes or insufficient key lengths (e.g. < 2048 bits is risky).

* **Diffie-Hellman Key Exchange**  

  * Method for two parties to derive a shared secret over insecure channel.  
  * Uses a group generator *g*, prime modulus *p*, and each party’s private exponent.  
  * Doesn’t itself provide authentication (susceptible to man-in-the-middle unless combined with signatures).

* **SSH (Secure Shell)**  

  * Uses asymmetric keys for authentication and session setup.  
  * Once connection is established, symmetric encryption (e.g. AES) is used for data.  
  * Key exchange (DH or ECDH) + host key verification + encrypted channel.

* **Digital Signatures & Certificates**  

  * Signature: data signed using sender’s private key; verified with public key.  
  * Certificate: binds identity (e.g. domain name) to public key, signed by a Certificate Authority (CA).  
  * Certificate chains and trust model; certificate revocation mechanisms (CRL, OCSP).

* **PGP / GPG (Pretty Good Privacy / GNU Privacy Guard)**  

  * Asymmetric encryption and signing for email and files.  
  * Web-of-trust model (PGP) vs hierarchical CA model.  
  * Key management, signing others’ keys, encrypting to multiple recipients, key revocation.

## 2. Commands / Tools Practiced (or likely to practice)

* `ssh-keygen` to generate RSA or ECC keys.  
* `ssh user@host` using public key authentication.  
* `gpg --gen-key`, `gpg --encrypt`, `gpg --decrypt`, `gpg --sign`, `gpg --verify`.  
* Tools to inspect certificates: `openssl x509 -in cert.pem -text -noout`.  
* Possibly `openssl genrsa`, `openssl rsautl`, `openssl dgst -sign` / `-verify`.

## 3. Takeaways

* Asymmetric cryptography solves the key distribution problem inherent in symmetric systems.  
* RSA and Diffie-Hellman are foundational algorithms; modern systems often prefer ECC equivalents.  
* Digital signatures add non-repudiation and integrity to communications.  
* SSH, TLS, and PGP rely heavily on public key infrastructure.  
* Proper key lengths, safe parameter choices, and certificate trust chains are critical for security.

## 4. Next Steps

* Practice generating and signing X.509 certificates via OpenSSL.  
* Use GPG to encrypt and sign messages with real keys, share public keys, verify signatures.  
* Study certificate authorities, root trust stores, and certificate lifecycle (renewal, revocation).  
