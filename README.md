# Ubuntu Server Remote Administration & Samba File Sharing Lab

## 📌 Project Overview

This project demonstrates the deployment and configuration of an Ubuntu Server virtual machine using UTM on Apple Silicon (M1), along with secure remote administration from Windows 11 and cross platform file sharing using Samba.

The lab simulates real world IT support tasks including server setup, network troubleshooting, SSH remote access, and SMB file sharing between Linux and Windows systems.

---

## 🚀 Key Highlights

- Successfully deployed an Ubuntu Server virtual machine using UTM on Apple Silicon (M1)
- Configured secure remote administration using SSH
- Diagnosed and resolved DNS and network connectivity issues
- Configured Samba for Windows to Linux file sharing
- Verified successful file transfer between Windows 11 and Ubuntu Server
- Demonstrated real world IT troubleshooting and system administration workflows

---

## 🖥️ Environment & Tools

- Ubuntu Server 24.04 LTS (ARM64)
- Windows 11 Pro
- UTM Virtualization
- OpenSSH Server
- Samba (SMB Protocol)
- TCP/IP Networking
- DNS Services

---

## 🎯 Project Objectives

- Deploy a Linux server in a virtualized environment
- Configure network connectivity between Windows and Linux
- Troubleshoot DNS and connectivity issues
- Enable secure remote administration via SSH
- Configure Samba file sharing between Windows and Ubuntu
- Perform basic Linux system administration tasks

---

## ⚙️ Implementation Steps

### 1. Ubuntu Server Deployment

- Installed Ubuntu Server inside UTM virtual machine
- Configured initial network settings for communication between systems
![Ubuntu Server and Windows 11 Ready](screenshots/Screenshot%202026-06-11%20at%2006.31.51.png)
---

### 2. Network & DNS Troubleshooting

Diagnosed DNS resolution errors:

```text
Temporary failure in name resolution
```

Verified connectivity using:

```bash
ping google.com!
[Network Interface IP Address](screenshots/Screenshot%202026-06-11%20at%2006.43.16.png)
```

Confirmed successful internet and local network access.

---

### 3. SSH Installation & Remote Access

Verified SSH service:

```bash
sudo systemctl status ssh
```

Result:

```text
active (running)
```

Connected from Windows 11:

```bash
ssh kings29@192.168.64.5
```

Result:

```text
Welcome to Ubuntu 24.04 LTS
```

Successfully established remote administration access.

![SSH Connection](screenshots/Screenshot%202026-06-11%20at%2006.39.05.png)
---
![SSH Remote Login](screenshots/Screenshot%202026-06-11%20at%2006.36.18.png)
### 4. Linux User Management

Verified user directories:

```bash
ls /home
```

Confirmed user accounts and permissions.

---

### 5. Samba Installation & Configuration

Configured Samba share:

```ini
[shared]
path = /home/kings29/shared
browseable = yes
read only = no
valid users = kings29
```

Restarted Samba service:

```bash
sudo systemctl restart smbd
```
![Samba Service Restart](screenshots/Screenshot%202026-06-11%20at%2008.13.19.png)
Verified configuration:

```bash
sudo testparm
```

---

### 6. Shared Folder Setup

Created shared folder:

```bash
mkdir -p /home/kings29/shared
chmod 777 /home/kings29/shared
```

Verified permissions:

```bash
ls -ld /home/kings29/shared
```

Example output:

```text
drwxrwxrwx 2 kings29 kings29 4096 Jun 8 09:25 /home/kings29/shared
```
![Shared Folder Permissions](screenshots/Screenshot%202026-06-11%20at%2006.45.42.png)
---

### 7. File Transfer Testing

Created test file:

```bash
echo "Samba test file" > /home/kings29/shared/test.txt
```

Verified file creation:

```bash
ls -l /home/kings29/shared
```

Result:

```text
test.txt
```
![File Transfer Verified](screenshots/test%20file.png)
---

### 8. Windows File Access

Accessed Samba share from Windows File Explorer:

```text
\\192.168.64.5\shared
```

Result:

- Shared folder opened successfully
- File transfer between Windows and Ubuntu confirmed
- Samba configuration validated
- ![Windows UNC Path Entry](screenshots/Screenshot%202026-06-11%20at%2006.47.33.png)
- ![Windows Network Navigation](screenshots/Screenshot%202026-06-11%20at%2008.06.23.png)
- ![Windows Samba Authentication](screenshots/Screenshot%202026-06-11%20at%2006.49.22.png)
 ![Windows Samba Access](screenshots/Screenshot%202026-06-11%20at%2008.43.42.png)
---

## 🛠️ Tools & Commands Used

### Linux Commands

```bash
ip a
ping google.com
ls /home
ls -ld /home/kings29/shared
ls -l /home/kings29/shared
systemctl status ssh
systemctl status smbd
testparm
```

### Services

- OpenSSH
- Samba (SMB)
- DNS
- TCP/IP Networking

---

## 🧠 Skills Demonstrated

### Technical Skills

- Linux System Administration
- Ubuntu Server Configuration
- SSH Remote Access
- DNS Troubleshooting
- Network Troubleshooting
- Samba File Sharing
- Linux File Permissions
- Virtualization (UTM)
- Windows-Linux Integration

### IT Support Skills

- Incident Troubleshooting
- Problem Resolution
- Remote Administration
- Technical Documentation
- Infrastructure Support
- Service Validation
- Cross-Platform Support

---


## 🧩 Challenges & Solutions

### DNS Resolution Failure

**Issue:**

```text
Temporary failure in name resolution
```

**Solution:**

- Verified network configuration
- Tested connectivity using ping
- Corrected DNS configuration

### SSH Authentication Issues

**Issue:**

Unable to log in remotely.

**Solution:**

- Verified username
- Verified credentials
- Tested SSH service status

### Samba Access Issues

**Issue:**

Windows blocked access to shared folder.

**Solution:**

- Updated Samba configuration
- Verified permissions
- Validated user access settings

### File Visibility Issues

**Issue:**

Shared files were not appearing.

**Solution:**

- Verified shared folder path
- Confirmed permissions
- Tested file creation and visibility

---

## 📊 Project Status

**Status: COMPLETED ✅**

Completed:

- Ubuntu Server deployment
- Network configuration
- DNS troubleshooting
- SSH configuration
- Remote administration
- User management
- Samba configuration
- Windows file sharing
- File transfer validation

---

## 📚 Key Learning Outcomes

- Linux server deployment and management
- SSH remote administration
- DNS troubleshooting techniques
- Samba file sharing configuration
- Windows and Linux interoperability
- Linux permissions management
- Structured troubleshooting methodology
- Technical documentation practices



## 🏁 Summary

Successfully deployed and configured an Ubuntu Server environment, implemented secure SSH remote administration, resolved network and DNS issues, configured Samba file sharing, and validated file transfer between Windows 11 and Ubuntu Linux systems.
