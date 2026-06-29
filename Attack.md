# Attack Simulation

## Objective

Simulate an attacker creating a scheduled task for persistence.

## MITRE ATT&CK

Technique: T1053.005 - Scheduled Task

Tactic: Persistence

## Command Used

```cmd
schtasks /create /tn "WazuhLabTask" /tr "notepad.exe" /sc once /st 23:59 /f
```

## Expected Result

Sysmon logs a Process Creation (Event ID 1).

The Wazuh Manager evaluates the event.

The custom detection rule generates an alert.
