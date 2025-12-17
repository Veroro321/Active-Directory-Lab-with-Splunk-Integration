# Active Directory Lab with Splunk Integration

![Project Banner](screenshots/banner.png)

## Overview

This project demonstrates a **lab environment simulating a real-world Active Directory (AD) infrastructure** integrated with **Splunk** for centralized logging and monitoring.  
It showcases user and group management, domain policies, and security monitoring through a SIEM platform.

**Key Features:**
- Active Directory domain setup with users, groups, and Organizational Units (OUs)  
- Group Policy Objects (GPOs) for security enforcement  
- Event collection from AD logs into Splunk  
- Realistic simulation of user activity and login events  
- Visualization of security events via Splunk dashboards  

---

## Table of Contents
1. [Lab Architecture](#lab-architecture)  
2. [Setup Instructions](#setup-instructions)  
3. [Simulated Scenarios](#simulated-scenarios)  
4. [Splunk Integration](#splunk-integration)  
5. [Screenshots](#screenshots)  
6. [Technologies Used](#technologies-used)  
7. [Future Enhancements](#future-enhancements)  

---

## Lab Architecture

![Architecture Diagram](screenshots/architecture.png)

- **VM1 – Windows Server (AD Domain Controller)**:  
  - Active Directory Domain Services installed  
  - User and group creation, OU management, GPO policies  
- **VM2 – Client VM (Windows 10/11)**:  
  - Joined to the AD domain  
  - Used to generate login and activity events  
- **VM3 – Splunk Server (Linux/Windows)**:  
  - Collects Windows Event Logs from AD  
  - Dashboards visualize authentication, user activity, and security alerts  

---

## Setup Instructions

### 1. Active Directory Environment
1. Install **Windows Server 2019/2022** on a VM.  
2. Add the **Active Directory Domain Services** role.  
3. Promote the server to a **Domain Controller**.  
4. Create users, groups, and Organizational Units.  
5. Configure Group Policies (password complexity, account lockout, etc.).

### 2. Splunk Integration
1. Install **Splunk Free** on a separate VM (Linux or Windows).  
2. Install the **Universal Forwarder** on AD VMs.  
3. Configure forwarding of Windows Event Logs (Security, System, Application).  
4. Create dashboards to monitor:
   - Failed logins  
   - Successful logins  
   - Privilege changes  
   - Group membership changes  

### 3. Simulated Security Events
- Failed login attempts (to trigger alerts)  
- User account creation/deletion  
- Privilege escalation  
- Group membership changes  

---

## Simulated Scenarios

| Scenario | Event Source | Detection in Splunk |
|----------|--------------|-------------------|
| Failed login | Security Event Log | Dashboard alert |
| Privilege escalation | Security Event Log | Automated search/report |
| User creation/deletion | AD logs | Dashboard visualization |
| Group policy changes | System logs | Splunk alert triggered |

---

## Splunk Integration

![Splunk Dashboard](screenshots/splunk_dashboard.png)

- Monitors real-time authentication events  
- Detects anomalies such as repeated failed logins or privilege changes  
- Provides visual analytics to track AD activity and potential security issues  

---

## Screenshots

1. Active Directory Users & Groups

![AD Users](screenshots/ad_users.png)

2. Group Policy Objects

![AD GPO](screenshots/ad_gpo.png)

3. Splunk Event Collection Dashboard

![Splunk Events](screenshots/splunk_events.png)

4. Security Alerts Example

![Splunk Alert](screenshots/splunk_alert.png)

---

## Technologies Used
- **Windows Server 2019/2022** – Active Directory domain controller  
- **Windows 10/11 Client VM** – Domain-joined endpoint  
- **Splunk Free** – SIEM platform for log collection and analysis  
- **Universal Forwarder** – Collects Windows Event Logs  
- **VirtualBox / VMware** – Virtualization platform for lab setup  

---

## Future Enhancements
- Add **more realistic attack simulations** (password spraying, brute force, phishing)  
- Integrate **SOAR workflows** to automate responses to detected incidents  
- Expand dashboards to include **audit trails, login patterns, and compliance reports**  
- Implement **multi-domain or hybrid AD environments** for enterprise-scale simulation  


