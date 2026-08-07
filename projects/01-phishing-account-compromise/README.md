# PHISH-001 — Phishing to Account Compromise

## Project Status

🟡 Investigation in progress

## Objective

Investigate a user-reported phishing email and determine whether it resulted in account compromise using Splunk SIEM.

## Investigation Flow

User Report  
↓  
Email Analysis  
↓  
IOC Extraction  
↓  
Splunk Investigation  
↓  
Attack Timeline  
↓  
MITRE ATT&CK Mapping  
↓  
Incident Response

## Primary Tool

**Splunk SIEM**

## Investigation Scenario

A user reports a suspicious Microsoft 365-style account verification email.

The SOC analyst investigates the email, extracts indicators of compromise (IOCs), and searches Splunk for related authentication activity.

The investigation will determine whether the phishing attempt resulted in account compromise.

## Key Questions

- Is the email malicious?
- What indicators can be extracted?
- Did the user interact with the phishing link?
- Was the account successfully accessed?
- What attacker activity occurred after the login?
- Can the activity be mapped to MITRE ATT&CK?
- What detection and response actions should be recommended?

## Evidence

Evidence will include:

- Simulated phishing email
- Email header analysis
- Extracted IOCs
- Splunk search results
- Attack timeline
- MITRE ATT&CK mapping
- Incident response recommendations

> **Note:** This is a controlled cybersecurity training project using fictional data. No real credentials or sensitive information are used.

---

**Status:** Investigation in progress.
