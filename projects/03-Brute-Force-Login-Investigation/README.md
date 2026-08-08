# BRUTE-001 — Brute-Force Login Investigation

**Project Type:** SOC Investigation  
**Primary Tool:** Wazuh  
**Investigation Type:** Authentication Attack  
**Status:** Investigation in Progress

## Project Objective

Investigate repeated failed authentication attempts detected by Wazuh and determine whether the activity represents a brute-force attack against a user account or system.

The investigation will analyze authentication events, identify the source IP address, correlate failed and successful logins, and determine the appropriate SOC response.

## Scenario

A Wazuh alert is generated after multiple failed authentication attempts are detected against a monitored system.

The SOC analyst must determine:

- Which account was targeted?
- Which source IP generated the authentication attempts?
- How many failed login attempts occurred?
- Was a successful login observed after the failed attempts?
- Was the source IP associated with other suspicious activity?
- Does the activity indicate a possible brute-force attack?
- What response actions should be recommended?

## Investigation Workflow

```text
Wazuh Alert
      |
      v
Authentication Events
      |
      v
Failed Login Analysis
      |
      v
Source IP Investigation
      |
      v
Successful Login Correlation
      |
      v
User Account Analysis
      |
      v
Attack Assessment
      |
      v
SOC Response
```

## Tools

- Wazuh
- Linux Authentication Logs
- Windows Security Event Logs
- MITRE ATT&CK
- GitHub

## Evidence

The investigation will use simulated authentication telemetry.

Evidence will include:

- Failed authentication attempts
- Successful authentication event
- Username
- Source IP address
- Destination host
- Authentication timestamps
- Wazuh alert information

> All data in this project is fictional and created for cybersecurity training.

## Key Investigation Questions

1. Which account was targeted?
2. Which host was targeted?
3. What source IP generated the failed login attempts?
4. How many failed attempts occurred?
5. What time period did the activity occur over?
6. Was a successful login observed?
7. Did the same source IP target other accounts or hosts?
8. Does the activity indicate brute-force behavior?
9. Which MITRE ATT&CK technique applies?
10. What containment and response actions should the SOC recommend?

## Project Structure

```text
03-brute-force-login-investigation/
|
|-- README.md
|
|-- evidence/
|   |-- authentication-events.txt
|
|-- investigation/
|   |-- event-analysis.md
|   |-- wazuh-investigation.md
```

## Investigation Status

**Current Status:** Investigation not started.

The final assessment will be based on the authentication evidence and Wazuh alerts identified during the investigation.

## Skills Demonstrated

- SOC alert triage
- Authentication log analysis
- Brute-force detection
- Source IP investigation
- User account investigation
- Wazuh alert analysis
- MITRE ATT&CK mapping
- Incident response
- Evidence-based decision making
