# PHISH-002 — PowerShell Event Analysis

## Case Information

| Field | Value |
|---|---|
| Case ID | PHISH-002 |
| Host | WS-FINANCE-07 |
| User | alex.morgan |
| Event ID | 4688 |
| Created Process | powershell.exe |
| Parent Process | WINWORD.EXE |
| Source IP | 203.0.113.50 |
| Destination Port | 443 |

## Initial Alert

The SOC received an alert for suspicious PowerShell execution on a Windows endpoint.

The available evidence shows that Microsoft Word launched PowerShell.

## Process Analysis

### Parent Process

```text
WINWORD.EXE
```

### Child Process

```text
powershell.exe
```

The parent-child relationship is important because Microsoft Word normally does not need to launch PowerShell during ordinary document viewing.

This relationship requires further investigation.

## Command-Line Analysis

Observed command line:

```text
powershell.exe -NoProfile -ExecutionPolicy Bypass -EncodedCommand <SIMULATED_BASE64>
```

### Observed Parameters

| Parameter | Observation |
|---|---|
| `-NoProfile` | Prevents PowerShell profile scripts from loading |
| `-ExecutionPolicy Bypass` | Attempts to bypass the normal PowerShell execution policy |
| `-EncodedCommand` | Indicates that the PowerShell command is encoded |

## Analyst Observation

The combination of a Microsoft Word parent process, PowerShell execution, an execution-policy bypass parameter, and an encoded command is suspicious.

The evidence does not by itself prove compromise. Additional endpoint and network telemetry should be correlated in Splunk.

## Network Indicator

Observed destination:

```text
203.0.113.50:443
```

This indicator should be investigated against other endpoint and authentication events.

## Initial Assessment

**Assessment:** Suspicious PowerShell activity.

**Confidence:** Medium

The activity contains multiple suspicious characteristics and requires additional investigation.

## Recommended Investigation

The next investigation should determine:

1. Whether the same host generated additional PowerShell events.
2. Whether the suspicious process created child processes.
3. Whether the destination IP appears elsewhere in the environment.
4. Whether additional users or endpoints contacted the same destination.
5. Whether the activity can be mapped to MITRE ATT&CK techniques.

## Evidence Source

```text
evidence/powershell-event.txt
```

> All data in this project is fictional and created for cybersecurity training.
