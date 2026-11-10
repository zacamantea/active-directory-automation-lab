# Active Directory Automation Lab

**A Windows domain lab on Proxmox, built to be rebuilt.** A domain controller and a mix of Windows 10 and 11 clients, with a plan to automate users, groups, GPOs, file shares and security baselines in PowerShell.

> **Status: lab built, automation not yet written.** The virtual machines exist and are backed up; the scripts below are the planned work. This README says so plainly rather than pretending otherwise.

---

## The lab

| VM | Role |
|---|---|
| `LAB-DC01` | Domain controller |
| `LAB-W11E01` | Windows 11 Enterprise client |
| `LAB-W11P01`, `LAB-W11P02` | Windows 11 Pro clients |
| `LAB-W10P01`, `LAB-W10P02` | Windows 10 Pro clients |

- Runs on a Proxmox VE node; the VMs are **powered off until needed** to save RAM
- Mixed editions on purpose, to test policy behaviour across Enterprise vs Pro and Windows 10 vs 11
- Protected by a **weekly backup** of stopped guests to the Proxmox Backup Server, and snapshot-friendly for "break it, roll back" experiments

## What it is for

- Practise the Windows enterprise stack: AD DS, DNS, Group Policy, file services, domain join
- Test security baselines and see their effect on real clients
- Build repeatable, scripted environments rather than clicking through wizards

## Planned automation (PowerShell)

- [ ] Create the OU structure, users and groups **from a CSV**
- [ ] GPO set: password and lockout policy, security baseline, drive mappings, software restriction
- [ ] File shares with role-based NTFS and share permissions
- [ ] Join the clients to the domain and apply policy
- [ ] Validation script that proves the environment matches the spec
- [ ] A one-command "rebuild the lab from backups or scripts" path

## How it will be organised

```
scripts/         PowerShell modules (users, groups, GPOs, shares, join)
data/            CSV inputs (sample data only, no real people)
docs/            Design, diagrams, test cases
```

## Why this repo is public

To show the plan and the approach. Real credentials and any real data stay out of it; the lab uses sample accounts only.
