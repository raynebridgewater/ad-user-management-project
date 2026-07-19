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
- Format: (*e.g. jsmith*)
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
- Hypervisor: VMWare Workstation Player
- Domain Controller (DC) specs: TBD
- Client VM(s): Windows 11, specs TBD
- Network Topology - TBD
## 2. Build Log
