# active-directory-automation-lab

A Windows Active Directory lab on Proxmox.

## Lab inventory (built, currently powered off to save RAM)
| VM | Role |
|---|---|
| LAB-DC01 | Domain controller |
| LAB-W11E01 | Windows 11 Enterprise client |
| LAB-W11P01 / LAB-W11P02 | Windows 11 Pro clients |
| LAB-W10P01 / LAB-W10P02 | Windows 10 Pro clients |

Backed up weekly (stopped guests) to the Proxmox Backup Server.

## Status
VMs are created and snapshot-capable; the automation is **not written yet**.

## Planned (PowerShell)
- [ ] Users / OUs / groups from a CSV
- [ ] GPOs and security baseline
- [ ] File shares with permissions
- [ ] Domain join of the clients
