# Attack Simulation

## Objective

Simulate suspicious execution of the Windows MSHTA utility.

## MITRE ATT&CK

Technique: T1218.005 – Mshta

Tactic: Defense Evasion

---

## Test Commands

```cmd
mshta.exe about:blank
```

```cmd
mshta.exe javascript:close()
```

---

## Expected Telemetry

- Sysmon Event ID 1
- Image = mshta.exe
- OriginalFileName = MSHTA.EXE
- CommandLine containing suspicious indicators

---

## Expected Detection

The custom Wazuh rule generates an alert for suspicious MSHTA execution.
