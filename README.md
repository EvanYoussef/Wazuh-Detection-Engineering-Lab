# Detection 01 – Encoded PowerShell

## Objective

Detect PowerShell processes executing Base64 encoded commands.

## MITRE ATT&CK

- Tactic: Execution
- Technique: T1059.001 - PowerShell

## Attack Simulation

```powershell
powershell.exe -EncodedCommand RwBlAHQALQBEAGEAdABlAA==
