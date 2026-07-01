# Investigation

## Alert Summary

A suspicious execution of `rundll32.exe` was detected.

---

## Telemetry Source

Microsoft-Windows-Sysmon

Event ID: 1

---

## Observed Fields

**Image**

```
C:\Windows\System32\rundll32.exe
```

**Command Line**

```
rundll32.exe shell32.dll,Control_RunDLL
```

**Parent Process**

```
cmd.exe
```

**Original File Name**

```
RUNDLL32.EXE
```

---

## Detection Logic

The custom rule monitors Sysmon Process Creation events for executions of `RUNDLL32.EXE` with command-line arguments commonly associated with DLL execution and LOLBin abuse.

---

## Why This Matters

Attackers frequently abuse `rundll32.exe` to execute malicious DLLs while leveraging a trusted Microsoft binary to evade detection.

---

## Analyst Response

Investigate:

- Parent process
- DLL path
- Command-line arguments
- User account
- Child processes
- Network connections

---

## MITRE ATT&CK

Technique: T1218.011 – Rundll32

Tactic: Defense Evasion
