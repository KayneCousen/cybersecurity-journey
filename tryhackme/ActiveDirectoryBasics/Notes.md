# Room: Active Directory Basics (TryHackMe)

**Date:** 1 Sept 2025  
**Path:** Cyber Security 101  
**Goal:** Understand what Active Directory is and how it’s used in networks.  



## 1. Key Concepts Learned
- Active Directory is Microsoft’s directory service for managing users, computers, and permissions in a network.
- A **Domain Controller (DC)** is the server that runs AD and authenticates users.
- **Objects**: Users, Groups, Computers, Organizational Units (OUs).
- Common protocols: **LDAP** (lookups), **Kerberos** (authentication), **SMB** (file sharing).



## 2. Commands / Tools Practiced
- `gpupdate /force` will force all the GPOs to refresh even if there are no changes users on Windows
- `xfreerdp [MACHINE_IP]` is a free and open-source implementation of the Microsoft Remote Desktop Protocol (RDP)
- Logged into lab VM and practiced navigating the AD structure.



## 3. Takeaways
- AD is like the “central brain” of a Windows network.
- Every user and computer in the company usually belongs to the domain.
- Misconfigured permissions in AD can give attackers huge power.



## 4. Next Steps
- Continue Cyber Security 101 path (Command Line)
- Later: learn AD attack techniques (Kerberoasting, Pass-the-Hash) once fundamentals are stronger.
