
# Active Directory Simulation – CyberTech Solutions

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **CyberTech Solutions**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**CyberTech Solutions** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (Account Department)
- 1 x Windows 10 Client PC (Legacy Software)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 192.168.1.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win PRO)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 192.168.1.243  | AD Domain Controller (DC)   |
| Windows 8 PC  | DHCP    | Client (Accounts)           |
| Windows XP PC | DHCP    | Legacy Client               |

---

## Domain Configuration

- **Domain Name**: `fikayotech.ai`
- **Server Name**: `FIKAYOTECH`
- **Static IP**: `192.168.1.243`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
CyberTech.local
├── OU: IT Department
│   └── Users: Fiyin.IT
    

├── OU: Production Department
│   └── Users: Blessing.Production
    

├── OU: Purchasing Department
│   └── Users: Adeola.Purchasing

├── OU: HR Department
│   └── Users: Esther.HR
    

├── OU: Consultation Department
│   └── Users: Ade.Consultation
    

├── OU: Finance Department
│   └── Users: Oluyemi.Finance
    └── Users: Charles.IT
    

├── OU: Sales
│   └── Users: Olusola.Sales
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableShutdownAction`
- **Linked to**: OU: IT Department
- **Policy Configured**:
  - `Computer Configuration` > `Policies` > `Administrative Templates` > `Start Menu Taskbar` > `Remove and Prevent access to the Shut Down, Restart, Sleep, and Hibernate commands`
  - Set **"Remove and Prevent access to the Shut Down, Restart, Sleep, and Hibernate commands"** to **Enabled**

Result: The Shutdown, restart, sleep and hibernate commands are removed from the Start MENU **IT OU**.

---

## Screenshots

- AD Domain Structure
- GPO Editor Screenshot
- PC joined to domain
- Result of Remove and Prevent access to the Shut Down, Restart, Sleep, and Hibernate commands

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**Adeyinka M. Adeyanju**  
Cybersecurity Analyst  
