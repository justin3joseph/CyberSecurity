# Cybersecurity Lab Plan (2 Hours/Day)

To study Cybersecurity with 2-hour lab practicals, you can structure your sessions effectively by combining short theory segments with hands-on exercises. Here’s a week-wise lab plan for 4–6 weeks (which can be extended), using free/open-source tools and optionally AWS Cloud for practice.

---

## 🔧 Basic Setup (Before First Session)

### Tools to Install (Locally or on AWS Cloud):
- Kali Linux (VM or cloud)
- VirtualBox / VMware (if local)
- Wireshark
- Burp Suite Community Edition
- OWASP Juice Shop or DVWA (vulnerable web apps)
- Python (for scripting tasks)
- Nmap, Nikto, Metasploit (Kali tools)

### AWS Cloud Setup Option:
- EC2 with Ubuntu/Kali
- Install lab tools
- Configure security groups to allow required ports (carefully)

---

## 🗓️ Weekly Cybersecurity Lab Plan

### **Week 1: Introduction to Cybersecurity and Linux**
- **Theory (30 min)**: What is cybersecurity, key domains (network, app, cloud, etc.)
- **Lab (90 min)**:
  - Basic Linux commands
  - File permissions & users
  - Setup Kali Linux or connect to AWS instance
  - Practice `netstat`, `ping`, `traceroute`, `ifconfig`, etc.

### **Week 2: Networking and Reconnaissance**
- **Theory (30 min)**: IP, ports, protocols (TCP/UDP), the 3-way handshake
- **Lab (90 min)**:
  - Use Nmap for network scanning
  - Passive recon with `whois`, `nslookup`, `theHarvester`
  - Packet capture with Wireshark
  - Use `tcpdump` for basic analysis

### **Week 3: Vulnerability Scanning**
- **Theory (30 min)**: Types of vulnerabilities, CVE, CVSS
- **Lab (90 min)**:
  - Scan DVWA/Juice Shop using Nikto or OpenVAS
  - Identify common issues (XSS, SQLi, etc.)
  - Explore OWASP Top 10 vulnerabilities

### **Week 4: Web Application Attacks**
- **Theory (30 min)**: OWASP Top 10 overview
- **Lab (90 min)**:
  - Run attacks on DVWA (XSS, SQLi, CSRF)
  - Use Burp Suite to intercept and modify requests
  - Try brute-force attack using Hydra (for login pages)

### **Week 5: Exploitation Basics**
- **Theory (30 min)**: Intro to Metasploit and payloads
- **Lab (90 min)**:
  - Exploit a known vulnerability in Metasploitable
  - Use `msfconsole` to gain reverse shell
  - Post-exploitation: find users, passwords, and files

### **Week 6: Security Best Practices & Mini Project**
- **Theory (30 min)**: Cyber hygiene, defense-in-depth
- **Lab (90 min)**:
  - Secure a Linux VM: firewall, fail2ban, password policy
  - Mini project: Simulate an attack & patch the vulnerability
  - Report writing: Create a simple vulnerability assessment report

---

## ☁️ Optional AWS-Based Lab Setup
- Launch EC2 instance with Kali Linux or Ubuntu
- Open ports only when needed
- Use Elastic IP for access
- Store scripts and reports in S3 or GitHub

---

## 📚 Extra Learning Resources

### Books:
- *The Web Application Hacker's Handbook*
- *Hacking: The Art of Exploitation*

### Free Courses:
- [Cybrary](https://www.cybrary.it/)
- [TryHackMe](https://tryhackme.com/)
- [Hack The Box](https://www.hackthebox.com/)
- [OWASP WebGoat](https://owasp.org/www-project-webgoat/)

### Certifications (Optional Later):
- CompTIA Security+
- CEH (Certified Ethical Hacker)
- OSCP
