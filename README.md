# 🔴 Advanced Penetration Testing & Pivoting Lab
**Author:** Md. Jipel Ahamed Arman  
*Cybersecurity Enthusiast | Penetration Testing | Red Teaming | Network Security*

---

## 📖 Project Overview
This project documents the design and execution of a professional cybersecurity home lab built using **VMware Workstation**. The environment simulates a realistic, segmented enterprise network, specifically designed to practice the transition from initial access to internal network compromise.

**Core Focus Areas:**
* Vulnerability Assessment & Exploitation
* Privilege Escalation (Linux/Windows)
* **Internal Network Enumeration & Pivoting**
* Lateral Movement & Post-Exploitation

---

## 🧠 Lab Architecture
The environment is logically segmented into two distinct zones to simulate a perimeter-based defense.



### **Zone 1: External Network (192.168.50.0/24)**
* **Kali Linux:** Primary Offensive Platform.
* **Metasploitable 2 (The Pivot):** A dual-homed vulnerable web server acting as the bridge.
  * `eth0`: Connected to External Network.
  * `eth1`: Connected to Internal Network.

### **Zone 2: Internal Network (10.10.10.0/24)**
* **Domain Controller:** Windows Active Directory Services.
* **App Server:** Internal Corporate Application Host.
* **Employee Workstation:** Windows 10 Client System.

---

## ⚔️ Activities Performed

### 1. Reconnaissance & Enumeration
* **Host Discovery:** `netdiscover`, `ARP scanning`.
* **Service Mapping:** Full `Nmap` TCP/UDP port scans and banner grabbing.
* **Vulnerability Research:** Mapping services to known CVEs using `Searchsploit`.

### 2. Exploitation
Successfully gained initial access through multiple vectors:
* **vsftpd 2.3.4 Backdoor** (CVE-2011-2523)
* **Samba usermap_script** (CVE-2007-2447)
* **PHP CGI Argument Injection** (CVE-2012-1823)
* **Credential Attacks:** SSH/Telnet brute-forcing and MySQL default credential exploitation.

### 3. Pivoting & Lateral Movement
* **Proxychains & SSH Tunneling:** Routing traffic through the compromised Metasploitable host to reach the 10.10.10.0/24 segment.
* **Meterpreter Routing:** Utilizing MSF post-exploitation modules to automate internal routing.

### 4. Privilege Escalation & Post-Exploitation
* **Local Escalation:** Exploiting misconfigurations to gain `ROOT` and `SYSTEM` privileges.
* **Credential Harvesting:** LSASS memory dumping, NTLM hash extraction, and Token Impersonation.

---

## 🧰 Tools & Technologies
* **Hypervisor:** VMware Workstation Pro
* **OS:** Kali Linux, Metasploitable 2, Windows Server, Windows 10
* **Frameworks:** Metasploit, Proxychains
* **Scanning:** Nmap, Netdiscover
* **Cracking:** Hashcat, John the Ripper

---

## 📄 Included Reports
This repository includes detailed documentation of the lab's lifecycle:
1. [cite_start][Isolated VMware Lab Setup Report](./Reports/Lab_Setup.pdf) 
2. [Vulnerability Assessment Metasploitable 2]
3. [Full Penetration Testing Execution Report]

---

## ⚠️ Disclaimer
This project was conducted in a **fully isolated and authorized lab environment** for educational purposes only. Unauthorized access to computer systems is illegal. Always follow ethical guidelines and the rules of engagement.
