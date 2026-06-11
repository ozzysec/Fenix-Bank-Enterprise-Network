# Phase 1: Infrastructure & Virtualization Setup

## Objective
To establish a secure, isolated virtual environment capable of hosting an enterprise domain network. This foundational phase ensures that all future virtual machines (VMs) can communicate internally while remaining logically separated from the physical host network.

## Step 1: Hypervisor Deployment
1. **Installed Oracle VirtualBox** as a Type 2 Hypervisor to allocate and manage host system resources.
2. **Installed the VirtualBox Extension Pack** to enable enterprise-grade hardware emulation, including support for USB 3.0 (xHCI), Remote Desktop Protocol (VRDP), and advanced disk encryption.

## Step 2: Virtual Network Configuration (The Backbone)
Instead of using standard isolated NAT connections, a dedicated logical network segment was created to simulate a corporate branch environment.
1. Navigated to VirtualBox **Network Manager** (via the Global Tools menu).
2. Created a new **NAT Network** and designated the name: `Bank_Corporate_LAN`.
3. Configured the **IPv4 Prefix (Network CIDR)** to `10.0.0.0/24`.
   * *Justification:* This utilizes a private, non-routable Class A IP block to mimic standard internal enterprise addressing and prevent IP conflicts with the external internet.
4. **Enabled DHCP** to allow automatic IP assignments for future standard client endpoints (e.g., Teller PCs).

## Step 3: Operating System Procurement
Created a centralized repository for official evaluation media to ensure standardized deployments.
1. Downloaded the **Windows Server 2022 (Desktop Experience) Evaluation ISO** to serve as the future Domain Controller.
2. Downloaded the **Windows 10 Enterprise 22H2 Evaluation ISO** to serve as the standard endpoint operating system for bank employees.

## Phase 1 Validation
* **Status:** Complete.
* **Evidence:** The NAT Network `Bank_Corporate_LAN` is active and configured to route `10.0.0.x` traffic exclusively within the isolated lab environment. 

---
### 📸 Architecture Screenshots
Hypervisor Deployment
<img width="1072" height="879" alt="Hypervisor-VirtualBox" src="https://github.com/user-attachments/assets/88038209-2122-45b9-8fc1-fc05011f2a90" />
Network Configuration NAT Network
<img width="960" height="754" alt="Fenix-NAT" src="https://github.com/user-attachments/assets/8703f0e8-78b6-4ebd-83c3-066a9f334807" />
ISO image files
<img width="1124" height="642" alt="Fenix-ISO" src="https://github.com/user-attachments/assets/4c1f7d34-e131-4fb3-802a-39684eef70f3" />


