# Email Analysis

> **Case ID:** PHISH-001  
> **Evidence Type:** User-reported phishing email  
> **Investigation Phase:** Initial Triage

---

## 1. Initial Alert

A user reported receiving a suspicious Microsoft 365-style account verification email.

The message appeared to request the user to verify their account through an external link.

The SOC analyst received the user report and began investigating the message to determine whether it was a phishing attempt.

---

## 2. Email Metadata

| Field | Value |
|---|---|
| From | TBD |
| Reply-To | TBD |
| To | TBD |
| Subject | TBD |
| Date/Time | TBD |
| Sending IP | TBD |
| Return-Path | TBD |
| Message-ID | TBD |

---

## 3. Email Authentication

| Authentication Control | Result | Analyst Observation |
|---|---|---|
| SPF | TBD | TBD |
| DKIM | TBD | TBD |
| DMARC | TBD | TBD |

These authentication results will be evaluated together with the sender domain, headers, message content, and infrastructure.

---

## 4. Header Analysis

The analyst will review the email headers for:

- Sender and Reply-To mismatches
- Suspicious originating IP addresses
- Unexpected mail servers
- Domain inconsistencies
- Authentication failures
- Unusual routing information
- Message-ID anomalies

### Findings

**Status:** Pending evidence collection.

---

## 5. Email Content Analysis

### Subject

**TBD**

### Sender

**TBD**

### Message Summary

**TBD**

### Social Engineering Indicators

The analyst will look for:

- Urgent account-verification requests
- Threats of account suspension
- Requests for credentials
- Unexpected login prompts
- Brand impersonation
- Suspicious links
- Mismatched sender information
- Unusual language or formatting

### Initial Assessment

**Status:** Suspicious — investigation in progress.

---

## 6. URL Analysis

| Indicator | Value | Assessment |
|---|---|---|
| URL | TBD | TBD |
| Domain | TBD | TBD |
| Redirect | TBD | TBD |
| Protocol | TBD | TBD |

The URL will be treated as a primary investigation pivot and correlated with Splunk telemetry.

---

## 7. IOC Extraction

| IOC Type | Indicator | Confidence | Source |
|---|---|---|---|
| Email Address | TBD | TBD | Email Header |
| Domain | TBD | TBD | Email URL |
| URL | TBD | TBD | Email Content |
| IP Address | TBD | TBD | Email Header |
| Hash | TBD | TBD | Attachment / Artifact |

---

## 8. Evidence Assessment

The analyst will correlate:

1. Email headers
2. Authentication results
3. Message content
4. URLs and domains
5. Extracted IOCs
6. Splunk telemetry

No final compromise verdict will be made from the email alone.

---

## 9. Analyst Conclusion

**Current Verdict:** Pending investigation.

The email will be classified as malicious, benign, or inconclusive after the available evidence has been analyzed and correlated with Splunk telemetry.

---

## 10. Next Investigation Step

Extract confirmed IOCs from the email and use them as investigation pivots in Splunk.

**Next phase:** IOC correlation and authentication investigation.
