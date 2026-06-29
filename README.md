# Wazuh-Detection-Engineering-Lab
A SOC Environment Created For Evan Youssefs' Resume.

# Wazuh Detection Engineering Lab

## Overview

This repository documents the design, implementation, and validation of a Detection Engineering laboratory using **Wazuh SIEM**, **Sysmon**, **Windows 11**, **Ubuntu Server**, **Kali Linux**, and **VMware Workstation**.

The purpose of this project is to simulate real-world attacker techniques, collect endpoint telemetry, develop custom Wazuh detection rules, and validate detections using the **MITRE ATT&CK Framework**.

This project demonstrates practical Security Operations Center (SOC) and Detection Engineering skills through hands-on attack simulation, log analysis, custom rule development, and incident investigation.

---

# Objectives

* Build an enterprise-style SIEM lab
* Configure Wazuh Manager, Indexer, and Dashboard
* Deploy Windows endpoints with Sysmon and the Wazuh Agent
* Generate realistic attack activity
* Develop custom Wazuh detection rules
* Validate detections using endpoint telemetry
* Map detections to the MITRE ATT&CK Framework
* Document each detection with screenshots, attack simulations, and technical analysis

---

# Lab Architecture

Host Machine

* Windows 11
* VMware Workstation

Virtual Machines

* Ubuntu Server

  * Wazuh Manager
  * Wazuh Dashboard
  * Wazuh Indexer
* Windows 11

  * Sysmon
  * Wazuh Agent
* Kali Linux

  * Attack Simulation

---

# Technologies Used

## Operating Systems

* Ubuntu Server
* Windows 11
* Kali Linux

## Security Tools

* Wazuh SIEM
* Sysmon
* PowerShell
* MITRE ATT&CK Framework

## Virtualization

* VMware Workstation

## Languages

* XML
* PowerShell
* Linux Bash

## Investigation Tools

* Discover (Wazuh Dashboard)
* DQL (Dashboard Query Language)

---

# Detection Coverage

## Execution

* ✅ Encoded PowerShell Execution
* ⏳ PowerShell Download Cradle (Invoke-WebRequest)
* ⏳ Invoke-Expression (IEX)
* ⏳ Suspicious cmd.exe Execution

## Defense Evasion

* ⏳ mshta.exe
* ⏳ regsvr32.exe
* ⏳ rundll32.exe

## Persistence

* ⏳ Registry Run Keys
* ⏳ Scheduled Tasks

## Credential Access

* ⏳ LSASS Memory Access
* ⏳ Mimikatz Indicators

## Discovery

* ⏳ Network Discovery
* ⏳ SMB Share Enumeration

## Lateral Movement

* ⏳ PsExec
* ⏳ Remote Desktop (RDP)

---

# Detection Methodology

Each detection follows the same workflow:

1. Simulate attacker behavior
2. Collect endpoint telemetry using Sysmon
3. Forward logs through the Wazuh Agent
4. Analyze telemetry within Wazuh
5. Develop a custom detection rule
6. Validate successful detection
7. Document findings
8. Map the technique to MITRE ATT&CK

---

# Sample Detection

## Detection

PowerShell Base64 Encoded Command Execution

### MITRE ATT&CK

Technique:

* T1059.001 – PowerShell

Tactic:

* Execution

### Attack Simulation

```
powershell.exe -EncodedCommand RwBlAHQALQBEAGEAdABlAA==
```

### Result

* Successfully detected using Sysmon Event ID 1
* Custom Wazuh detection rule created
* Detection validated through the Wazuh Dashboard

---

# Skills Demonstrated

* Detection Engineering
* Security Monitoring
* Threat Detection
* SIEM Administration
* Endpoint Telemetry
* Sysmon Configuration
* Wazuh Rule Development
* Windows Event Analysis
* MITRE ATT&CK Mapping
* DQL Querying
* XML Rule Development
* Linux Administration
* VMware Virtualization
* Security Operations
* Incident Investigation

---

# Lessons Learned

Throughout this project I gained hands-on experience deploying and administering a SIEM environment, configuring endpoint telemetry with Sysmon, developing custom Wazuh detection rules, investigating Windows events, validating detections against simulated attacks, and mapping alerts to the MITRE ATT&CK framework. The project also strengthened troubleshooting, log analysis, and detection engineering skills.

---

# Future Enhancements

* Active Directory Integration
* Linux Endpoint Monitoring
* Sigma Rule Conversion
* Threat Intelligence Integration
* VirusTotal Integration
* Email Alerting
* SOAR Automation
* Additional Windows Endpoints
* Detection Tuning
* Dashboard Visualizations

---

# Disclaimer

This project is intended for educational purposes within an isolated virtual lab environment. All attack simulations are performed on systems owned and controlled by the author. No techniques demonstrated in this repository should be executed against systems without explicit authorization.
