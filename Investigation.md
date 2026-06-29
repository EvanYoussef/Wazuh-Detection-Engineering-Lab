# Investigation

## Alert Summary

A suspicious execution of `mshta.exe` was detected.

---

## Telemetry Source

Microsoft-Windows-Sysmon

Event ID: 1

---

## Observed Fields

Image

```
C:\Windows\System32\mshta.exe
```

Command Line

```
mshta.exe javascript:close()
```

Parent Process

```
cmd.exe
```

Original File Name

```
MSHTA.EXE
```

---

## Detection Logic

The detection monitors Sysmon Process Creation events for executions of `MSHTA.EXE` with command-line arguments frequently associated with malicious activity.

---

## Why This Matters

MSHTA is a trusted Microsoft binary that attackers commonly abuse to execute:

- HTA files
- JavaScript
- VBScript
- Remote payloads

Using a legitimate Windows binary helps attackers evade application allowlisting and blend in with normal system activity.

---

## Analyst Response

Investigate:

- Parent process
- User account
- Command-line arguments
- Remote URLs
- Additional child processes
- Network connections

---

## MITRE ATT&CK

Technique

T1218.005 – Mshta

Tactic

Defense Evasion
