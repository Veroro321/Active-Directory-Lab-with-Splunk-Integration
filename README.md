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

The lab consists of four fully virtual machines:
<img width="461" height="573" alt="image" src="https://github.com/user-attachments/assets/d239554f-174f-4a84-b113-41f5e120cf0e" />




| VM | Role |
|----|------|
| **Windows Server** | Domain Controller hosting Active Directory Domain Services (AD DS), managing users, groups, and GPOs |
| **Windows Client VM** | Domain-joined endpoint for simulating user activity |
| **Splunk Server** | Collects and visualizes Windows Event Logs from AD and client VMs |
| **Kali Linux ** | This is the machine that we will conduct our brute force attacks to generate some data to go into SPLUNK |


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

<img width="1024" height="768" alt="lab2Screenshot 2024-12-20 133142" src="https://github.com/user-attachments/assets/1dbe47b6-c4ca-4d7c-99e0-668852b434b1" />

**Virtualization**
- VirtualBox 

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


**Group Policy Objects**  
<img width="250" height="357" alt="image" src="https://github.com/user-attachments/assets/e23647c5-72ee-4c97-b28c-5150fe95d2db" />

**Splunk Event Collection Dashboard**  
**Security Alerts Example**  

<img width="1232" height="327" alt="image" src="https://github.com/user-attachments/assets/22561904-3084-4da6-bbb9-553a136608cc" />



---

## Future Enhancements
- Expand lab to include **multi-domain or hybrid AD environments**  
- Integrate **SOAR tools** for automated response  
- Enhance dashboards with detailed **audit trails** and compliance reporting  

