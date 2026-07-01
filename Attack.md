# Attack Simulation

## Objective

Simulate execution of the Windows Rundll32 utility to validate detection logic.

## MITRE ATT&CK

Technique: T1218.011 – Rundll32

Tactic: Defense Evasion

---

## Test Command

```cmd
rundll32.exe shell32.dll,Control_RunDLL
```

---

## Expected Telemetry

- Sysmon Event ID 1
- Image = rundll32.exe
- OriginalFileName = RUNDLL32.EXE
- CommandLine containing DLL execution

---

## Expected Detection

The custom Wazuh rule generates an alert for suspicious Rundll32 execution.
