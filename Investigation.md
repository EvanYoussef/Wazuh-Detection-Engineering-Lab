# Investigation

## Telemetry Source

Microsoft-Windows-Sysmon

Event ID: 1

## Detection Logic

The custom rule detects executions of schtasks.exe using the `/create` parameter, which may indicate an attempt to establish persistence through Windows Scheduled Tasks.

## MITRE ATT&CK

Technique: T1053.005

Tactic: Persistence

## Analyst Notes

Legitimate administrators also use schtasks.exe, so analysts should verify:
- Who created the task
- The task name
- The executable being launched
- Whether the activity aligns with expected administrative behavior
