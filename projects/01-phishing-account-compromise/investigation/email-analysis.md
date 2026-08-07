# Email Analysis

## Case ID

PHISH-001

## Initial Alert

A user reported receiving a suspicious Microsoft 365-style account verification email.

The SOC analyst received the report and began investigating the email for signs of phishing.

## Email Metadata

| Field | Value |
|---|---|
| From | security@micr0soft-example.test |
| Reply-To | account-review@identity-check.example.test |
| To | alex.morgan@northbridge-example.test |
| Subject | Action Required: Verify Your Microsoft 365 Account |
| Sending IP | 203.0.113.45 |

## Authentication Results

| Control | Result |
|---|---|
| SPF | FAIL |
| DKIM | NONE |
| DMARC | FAIL |

## Suspicious Indicators

- Sender domain visually resembles a trusted Microsoft domain.
- Reply-To uses a different domain.
- SPF authentication failed.
- DKIM was not present.
- DMARC authentication failed.
- Email creates urgency around account verification.
- The message contains an external login URL.

## Suspicious URL

```text
https://login.identity-check.example.test/verify
