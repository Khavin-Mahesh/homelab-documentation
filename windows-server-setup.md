# Windows Server 2022 Setup

This document outlines the configuration of the Windows Server 2022 virtual machine used as the Domain Controller in the homelab environment.

---

## VM Configuration

- **Hypervisor:** VMware Workstation
- **Memory:** 16 GB
- **CPU:** 4 cores
- **Disk Size:** 80 GB
- **Network:** VMnet8 (NAT)
- **IP Address:** `192.168.239.10`
- **Subnet Mask:** `255.255.255.0`
- **Gateway:** `192.168.239.2`
- **DNS Server:** `127.0.0.1` (localhost)

---

## Installation

- **OS ISO:** Windows Server 2022 Evaluation
- **Version:** Standard Edition (Desktop Experience)
- Installed using default graphical installer
- Named the host: `dc1`

---

## Features Installed

- Active Directory Domain Services (AD DS)
- DNS Server

---

## Domain Configuration

- Created new forest: `homelab.local`
- Promoted server to domain controller
- Rebooted and verified domain services
- DSRM password set during promotion

---

## Notes

- Server successfully acting as Domain Controller and DNS server
- Verified with ADUC, DNS Manager, and GPMC
