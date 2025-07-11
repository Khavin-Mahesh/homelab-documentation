# Windows 10 Domain-Joined Client

## VM Configuration

- RAM: 4 GB
- CPU: 2 cores
- Disk: 60 GB
- Network: VMnet8 (NAT)
- IP: `192.168.239.20`
- Gateway: `192.168.239.2`
- DNS: `192.168.239.10` (domain controller)

## Setup

- Downloaded ISO from Microsoft
- Installed Windows 10 Pro
- Disabled IE Enhanced Security temporarily

## Domain Join

- Joined domain: `homelab.local`
- Logged in as: `homelab\tuser`
- Verified login and domain policies applied

## Notes

- Verified connectivity and DNS resolution
