# Active Directory Lab with Splunk Integration

<img width="440" height="440" alt="Splunk-Emblem" src="https://github.com/user-attachments/assets/b6226698-f577-42ea-9112-fd07c2c661d5" />

<img width="260" height="260" alt="R" src="https://github.com/user-attachments/assets/1538f034-af66-49ec-9623-fa575d2e4393" />


## Overview

This project demonstrates the design and implementation of an **isolated Active Directory (AD) laboratory environment** integrated with **Splunk** for centralized logging and monitoring.  
The lab simulates real-world enterprise IT infrastructure, supporting:

- User and group management  
- Domain policies and Group Policy Objects (GPOs)  
- Authentication monitoring  
- Security event collection and visualization  

The goal is to showcase practical skills in **Active Directory administration, SIEM monitoring, and security operations**, similar to workflows used by SOC, Incident Response, and IT Security teams.

---

## Lab Architecture

The lab consists of three fully isolated virtual machines configured on a host-only network:

| VM | Role |
|----|------|
| **Windows Server** | Domain Controller hosting Active Directory Domain Services (AD DS), managing users, groups, and GPOs |
| **Windows Client VM** | Domain-joined endpoint for simulating user activity |
| **Splunk Server** | Collects and visualizes Windows Event Logs from AD and client VMs |

![Architecture Diagram](screenshots/architecture.png)

All operations are performed in a **controlled, isolated environment** for safe experimentation.

---

## Tools & Technologies

**Active Directory & Windows**
- Windows Server 2019/2022 Evaluation  
- Windows 10/11 Client  
- Active Directory Domain Services (AD DS)  
- Group Policy Objects (GPOs)  

**SIEM / Monitoring**
- [Splunk Free](https://www.splunk.com/)  
- Splunk Universal Forwarder  

**Virtualization**
- VirtualBox / VMware Workstation  

---

## Lab Methodology

### 1. Environment Preparation
- Configured **host-only networking** to isolate lab environment  
- Created **VM snapshots** for rollback  
- Installed required Windows Server and Client VMs  
- Disabled unnecessary services to reduce log noise  

### 2. Active Directory Setup
- Installed **AD DS** on Windows Server VM  
- Promoted server to **Domain Controller**  
- Created **Organizational Units (OUs), users, and groups**  
- Configured **Group Policy Objects (GPOs)** for security (password complexity, account lockout, auditing)  

### 3. Simulated User Activity
- Generated successful and failed login attempts  
- Created, deleted, and modified user accounts  
- Executed privilege escalation and administrative tasks  
- Modified group memberships  

### 4. Splunk Integration
- Installed **Splunk Free** on a dedicated VM  
- Deployed **Splunk Universal Forwarder** on AD and client VMs  
- Collected **Windows Event Logs**: Security, System, Application  
- Created dashboards for:
  - Authentication monitoring  
  - Failed login detection  
  - Privilege escalation tracking  
  - Group membership and policy changes  

### 5. Security Monitoring and Analysis
- Monitored Splunk dashboards for anomalies and alerts  
- Validated log collection and event correlation  
- Simulated potential attack scenarios to test detection  

---

## Skills Demonstrated
- Active Directory deployment and administration  
- User and group management in enterprise environments  
- Group Policy Object configuration for security  
- Windows Event Log collection and SIEM monitoring  
- Splunk dashboard creation and alerting  
- Security monitoring and threat detection  
- Lab design and network isolation  
- Technical documentation and reporting  

---

## Project Outcomes
- Built a fully functional **isolated Active Directory lab**  
- Integrated AD with **Splunk** for centralized log collection and monitoring  
- Simulated real-world scenarios: login failures, privilege escalation, group changes  
- Produced dashboards and alerts suitable for SOC-style analysis  
- Created a **repeatable lab setup** for portfolio demonstration  

---

## Screenshots

**AD Users & Groups**  
![AD Users](screenshots/ad_users.png)

**Group Policy Objects**  
![AD GPO](screenshots/ad_gpo.png)

**Splunk Event Collection Dashboard**  
![Splunk Dashboard](screenshots/splunk_dashboard.png)

**Security Alerts Example**  
![Splunk Alert](screenshots/splunk_alert.png)

---

## Future Enhancements
- Expand lab to include **multi-domain or hybrid AD environments**  
- Simulate advanced attack scenarios (password spraying, brute force, phishing)  
- Integrate **SOAR tools** for automated response  
- Enhance dashboards with detailed **audit trails** and compliance reporting  



*Note: Replace `screenshots/*.png` with your actual images from the lab.*
