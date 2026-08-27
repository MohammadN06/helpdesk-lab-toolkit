# Helpdesk Lab & Automation Toolkit

A home-built Active Directory lab simulating real help desk scenarios, paired with PowerShell scripts to automate the tickets I handle daily as a Tier 1 support technician (account unlocks, password resets, role/group management).

## Why this project
I work help desk support for a CMS Identity Management system, handling account unlocks, MFA troubleshooting, password resets, and role requests. This lab recreates that environment at home so I can document, automate, and demonstrate the same skills.

## Environment
- **Hypervisor:** Oracle VM VirtualBox
- **Domain Controller:** Windows Server 2022 Standard Evaluation (Desktop Experience)
- **Domain:** corp.local
- **Network:** Isolated internal network (not exposed to host network)

## Build Log

### Day 1 — Domain Controller Setup
- Installed VirtualBox and configured an isolated internal network for the lab.
- Downloaded Windows Server 2022 Evaluation and Windows 11 Enterprise Evaluation ISOs.
- Created the DC01 VM (4GB RAM, 80GB dynamic disk).
- Hit a disk-full error mid-install due to low host drive space — freed up space and recreated the virtual disk.
- Initially installed Server Core by mistake. Learned that Microsoft doesn't allow converting between Server Core and Desktop Experience after install — had to do a clean reinstall selecting the correct edition.
- Successfully installed Windows Server 2022 (Desktop Experience).
- Installed the Active Directory Domain Services role.
- Promoted the server to a domain controller for the domain **corp.local**.

## Coming next
- Create test user accounts and an OU structure
- Build a client VM and join it to the domain
- Write PowerShell scripts to automate common help desk tickets (account unlock checks, bulk password resets, new-user provisioning)
