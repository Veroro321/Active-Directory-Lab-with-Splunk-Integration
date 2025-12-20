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



<img width="503" height="558" alt="image" src="https://github.com/user-attachments/assets/93c0cfad-ba2b-4036-9be3-aac63669176a" />


[Uploading Untitled Diagram (2).drawio…]()


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
- Splunk Free
- Splunk Universal Forwarder

**Offensive Security / Attack Simulation**
- Kali Linux
- Crowbar (used to brute-force SSH authentication)

<img width="1215" height="334" alt="image" src="https://github.com/user-attachments/assets/8abfa251-3670-43fd-b25d-f75ead27d6ee" />

Example of the System, application, etc... being tracked on Splunnk
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
<img width="1024" height="768" alt="VirtualBox_ADDC01_20_12_2025_13_43_42" src="https://github.com/user-attachments/assets/3f9a11b6-9d8e-45c8-a652-4f9a0763e579" />
<img width="1024" height="768" alt="VirtualBox_ADDC01_20_12_2025_13_46_53" src="https://github.com/user-attachments/assets/bb6d417f-bc34-4593-a168-e0880839ee38" />


**Group Policy Objects**  


**Splunk Event Collection Dashboard**  
**Security Alerts Example**  

<img width="1232" height="327" alt="image" src="https://github.com/user-attachments/assets/22561904-3084-4da6-bbb9-553a136608cc" />



---

## Future Enhancements
- Expand lab to include **multi-domain or hybrid AD environments**  
- Integrate **SOAR tools** for automated response  
- Enhance dashboards with detailed **audit trails** and compliance reporting  

