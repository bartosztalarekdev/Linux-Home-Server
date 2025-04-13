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
