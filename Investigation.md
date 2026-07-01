# Investigation

## Alert Summary

A failed SMB authentication attempt was detected from the Kali Linux attacker VM.

---

## Telemetry Source

Windows Security Log

Event ID: 4625

---

## Observed Fields

**Target User**

```
fakeuser
```

**Authentication Package**

```
NTLM
```

**Logon Type**

```
3 (Network)
```

**Source IP**

```
192.168.179.130
```

**Status**

```
0xC000006D
```

**SubStatus**

```
0xC0000064
```

---

## Detection Logic

The custom Wazuh rule identifies failed NTLM network authentication attempts (Logon Type 3) originating from the Kali Linux attacker IP.

---

## Why This Matters

Repeated failed network logons can indicate:

- Brute-force attacks
- Password spraying
- Unauthorized SMB access attempts
- Credential guessing

Detecting these events early allows defenders to investigate before attackers obtain valid credentials.

---

## Analyst Response

Review:

- Source IP address
- Username targeted
- Number of failed attempts
- Authentication package
- Related successful logons (Event ID 4624)
- Additional activity from the same IP address

---

## MITRE ATT&CK

Technique

T1110 – Brute Force

Tactic

Credential Access
