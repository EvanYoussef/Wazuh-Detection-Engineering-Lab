# Attack Simulation

## Objective

Simulate a failed SMB authentication attempt from a Kali Linux attacker system.

## MITRE ATT&CK

Technique: T1110 – Brute Force

Tactic: Credential Access

---

## Attack Command

```bash
smbclient -L //192.168.179.128 -U fakeuser
```

---

## Expected Telemetry

Windows Security Event

Event ID: 4625

Authentication Package: NTLM

Logon Type: 3

Source IP: 192.168.179.130

---

## Expected Detection

The custom Wazuh rule generates an alert for a failed network logon originating from the Kali Linux host.
