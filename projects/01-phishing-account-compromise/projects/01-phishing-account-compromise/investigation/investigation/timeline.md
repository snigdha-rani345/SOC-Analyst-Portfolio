# PHISH-001 — Attack Timeline

> **Case ID:** PHISH-001  
> **Investigation:** Phishing → Account Compromise  
> **SIEM:** Splunk

## Timeline

| Time (UTC) | Event | Source | Analyst Interpretation |
|---|---|---|---|
| 09:14:32 | Suspicious email received | Email telemetry | Initial phishing event |
| 09:17:08 | User clicked phishing URL | Web/activity telemetry | Possible credential-harvesting interaction |
| 09:19:41 | Successful authentication | Authentication telemetry | Suspicious login after phishing interaction |
| 09:21:03 | Second successful authentication | Authentication telemetry | Continued activity from suspicious source |
| 09:22:17 | New session created | Authentication telemetry | Possible attacker session |
| 09:23:55 | Mailbox rule created | Mailbox telemetry | Possible post-compromise activity |
| 09:25:12 | Failed authentication | Authentication telemetry | Possible follow-up access attempt |
| 09:26:44 | Failed authentication | Authentication telemetry | Repeated suspicious authentication |

## Key Correlation

```text
Phishing Email
      ↓
User Clicked Suspicious URL
      ↓
Successful Authentication
      ↓
Suspicious Source IP
      ↓
New Session
      ↓
Mailbox Rule Creation
      ↓
Additional Failed Login Attempts
