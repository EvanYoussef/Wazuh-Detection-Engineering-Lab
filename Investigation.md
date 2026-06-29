
### Put this in `Investigation.md`

```markdown
# Investigation

## Alert Summary

The custom Wazuh rule detected PowerShell executing a Base64 encoded command.

## Telemetry Source

- Source: Microsoft-Windows-Sysmon
- Event ID: 1
- Event Type: Process Creation
- Process: powershell.exe
- Command Line: powershell.exe -EncodedCommand RwBlAHQALQBEAGEAdABlAA==

## MITRE ATT&CK

- Technique: T1059.001 - PowerShell
- Tactic: Execution

## Analyst Notes

Encoded PowerShell is commonly used by attackers to hide command intent. This detection alerts when PowerShell is launched with encoded command parameters.
