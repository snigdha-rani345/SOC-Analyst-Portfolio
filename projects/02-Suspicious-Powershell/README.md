# PHISH-002 — Suspicious PowerShell Activity Investigation

**Project Type:** SOC Investigation  
**SIEM:** Splunk  
**Platform:** Windows Endpoint  
**Status:** Investigation in Progress

## Project Objective

Investigate suspicious PowerShell activity detected on a Windows endpoint and determine whether the activity indicates a potential endpoint compromise.

The investigation demonstrates how a SOC analyst can use Windows endpoint telemetry and Splunk to identify suspicious process execution, investigate indicators, correlate related events, and determine the appropriate response.

## Scenario

A security alert is generated after a user opens a suspicious document.

The document launches PowerShell with an unusual command.

The SOC analyst must determine:

- Which user executed PowerShell?
- Which endpoint was involved?
- What process launched PowerShell?
- What command line was executed?
- Was the PowerShell activity suspicious?
- Did additional suspicious activity occur?
- Does the activity indicate possible endpoint compromise?

## Investigation Workflow

```text
Security Alert
      |
      v
PowerShell Event
      |
      v
Process Investigation
      |
      v
Parent and Child Process Analysis
      |
      v
Command-Line Analysis
      |
      v
IOC Extraction
      |
      v
Splunk Correlation
      |
      v
MITRE ATT&CK Mapping
      |
      v
Incident Response
```

## Tools

- Splunk SIEM
- Windows Event Logs
- PowerShell Event Logs
- MITRE ATT&CK

## Evidence

The investigation will use simulated Windows endpoint telemetry.

Evidence will include:

- PowerShell execution event
- Process creation event
- Command-line information
- Parent process information
- User information
- Hostname information
- Network-related indicators, if identified

> All data in this project is fictional and created for cybersecurity training.

## Key Investigation Questions

1. Which user executed PowerShell?
2. Which endpoint was involved?
3. What process launched PowerShell?
4. What command line was executed?
5. Was encoded or obfuscated PowerShell used?
6. Are there suspicious indicators in the command?
7. Did the activity lead to additional suspicious events?
8. Which MITRE ATT&CK techniques apply?
9. What containment actions should the SOC recommend?

## Project Structure

```text
02-suspicious-powershell/
|
|-- README.md
|
|-- evidence/
|   |-- powershell-event.txt
|
|-- investigation/
|   |-- event-analysis.md
|   |-- splunk-investigation.md
```

## Investigation Status

**Current Status:** Investigation not started.

The final assessment will be based on the evidence identified during the investigation.

## Skills Demonstrated

- SOC alert triage
- Windows event analysis
- PowerShell investigation
- Process analysis
- Command-line analysis
- IOC identification
- Splunk SIEM investigation
- MITRE ATT&CK mapping
- Incident response
- Evidence-based decision making
