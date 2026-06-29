# Detection 03 – Suspicious MSHTA Execution

## Objective

Detect suspicious executions of `mshta.exe`, a Windows Living Off the Land Binary (LOLBin) commonly abused by attackers to execute malicious HTA applications, JavaScript, VBScript, or remotely hosted payloads.

---

## MITRE ATT&CK

**Tactic**

- Defense Evasion

**Technique**

- T1218.005 – Mshta

---

## Attack Simulation

The following commands were used during testing:

```cmd
mshta.exe about:blank
```

```cmd
mshta.exe javascript:close()
```

These commands are harmless but generate realistic telemetry associated with common attacker tradecraft.

---

## Detection Logic

This custom Wazuh rule monitors Sysmon Process Creation (Event ID 1) events and identifies executions of `MSHTA.EXE` with command-line arguments commonly associated with malicious activity, including:

- about:
- javascript:
- vbscript:
- http
- https
- .hta

---

## Validation

✅ Sysmon Event ID 1 Generated

✅ Wazuh Ingested the Event

✅ Custom Rule Triggered

✅ MITRE ATT&CK Mapping Verified

---

## Files

- Rule.xml
- Attack.md
- Investigation.md

---

## Analyst Recommendation

Because `mshta.exe` is frequently abused to execute remote scripts and bypass application controls, analysts should investigate:

- Parent process
- Command line arguments
- Remote URLs
- User account
- Integrity level
- Child processes
