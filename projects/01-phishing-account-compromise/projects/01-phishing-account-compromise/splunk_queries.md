# Email Analysis

> **Case ID:** PHISH-001  
> **Evidence Type:** User-reported phishing email  
> **Investigation Phase:** Initial Triage

---

## 1. Initial Alert

A user reported receiving a suspicious email that appeared to request interaction with an external login resource.

The SOC analyst received the report and began investigating the message to determine whether it represented a phishing attempt.

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

## 3. Authentication Results

| Control | Result |
|---|---|
| SPF | TBD |
| DKIM | TBD |
| DMARC | TBD |

These results will be evaluated together with the sender domain, headers, message content, and infrastructure.

---

## 4. Content Analysis

### Social Engineering Indicators

The analyst will review the message for:

- Urgency or pressure
- Credential requests
- Suspicious login prompts
- Unexpected links
- Impersonation of a trusted service
- Mismatched sender and reply-to addresses
- Suspicious wording or formatting

### URL Analysis

| Indicator | Value | Assessment |
|---|---|---|
| URL | TBD | TBD |
| Domain | TBD | TBD |
| Redirect | TBD | TBD |

---

## 5. IOC Extraction

Potential indicators identified during analysis:

| IOC Type | Indicator | Confidence |
|---|---|---|
| Email Address | TBD | TBD |
| Domain | TBD | TBD |
| URL | TBD | TBD |
| IP Address | TBD | TBD |
| Hash | TBD | TBD |

---

## 6. Analyst Assessment

**Current Assessment:** Pending evidence collection.

The email will not be classified as malicious solely because it appears suspicious. The analyst will correlate header information, message content, extracted indicators, and downstream security telemetry.

---

## 7. Evidence

Screenshots and sanitized email artifacts will be added after the lab evidence has been generated.

---

## 8. Next Investigation Step

Extract confirmed IOCs from the email and use them as pivots for the Splunk investigation.

**Next phase:** IOC correlation in Splunk.
