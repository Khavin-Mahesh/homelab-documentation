# Windows 10 Domain-Joined Client

This document outlines the configuration and domain join process for the Windows 10 virtual machine.

---

## VM Configuration

- **RAM**: 4 GB  
- **CPU**: 2 cores  
- **Disk**: 60 GB  
- **Network**: VMnet8 (NAT)  
- **IP Address**: `192.168.239.20`  
- **Gateway**: `192.168.239.2`  
- **DNS Server**: `192.168.239.10` (domain controller)

---

## Setup

- Downloaded official Windows 10 Pro ISO from Microsoft
- Installed Windows 10 Pro on VMware Workstation
- Renamed computer to `win10-client`
- Disabled Internet Explorer Enhanced Security temporarily

---

## Domain Join

- Set static IP and DNS
- Joined domain: `homelab.local`
- Rebooted and logged in as: `homelab\tuser`
- Verified domain login and Group Policy application

---

## Verification

Ran the following commands to confirm domain connectivity:

```cmd
echo %userdomain%
gpresult /r
ping dc1.homelab.local
