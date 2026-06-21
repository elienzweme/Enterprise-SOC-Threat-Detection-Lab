# Enterprise SOC Threat Detection Lab

![Platform](https://img.shields.io/badge/Platform-VMware-blue)
![SIEM](https://img.shields.io/badge/SIEM-Splunk-orange)
![Telemetry](https://img.shields.io/badge/Telemetry-Sysmon-green)
![Directory](https://img.shields.io/badge/Directory-Active%20Directory-red)
![Attack](https://img.shields.io/badge/Attack-Kali%20Linux-purple)
![AI](https://img.shields.io/badge/AI-Llama%203-teal)
![Framework](https://img.shields.io/badge/Framework-MITRE%20ATT%26CK-darkred)
![Windows](https://img.shields.io/badge/Windows-Server%202025-lightgrey)
![Project](https://img.shields.io/badge/Project-Completed-brightgreen)

---
# Cover Page

<p align="center">
  <img src="images/cover-page.png" width="1000">
</p>

---

# Overview

This project demonstrates the design, deployment, and operation of a Security Operations Center (SOC) lab built using VMware Workstation Pro, Splunk Enterprise, Sysmon, Active Directory, Kali Linux, and Llama 3 AI.

The environment simulates a real-world enterprise network where security telemetry is collected, centralized, analyzed, and investigated through custom Splunk dashboards and threat detection use cases aligned with the MITRE ATT&CK framework.

The project focuses on:

- Security Monitoring
- Detection Engineering
- Threat Hunting
- Active Directory Monitoring
- Incident Investigation
- AI-Assisted Security Analysis
- MITRE ATT&CK Mapping

---

# Project Metrics

![Project Metrics](diagrams/project-metrics.png)

| Metric | Value |
|----------|----------|
| Project Duration | 1.5 Weeks |
| Estimated Build Time | 50–80 Hours |
| Virtual Machines | 5 |
| Dashboards Created | 7 |
| Detection Use Cases | 9 |
| MITRE Techniques Mapped | 8+ |
| Log Sources | Sysmon & Windows Security Logs |
| SIEM Platform | Splunk Enterprise |
| AI Model | Llama 3 |

---

# Lab Architecture

![Architecture Diagram](Docs/Lab%20Architechure.png)

## Security Monitoring Pipeline

![Security Monitoring Pipeline](diagrams/Security-Monitoring-Pipeline%20(2).png)

Kali Linux → Windows Endpoints → Sysmon → Windows Event Logs → Splunk Universal Forwarder → Splunk Enterprise → Dashboards → Alerts → Llama 3 AI Analysis

---

# Environment Setup

![Infrastructure Overview](diagrams/Infrastructure%20Overview%201.png)

## Virtual Machines

| Host | Operating System | Role |
|--------|--------|--------|
| DC01 | Windows Server 2025 | Domain Controller |
| Client01 | Windows 11 | Endpoint |
| Client02 | Windows 11 | Endpoint |
| Splunk01 | Ubuntu Server | SIEM Platform |
| Kali01 | Kali Linux | Attack Simulation |

## Network Configuration

![Network Architecture](diagrams/network-architecture.png)

| System | IP Address |
|----------|----------|
| DC01 | 192.168.10.10 |
| Splunk01 | 192.168.10.20 |
| Client01 | 192.168.10.100 |
| Client02 | 192.168.10.101 |
| Kali01 | 192.168.10.30 |

---

# Active Directory Configuration

Configured Active Directory Domain Services to simulate an enterprise environment.

## Domain

CORP.local

## Components

- Organizational Units (OUs)
- Security Groups
- Administrative Groups
- User Accounts
- Workstations
- Domain Controller

### Screenshot

<h3>Screenshot</h3>

<p align="center">
  <img src="images/ad-users-and-computers.png" width="1200">
</p>

---

# Sysmon Deployment

Sysmon was installed on all Windows systems using the SwiftOnSecurity configuration.

## Events Collected

- Event ID 1 – Process Creation
- Event ID 3 – Network Connection
- Event ID 11 – File Creation
- Event ID 13 – Registry Modification
- Event ID 22 – DNS Query

### Screenshot

![Sysmon Deployment](images/sysmon-running.png)

---

# Splunk Deployment

![Tools Used](diagrams/Tools%20Used.png)

Splunk Enterprise was installed on Ubuntu Server.

## Configuration

- Search & Reporting App
- Custom Indexes
- Dashboards
- Data Inputs
- Alerting

### Screenshot

![Splunk Deployment](images/splunk-home.png)

---

# Log Forwarding

Splunk Universal Forwarder was deployed to all Windows systems.

## Data Sources

- Windows Security Logs
- Sysmon Operational Logs
- Application Logs
- System Logs

### Verification Search

```spl
index=* | stats count by host
```

### Screenshot

![Log Verification](images/dc01-splunk-forwarder-running.png)

---

# Validation Results

## Event ID Distribution

![Event Validation](screenshots/EventID_Validation.png)

## Sysmon Event Visibility

![Sysmon Event](screenshots/Sysmon Event.png)

## Threat Hunting Validation

![Threat Hunting](screenshots/Threat-Hunting.png)

## PowerShell MITRE Detection

![PowerShell MITRE](screenshots/PowerShell MITRE.png)

---

# Dashboards

## 1. SOC Command Center

Provides centralized visibility across the entire SOC environment.

### Panels

- Total Events
- Hosts Reporting
- Active Alerts
- Event Volume Trend
- Top Hosts
- Top Processes
- Latest Events

![SOC Dashboard](dashboards/soc-comand-center.png)

---

## 2. Executive Security Dashboard

Provides management-level security visibility.

### Panels

- Total Security Events
- Reporting Hosts
- Data Sources
- Trend Analysis
- Latest Activity

![Executive Dashboard](dashboards/executive-security.png)

---

## 3. Authentication Dashboard

Monitors authentication activity.

### Panels

- Successful Logons
- Failed Logons
- Authentication Trend
- Top Targeted Accounts
- Top Failed Sources

![Authentication Dashboard](dashboards/authentication.png)

---

## 4. Endpoint Threat Dashboard

Monitors endpoint activity using Sysmon.

### Panels

- Process Creation
- Network Connections
- DNS Queries
- File Creations
- Registry Modifications

![Endpoint Dashboard](dashboards/endpoint-threat.png)

---

## 5. Threat Hunting Dashboard

Provides threat hunting visibility.

### Panels

- PowerShell Activity
- Suspicious Processes
- Encoded Commands
- Network Activity
- DNS Activity

![Threat Hunting Dashboard](dashboards/threat-hunting.png)

---

## 6. MITRE ATT&CK Monitoring Dashboard

Maps telemetry to MITRE ATT&CK techniques.

### Panels

- MITRE Technique Reference
- Sysmon Event Distribution
- PowerShell Activity
- Top Sysmon Processes
- Host Activity

![MITRE Dashboard](dashboards/mitre-att&ck-monitoring.png)

---

## 7. Active Directory Monitoring Dashboard

Monitors identity-related activity.

### Panels

- User Creation
- Group Membership Changes
- Account Lockouts
- Privileged Activity
- Computer Account Changes

![AD Dashboard](dashboards/active-directory-monitoring.png)

---

# Kali Attack Simulation

![Kali Attack Simulation](diagrams/Kali%20Attack%20Simulation.png)

Kali Linux was used to simulate attacker behavior against the enterprise environment.

Activities included:

- Host Discovery
- Port Scanning
- Service Enumeration
- Authentication Attacks
- Brute Force Simulations
- Detection Validation

---

# Detection Engineering

![Detection Engineering](diagrams/Detection%20Engineering.png)

## Use Cases Implemented

- Failed Login Detection
- Account Lockout Detection
- Password Spraying Detection
- New User Creation
- Group Membership Changes
- PowerShell Execution
- Suspicious Process Creation
- DNS Monitoring
- Registry Modifications

---

# Incident Investigation Example

## Failed Login Detection

### Detection Source

Authentication Dashboard

### Event ID

4625

### MITRE ATT&CK

T1110 – Brute Force

### Observation

Multiple failed login attempts were detected against domain user accounts.

### Investigation

- Reviewed Authentication Dashboard
- Identified source IP 192.168.10.101
- Correlated events with Kali Linux attack simulation
- Verified no successful authentication occurred

### Findings

![Investigation Findings](diagrams/Findings.png)

| Item | Result |
|--------|--------|
| Event ID | 4625 |
| Technique | T1110 – Brute Force |
| Source Host | Client02 |
| Source IP | 192.168.10.101 |
| Authentication Attempts | 16 Failed Logons |
| Successful Logons | None Observed |
| Risk Level | Medium |
| Investigation Status | Closed – Authorized Simulation |

### Outcome

Activity was determined to be an authorized brute-force simulation performed from Kali Linux.

### Analyst Recommendation

Monitor repeated failures and implement account lockout policies.

---

# MITRE ATT&CK Mapping

![MITRE ATT&CK Mapping](diagrams/MITRE%20ATT%26CK%20Mapping.png)

The lab maps Sysmon and Windows Security telemetry to MITRE ATT&CK techniques to improve threat detection and investigation workflows.

---

# AI-Powered Security Analysis

![AI Environment](diagrams/AI%20Environment.png)

![AI-Powered Security Analysis](diagrams/AI-Powered%20Security%20Analysis.png)

Llama 3 was integrated to assist with:

- Event Summarization
- Alert Triage
- Threat Explanation
- Investigation Assistance
- MITRE ATT&CK Mapping

---

# Skills Demonstrated

- Splunk Enterprise
- Detection Engineering
- Threat Hunting
- Incident Response
- Active Directory
- Sysmon
- Windows Security Monitoring
- SIEM Administration
- Log Analysis
- MITRE ATT&CK
- Kali Linux
- AI-Assisted Security Operations

---

# Lessons Learned

- SIEM deployment and management
- Endpoint telemetry collection
- Active Directory monitoring
- Threat detection engineering
- Log normalization
- Security dashboard development
- Investigation workflows

---

# Future Enhancements

- Sysmon Sigma Rule Integration
- Automated Alerting
- SOAR Integration
- Threat Intelligence Feeds
- Splunk Enterprise Security
- Multi-Domain Monitoring
- Detection-as-Code

---

# References

- Splunk Documentation
- Sysinternals Sysmon
- SwiftOnSecurity Sysmon Config
- MITRE ATT&CK Framework
- Microsoft Security Auditing Documentation
- VMware Workstation Pro Documentation

---

# Author

**Elie Nzweme**

Cybersecurity Portfolio Project

June 2026
