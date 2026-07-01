# Detection 05 – Failed SMB Network Authentication

## Objective

Detect failed SMB authentication attempts originating from a remote host using Windows Security Event ID 4625.

---

## MITRE ATT&CK

**Tactic**

- Credential Access

**Technique**

- T1110 – Brute Force

---

## Lab Environment

- Wazuh Manager (Ubuntu Server)
- Windows 11 Endpoint
- Kali Linux Attacker
- Sysmon
- VMware Workstation

---

## Attack Simulation

From the Kali Linux VM:

```bash
smbclient -L //192.168.179.128 -U fakeuser
```

An invalid username and password were intentionally supplied to generate a failed network logon.

---

## Detection Logic

The custom Wazuh rule detects:

- Windows Security Event ID 4625
- Network Logon (Type 3)
- Source IP Address: 192.168.179.130
- Failed NTLM authentication

---

## Validation

- ✅ Windows Security Event Generated
- ✅ Wazuh Alert Generated
- ✅ Custom Rule Triggered
- ✅ MITRE ATT&CK Mapping Verified

---

## Files

- Rule.xml
- Attack.md
- Investigation.md

---

## Analyst Recommendations

Investigate:

- Source IP address
- Username targeted
- Number of failed attempts
- Authentication package
- Related successful logons
- Possible brute-force activity
