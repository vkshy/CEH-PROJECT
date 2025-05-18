🛡️ Network Penetration Testing with Real-World Exploits and Security Remediation

This project simulates real-world network attacks and defense strategies using **Kali Linux** as the attacker machine and **Metasploitable 2** as the target. It covers key penetration testing phases including scanning, enumeration, exploitation, and remediation — all performed in a controlled lab environment for ethical learning purposes.

---

## 🎯 Objectives

* Understand and simulate real-world network attacks
* Perform scanning, enumeration, and exploitation using tools like Nmap and Metasploit
* Crack Linux password hashes using John the Ripper
* Identify outdated services and recommend appropriate remediations

---

## 💻 Lab Setup

### 🖥️ Operating Systems

* **Kali Linux** – Attacker Machine
* **Metasploitable 2** – Target Machine

### 🛠️ Tools Used

* `nmap` – For port, OS, and service version scanning
* `Metasploit` – For exploiting vulnerable services
* `John the Ripper` – For cracking password hashes
* Linux built-in commands (`cat`, `passwd`, `whoami`) – For user management and system enumeration

---

## 🚀 Tasks Performed

### 🔍 Network Scanning

```bash
nmap -v <IP>        # Basic scan
nmap -v -p- <IP>     # Full port scan
nmap -sV <IP>        # Service version detection
nmap -O <IP>         # OS detection
```

### 🔐 Hidden Ports Discovered

Ports such as **8787**, **36588**, **53204**, etc., were identified through deep scans.

### 📡 Enumeration

* OS Detected: **Linux 2.6.x** (Metasploitable)
* Open Services: **vsftpd**, **OpenSSH**, **Telnetd**
* Vulnerable Ports: **21 (FTP)**, **22 (SSH)**, **23 (Telnet)**

### 💥 Exploitation

* **vsftpd 2.3.4** backdoor using Metasploit
* Attempted brute-force and configuration assessment on **SSH (22)**
* Explored weak authentication in **Telnetd (23)** using manual login

### 👤 Privilege Escalation

* Created new user `rahul` with root privileges
* Cracked password hash using **John the Ripper**

### 🔧 Remediation Steps

| Service | Vulnerability               | Fix                                    |
| ------- | --------------------------- | -------------------------------------- |
| vsftpd  | Backdoor (CVE-2011-2523)    | Upgrade to 3.0.5 / Use SFTP            |
| SSH     | Weak passwords, brute-force | Use key-based auth, disable root login |
| Telnet  | Plaintext transmission      | Disable and replace with SSH           |

---

## 📚 Major Learning

* Understood user management and password storage in Linux
* Learned to crack hashes using **John the Ripper**
* Mastered Nmap for detecting ports, services, and OS
* Practiced exploiting FTP, SSH, and Telnet vulnerabilities
* Learned to secure systems by updating or disabling outdated services

---

## ⚠️ Disclaimer

This project is strictly for **educational purposes**. All actions were conducted in a **controlled lab environment**. Do not apply these techniques on real systems without permission.

---

## 📎 References

* [CVE-2011-2523](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-2523)
* [Metasploit Documentation](https://docs.rapid7.com/metasploit/)
* [John the Ripper](https://www.openwall.com/john/)
* [Apache Vulnerabilities](https://httpd.apache.org/security_report.html)
