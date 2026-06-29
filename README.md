# Detection 02 – Scheduled Task Creation

## Objective

Detect the creation of Windows Scheduled Tasks using `schtasks.exe`.

## MITRE ATT&CK

- Tactic: Persistence
- Technique: T1053.005 – Scheduled Task

## Attack Simulation

```cmd
schtasks /create /tn "WazuhLabTask" /tr "notepad.exe" /sc once /st 23:59 /f
```

## Detection Logic

This custom Wazuh rule monitors Sysmon Process Creation (Event ID 1) events and alerts when `schtasks.exe` is executed with the `/create` argument.

## Validation

- ✅ Sysmon Event Generated
- ✅ Wazuh Alert Generated
- ✅ Custom Rule Triggered

## Files

- Rule.xml
- Attack.md
- Investigation.md
