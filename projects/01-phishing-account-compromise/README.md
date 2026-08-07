# PHISH-001 — Phishing → Account Compromise

> **SOC Investigation Case Study**

| Field | Value |
|---|---|
| Case ID | PHISH-001 |
| Severity | TBD |
| Status | 🟡 Investigation in progress |
| Initial Detection | User-reported suspicious email |
| Primary Platform | Splunk SIEM |
| Investigation Goal | Trace attacker activity |

---

## 1. Executive Summary

This case study documents an end-to-end SOC investigation beginning with a user-reported phishing email.

The objective is to determine whether the message was malicious, extract indicators of compromise (IOCs), correlate those indicators with security telemetry in Splunk, and reconstruct the attacker's activity to determine whether the target account was compromised.

**Final verdict:** Pending investigation.

---

## 2. Incident Scenario

A fictional employee reports receiving a suspicious email that appears designed to trick the user into interacting with an attacker-controlled resource.

The SOC analyst receives the report as the initial alert and begins triage using the available email headers and message content.

### Investigation Workflow

```text
User Report
     ↓
Initial Triage
     ↓
Email Analysis
     ↓
IOC Extraction
     ↓
Splunk Correlation
     ↓
Authentication Investigation
     ↓
Attack Timeline
     ↓
MITRE ATT&CK Mapping
     ↓
Incident Response
     ↓
Detection Improvement
