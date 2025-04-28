# Linux Home Server

This project documents the process of building a simple home server based on Ubuntu Server.  
The goal was to create a stable, secure and easy-to-manage environment that supports basic services like SSH, HTTP and FTP, along with automation and monitoring.

## Features

- Static IP configuration using Netplan
- Remote access via SSH
- Web hosting with Apache
- FTP server with vsftpd
- Firewall rules using UFW
- Automated home directory backups using cron
- Basic system monitoring (htop, journalctl, disk usage)
- User management with sudo access

## System

- Ubuntu Server 22.04
- Installed inside VirtualBox (bridged network adapter)
- Single network interface: enp0s3
- Primary user: admin
---

## 📡 1. Static IP Configuration (Netplan)

**File:** `/etc/netplan/00-installer-config.yaml`

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: no
      addresses: [192.168.1.100/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]


🏠 Ubuntu Home Server Setup
Simple • Stable • Secure
A complete guide for building a home server based on Ubuntu Server 22.04 LTS.

Supports: SSH access, Apache web hosting, FTP server (vsftpd), automated backups, and basic system monitoring.

⚙️ System Information
Operating System: Ubuntu Server 22.04 LTS

Virtualization: VirtualBox (Bridged Adapter)

Network Interface: enp0s3

Primary User: admin (sudo privileges)

📡 Static IP Configuration (Netplan)
Edit /etc/netplan/00-installer-config.yaml:

yaml
Kopiuj
Edytuj
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: no
      addresses: [192.168.1.100/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]
Apply the configuration:

bash
Kopiuj
Edytuj
sudo netplan apply
🔒 Tip: Reserve this IP in your router’s DHCP settings.

🔐 Enable Remote Access (SSH)
Install and start SSH:

bash
Kopiuj
Edytuj
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
SSH Hardening Tips:

Change SSH port in /etc/ssh/sshd_config

Disable root login (PermitRootLogin no)

Use SSH key-based authentication

🌐 Install and Configure Apache Web Server
Install Apache:

bash
Kopiuj
Edytuj
sudo apt update
sudo apt install apache2
sudo systemctl enable apache2
sudo systemctl start apache2
📂 Website files should



Apply configuration:

sudo netplan apply

Enable Remote Access (SSH)

sudo systemctl enable ssh
sudo systemctl start ssh
