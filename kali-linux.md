# Kali Linux - Red Team VM

This document outlines the setup of the Kali Linux VM used for offensive security testing in the homelab.

---

## VM Configuration

- **RAM**: 4 GB  
- **CPU**: 2 cores  
- **Disk**: 80 GB  
- **Network**: VMnet8 (NAT)  
- **IP Address**: `192.168.239.30`  
- **Gateway**: `192.168.239.2`  
- **DNS Server**: `192.168.239.10` (Domain Controller)

---

## Installation

- Downloaded **Kali Linux ISO** from the [official Kali website](https://www.kali.org/get-kali/)
- Chose **Graphical Installer** for full setup
- Set hostname: `khavin-kali`
- Configured user account: `khavin`
- Used guided partitioning and default software selection
- Installed GRUB bootloader and completed setup

---

## Post-Installation Configuration

- Updated packages:

```bash
sudo apt update && sudo apt upgrade -y

-Installed essential tools
sudo apt install crackmapexec bloodhound neo4j -y

-Set static IP configuration using /etc/netplan/*.yaml and applied with:
sudo netplan apply

---

## Connectivity Verification

- Verified DNS resolution and ping to domain controller:

```bash
ping 192.168.239.10

Successfully joined homelab network

Tested access to Windows Server shares and performed SMB enumeration

Tools Tested
enum4linux

crackmapexec

BloodHound + Neo4j (GUI and graph analysis)

PowerShell enumeration using SharpHound.ps1

Next Steps
Begin red team testing against Windows domain

Document successful enumeration, privilege escalation, and attack paths

Correlate findings with logs and monitor detection using blue team tools

