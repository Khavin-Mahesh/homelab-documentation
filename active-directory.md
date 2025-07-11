# Active Directory Domain Setup

## Promotion Steps

1. Installed **Active Directory Domain Services (AD DS)** via Server Manager
2. Promoted server to domain controller
   - Domain name: `homelab.local`
   - DSRM password set
3. Server rebooted and joined the new domain as `dc1.homelab.local`

## DNS Configuration

- Internal DNS set to `127.0.0.1` on DC
- Forward Lookup Zone created for `homelab.local`
- A record created for `dc1` with IP `192.168.239.10`

## Post-Setup

- Confirmed tools installed: Active Directory Users and Computers, DNS, GPMC
- Created test user: `tuser@homelab.local`

## Notes

- Next steps: Add client VM and join it to the domain
