
# Cybersecurity Lab

### Focus: Linux fundamentals, user permissions, and basic networking  

---

## Introduction + Linux Essentials

### Objective:
Understand the Linux shell, basic commands, and how to navigate the file system.

### Lab Activities

#### 1. Basic File & Directory Commands
```bash
pwd                    # Show current directory
ls                     # List files
ls -l /home            # List files with details in /home
cd /etc                # Change directory to /etc
mkdir demo             # Create a directory named demo
touch demo.txt         # Create a new empty file
cat /etc/passwd        # View contents of a file
```

#### 2. File Management
```bash
cp demo.txt demo_copy.txt    # Copy file
mv demo.txt demo_renamed.txt # Rename/move file
rm demo_copy.txt             # Delete file
rmdir demo                   # Remove empty directory
```

#### 3. Help and Manual Pages
```bash
man ls              # Manual for the ls command
ls --help           # Quick help
```

---

## Users, Groups, and Permissions

### Objective:
Learn user management and file permission control.

### Lab Activities

#### 1. User and Group Commands *(May require sudo)*
```bash
whoami                     # Current user
id                         # UID, GID, groups
adduser cyberstudent       # Create a new user
passwd cyberstudent        # Set password
groups                     # List user’s groups
```

#### 2. File Permissions
```bash
ls -l file.txt             # Check permissions
chmod 755 file.txt         # Change permissions (rwxr-xr-x)
chmod u+x script.sh        # Give execute to user
chown user:group file.txt  # Change owner
```

#### 3. Practice Exercise
- Create a directory `secure_lab`
- Create a file `notes.txt`
- Change owner to `cyberstudent`
- Remove write permissions from others

---

## Network Utilities in Linux

### Objective:
Learn basic network diagnostics and system recon.

### Lab Activities

#### 1. Check IP & Interfaces
```bash
ifconfig                  # Show IP address (install via: apt install net-tools)
ip addr                   # Modern alternative
hostname -I               # IP address only
```

#### 2. Test Connectivity
```bash
ping google.com           # Ping external server
ping 8.8.8.8              # Ping Google DNS
traceroute google.com     # Trace route (install via: apt install traceroute)
```

#### 3. Open Ports & Active Connections
```bash
netstat -tuln             # Show listening ports (TCP/UDP)
netstat -anp              # Show all connections
ss -tuln                  # Modern alternative to netstat
```

---

## Setup Kali Linux / AWS EC2 *(Optional / Cloud Lab)*

### Objective:
Set up a security-focused lab environment.

#### Option A: Install Kali Linux (Local VM)
- Download Kali from: https://www.kali.org/get-kali/
- Use VirtualBox or VMware
- Set 2GB RAM, 2 CPU, and bridged networking

#### Option B: AWS EC2 Setup
- Launch Ubuntu/Kali EC2 Instance
- Choose `t2.micro`, set key pair
- SSH into instance:
```bash
ssh -i your-key.pem ubuntu@public-ip
```
##### Basic AWS Commands:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install net-tools traceroute nmap curl -y
```

---

## Review and Mini Project

### Mini Task: "System Health Check Script"

Create a bash script called `healthcheck.sh` that:
- Shows current user
- Lists disk usage
- Shows IP address
- Lists open network ports

#### Sample Script:
```bash
#!/bin/bash
echo "User: $(whoami)"
echo "Disk Usage:"
df -h
echo "IP Address: $(hostname -I)"
echo "Open Ports:"
ss -tuln
```

#### Run the script:
```bash
chmod +x healthcheck.sh
./healthcheck.sh
```
