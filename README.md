# 🧠 Active Directory Attack Lab

A complete lab environment to simulate and understand real-world Active Directory (AD) attacks. This lab is built using VMware and includes various common attack techniques used by adversaries in enterprise networks.

---

## 🏗️ Lab Architecture

- **Attacker Machine**: Kali Linux
- **Domain Controller**: Windows Server (Domain: `corp.local`)
- **Domain User Client**: Windows 10 (Joined to the domain)

---

## 🎯 Objectives

- Understand Active Directory structure and enumeration.
- Simulate real-world attacks like:
  - Kerberoasting
  - AS-REP Roasting
  - Pass-the-Hash
  - DCSync
- Escalate privileges to **Domain Admin**.

---

## ⚙️ Setup & Configuration

1. Install VMware and set up 3 virtual machines.
2. Configure Active Directory on Windows Server.
3. Join Windows 10 client to the domain.
4. Create standard user accounts in the domain (`user1`, `user2`, etc.).
5. Ensure communication between machines (test with `ping` and `nslookup`).

---

## 🔍 Enumeration Phase

- Collected domain info using:
  - `ldapsearch`
  - `rpcclient`
  - `enum4linux`
  - `BloodHound`
- Extracted user list and SPNs.

---

## 🛠️ Attack Techniques Used

### 1. 🔥 Kerberoasting
- Tool used: `GetUserSPNs.py`
- Extracted service account TGTs and cracked them offline.

### 2. 🧊 AS-REP Roasting
- Tool used: `GetNPUsers.py`
- Targeted users without Kerberos pre-authentication.

### 3. 🧪 Pass-the-Hash
- Used stolen NTLM hashes to authenticate directly without password.

### 4. 🧬 DCSync Attack
- Used `secretsdump.py` to replicate AD database and extract Administrator NTLM hash.
- Gained **Domain Admin** privileges.

---

## 📸 Screenshots

All key steps (setup, enumeration, exploitation, privilege escalation) are documented with screenshots in the `screenshots/` folder.

---

## 🧾 Documentation

Full PDF report is included in the repo:
- Detailed steps
- All commands used
- Troubleshooting tips
- Attack diagrams

---
