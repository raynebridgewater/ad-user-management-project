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

### Todo
- Dashboard informed me that there was no static IP assigned. This will be added later.

### Server Install
- Date: 19-07-2026
- Steps taken:
    - Downloaded Windows Server 2025 ISO from Microsoft
    - Created a virtual machine in VMware Workstation Player with 60GB of storage, 1 virtual processor with 2 cores and 4GB of RAM
    - Installed Windows Server 2025 Standard Evaluation (Desktop Experience)
    - Installed Active Directory Domain Services
    - Installed DNS Server roles
- Screenshots:
    - *Setup Options*
        ![Setup Options](/screenshots/Setup-Options.png)
    - *Image Options*
        ![Image Options](/screenshots/Image-Options.png)
    - *Pre-Partition*
        ![Pre-Partition](/screenshots/Pre-Partition.png)
    - *Post-Partition*
        ![Post-Partition](/screenshots/Post-Partition.png)
    - *Installing*
        ![Installing](/screenshots/Install.png)
    - *Admin Account Setup*
        ![Admin Account Setup](/screenshots/Admin-Account-Setup.png)
    - *Desktop Post-Install*
        ![Desktop Post-Install](/screenshots/Desktop-Post-Install.png)
    - *Adding Active Directory Domain Services Features*
        ![Adding Active Directory Domain Services Features](/screenshots/Add-AD-DS-Features.png)
    - *Adding DNS Server Features*
        ![Adding DNS Server Features](/screenshots/Add-DNS-Features.png)
    - *No Static IP Warning*
        ![No Static IP Warning](/screenshots/No-Static-IP-Warning.png)
    - *Server Role List*
        ![Server Role List](/screenshots/Server-Role-List.png)
    - *Server Roles Installed*
        ![Server Roles Installed](/screenshots/Server-Roles-Installed.png)
    - *Updated Dashboard*
        ![Updated Dashboard](/screenshots/Updated-Dashboard.png)    
- Notes: 
    - VMware was opting for an "easy install" when setting up the virtual machine. I was looking to set this up myself so opted to setup with out the OS and install manually.
- Issues -> Fixed
    - Failed to perform initial boot, formatted the drive and attempted to re-install - This fixed the issue and allowed for the installation to continue without a hitch.
