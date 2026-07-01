# Detection 04 – Suspicious Rundll32 Execution

## Objective

Detect suspicious executions of `rundll32.exe`, a Windows Living Off the Land Binary (LOLBin) commonly abused by attackers to execute malicious DLLs and evade application controls.

---

## MITRE ATT&CK

**Tactic**

- Defense Evasion

**Technique**

- T1218.011 – Rundll32

---

## Attack Simulation

The following command was executed:

```cmd
rundll32.exe shell32.dll,Control_RunDLL
```

This command safely launches the Windows Control Panel while generating telemetry for detection testing.

---

## Detection Logic

The custom Wazuh rule monitors Sysmon Process Creation (Event ID 1) events and detects executions of `RUNDLL32.EXE` with command-line arguments commonly associated with DLL execution and LOLBin abuse.

---

## Validation

- ✅ Sysmon Event ID 1 Generated
- ✅ Wazuh Successfully Ingested Event
- ✅ Custom Rule Triggered
- ✅ MITRE ATT&CK Mapping Verified

---

## Files

- Rule.xml
- Attack.md
- Investigation.md

---

## Analyst Recommendations

When investigating Rundll32 activity, verify:

- Parent process
- DLL being executed
- Command-line arguments
- User context
- Child processes
- Network activity
