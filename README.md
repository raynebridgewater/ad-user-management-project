# Active Directory Home Lab - Build Log
### Scenario
Simulated Hospitality Business structured around the following departments:
- IT
- Management
- Front of House (FoH)
- Back of House (BoH)
- All Staff (company-wide group)
### Goal
Design and build an Active Directory environment that creates and manages multiple users across multiple departments whilst also simulating common helpdesk scenarios. There will also be least-privilege access to shared resources such as a simulated POS system.
## 1. Planning
### Organizational Unit (OU) Structure
- Top-level Company OU
- Sub-OU: IT
- Sub-OU: Management
- Sub-OU: FoH
- Sub-OU: BoH
### Naming Convention
- Format: *jsmith*
### Group Strategy
- `All-Staff` - Company-Wide, All Users
- `IT` - Admin accounts
- `Management`
- `FoH`
- `BoH`
- POS access tiering
    - `POS-FullAccess` - Management (payments, voids, discounts, reports)
    - `POS-OrderProcessing` - Front of House (sales, billing)
    - Back of House - No POS Access required
### Environment
- OS: Windows Server
- Hypervisor: VMware Workstation Player
- Domain Controller (DC) specs: 2 vCPU, 4GB RAM, 60GB Storage
- Client VM(s): Windows 11, specs TBD
- Network Topology - TBD
## 2. Build Log
### Server Install
- Date: 19-01-2026
- Steps taken:
    - Downloaded Windows Server 2025 ISO from Microsoft
    - Created a virtual machine in VMware Workstation Player with 60GB of storage, 1 virtual processor with 2 cores and 4GB of RAM
    - Installed Windows Server 2025 Standard Evaluation (Desktop Experience)
- Notes: 
    - VMware was opting for an "easy install" when setting up the virtual machine. I was looking to set this up myself so opted to setup with out the OS and install manually.
    - Failed to perform initial boot, formatted the drive and attempted to re-install - This fixed the issue and allowed for the installation to continue without a hitch.