# Phase 2: Active Directory & Identity Management

## Objective
To establish a centralized Identity Provider (IdP) and Domain Name System (DNS) authority for the Fenix Bank enterprise network. This phase involves provisioning a Windows Server Domain Controller to enforce access controls, manage network assets, and implement the Principle of Least Privilege (PoLP) through Organizational Units (OUs).

## Step 1: Domain Controller Provisioning (`Fenix-DC01`)
1. **Virtual Machine Creation:** Provisioned a new VM in VirtualBox specifically for the domain controller.
   * **OS:** Windows Server 2022 (Desktop Experience)
   * **Compute:** 4GB RAM, 2 vCPUs
   * **Storage:** 50GB dynamically allocated VDI
2. **Network Attachment:** Connected the VM's virtual Network Interface Card (NIC) to the isolated `Bank_Corporate_LAN` NAT Network.

## Step 2: Network Configuration & Hardening
To ensure reliable endpoint communication and DNS resolution, the server required a static IPv4 configuration rather than relying on DHCP.
1. Renamed the local host to `Fenix-DC01` for standard naming convention compliance.
2. Configured the static IP adapter settings:
   * **IPv4 Address:** `10.0.0.5`
   * **Subnet Mask:** `255.255.255.0` (/24)
   * **Default Gateway:** `10.0.0.1` (VirtualBox NAT Gateway)
   * **Preferred DNS:** `127.0.0.1` (Loopback address, as this server acts as its own DNS resolver).

## Step 3: Role Installation & Domain Promotion
1. Utilized Server Manager to perform a role-based installation of **Active Directory Domain Services (AD DS)** and the **DNS Server** role.
2. Promoted the server to a Domain Controller, establishing a new forest root domain: `fenixbank.local`.
3. Created the initial Domain Administrator "break-glass" recovery credentials.

## Step 4: Organizational Architecture (IAM)
Configured the logical directory structure to simulate a multi-departmental financial institution.
1. Opened **Active Directory Users and Computers (ADUC)**.
2. Designed an Organizational Unit (OU) hierarchy to separate assets and users for future Group Policy enforcement:
   * `_Fenix_Tellers`
   * `_Fenix_IT_Security`
   * `_Fenix_Workstations`
3. Provisioned standard test user accounts (e.g., a simulated Bank Teller) within their respective OUs.

## Phase 2 Validation
* **Status:** Complete.
* **Evidence:** `Fenix-DC01` is actively resolving DNS queries and successfully managing the `fenixbank.local` domain space. 

---
### 📸 Architecture Screenshots
# Creating the VM

<img width="790" height="558" alt="Fenix-DC01-OS" src="https://github.com/user-attachments/assets/c122e59e-fe44-4a94-b792-11fa3b3594b6" />
<img width="790" height="558" alt="Fenix-DC01-Disk" src="https://github.com/user-attachments/assets/66ae6eac-7fdd-42c8-9036-7a3680919980" />
<img width="792" height="559" alt="Fenix-DC01-RAM" src="https://github.com/user-attachments/assets/32246f33-101d-4364-bf7f-a309970e3d8c" />

# Server Network Config
<img width="1025" height="853" alt="Fenix-DC01-Network-Config" src="https://github.com/user-attachments/assets/6018c9a7-597d-42ff-8c85-8e733b0f79d2" />

# Promoting to Active Directory - Setup & Install
<img width="1026" height="850" alt="Fenix-DC01-Promote-to-AD-DS" src="https://github.com/user-attachments/assets/b0e577cd-828c-4543-885d-38f59ae34710" />
<img width="1025" height="850" alt="Fenix-DC01-DNS" src="https://github.com/user-attachments/assets/c1d93fed-3ddc-4782-9d8e-2ea7092cffb4" />
<img width="1025" height="851" alt="Fenix-DC01-Deployment-Forest" src="https://github.com/user-attachments/assets/2697f762-a933-49b0-b72f-d346821cb91e" />

# Active Directory Users and Computers, OUs & Users
<img width="1023" height="853" alt="Fenix-DC01-ActiveDir-OUs-and-Users" src="https://github.com/user-attachments/assets/71832b60-b0d1-4680-9e91-25e31585b97c" />



