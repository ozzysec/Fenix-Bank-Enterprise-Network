# Fenix-Bank-Enterprise-Network
Creating a network simulating the enterprise architecture of a bank. 

# Fenix Bank: Simulated Enterprise Corporate Network

## Objective
The Fenix Bank project is a fully functional, simulated enterprise local area network (LAN) built from scratch within a hypervisor environment. The objective of this lab is to demonstrate hands-on proficiency in network architecture, Windows Server administration, Identity and Access Management (IAM), and defensive security monitoring (SIEM/Vulnerability Scanning). 

### Skills Learned
- Enterprise Network Architecture & Subnetting (`10.0.0.0/24`)
- Active Directory Domain Services (AD DS) setup and administration.
- Implementation of Role-Based Access Control (RBAC) and Group Policy Objects (GPOs).
- Security Information and Event Management (SIEM) log ingestion and alert configuration.
- Vulnerability management and GLBA compliance auditing.

### Tools Used
- **Hypervisor:** Oracle VirtualBox
- **Infrastructure:** Windows Server 2022 (Domain Controller), Windows 10 Enterprise (Endpoints)
- **Security Tools:** Splunk / Wazuh (SIEM), Nessus Essentials (Vulnerability Scanner)
- **Network Routing:** NAT Network Configuration & DHCP Management

---

## Network Topology & Architecture

<img width="2087" height="1703" alt="Fenix Bank Network Topology" src="https://github.com/user-attachments/assets/8fa2ba6d-1405-4093-99c3-79750d51e122" />

---

## Project Documentation by Phase

### Phase 1: Infrastructure Pre-computation & Virtualization
- Configured a private, isolated NAT network (`Bank_Corporate_LAN`) mapped to `10.0.0.0/24`.
- Allocated specific RAM and vCPU resources to balance host stability with lab efficiency.

### Phase 2: Active Directory & Domain Configuration
*(Link to a document or insert screenshots of your Fenix Bank AD layout here)*
- Promoted Windows Server 2022 to a Domain Controller (`fenixbank.local`).
- Created dedicated Organizational Units (OUs) for Retail Banking, Wealth Management, and IT Security.

### Phase 3: Endpoint Provisioning & Access Control
- Deployed Windows 10 Enterprise endpoints and joined them to the `fenixbank.local` domain. Ensuring seamless domain integration and unified security policy application
- Implemented Role-Based Access Control (RBAC) via NTFS permissions, strictly adhering to the principle of least privilege for sensitive teller, banker and financial data shares. 

### Phase 4: SIEM Deployment & Incident Response
*(Insert screenshot of Splunk dashboard triggering a brute force alert here)*
- Forwarded Windows Security Event logs to the centralized Watchtower SIEM.
- Simulated an insider threat/brute force attack by generating failed logon attempts.
- Integraded Wazuh/Splunk for centralized log aggregation, transforming raw Windows Event logs into actionable security telemetry.

### Phase 5: Vulnerability Assessment & Compliance
*(Link to exported Nessus PDF here)*
- Conducted credentialed vulnerability scans against endpoint machines.
- Drafted remediation strategies for identified CVEs to maintain financial compliance standards. Mapped security posture against GLBA compliance standards, demonstrating an understanding of regulatory requirements in financial IT
