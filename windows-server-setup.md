# Windows Server 2022 Setup

## VM Configuration
- **VM Software:** VMware Workstation
- **Memory:** 16 GB
- **CPU Cores:** 4
- **Disk Size:** 80 GB
- **Network:** VMnet8 (NAT)

## Installation
- ISO: Windows Server 2022 Evaluation
- Version: Standard (Desktop Experience)
- Static IP: 192.168.239.10
- Subnet: 255.255.255.0
- Gateway: 192.168.239.2
- DNS: 127.0.0.1

## Features Installed
- Active Directory Domain Services (AD DS)
- DNS Server

## Domain Info
- Domain: `homelab.local`
- Hostname: `dc1`

## Notes
- Promoted to Domain Controller after AD DS install
