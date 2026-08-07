# Splunk Investigation Queries

## Case ID

PHISH-001

## Investigation Objective

Use Splunk to determine whether the phishing email was followed by
suspicious authentication activity. The investigation focuses on identifying
the affected user, authentication activity, source IP addresses, locations,
and other related indicators.

# Query 1 - Find All Case Activity

## Purpose

Identify all available events related to the investigation and establish
the initial timeline of activity.

## Splunk Query

```spl
index=phish001
| sort _time
```

## Screenshot

![Query 1 - Find All Case Activity](./screenshots/Query-01.png)

## Event Details

- Timestamp:  Multiple events returned; review chronologically
- Event Type:  Email and authentication-related events
- Username:  Visible in the returned event data
- Source IP:  Authentication events contain source IP information
- Authentication Status:  Authentication activity is present in the results
- Location:  Available in the authentication event data
- URL / Rule:  Phishing-related email and authentication indicators are present
- Other Relevant Information:  The results establish the initial timeline for the investigation, including the phishing email and subsequent account activity.

## Analyst Analysis

The query returns the available events associated with the PHISH-001
investigation in chronological order.

The results show phishing-related email activity followed by authentication
events. These events provide the initial timeline needed to correlate the
suspected phishing email with subsequent account activity.

The authentication events should be examined further for the affected user,
source IP address, location, and authentication status to determine whether
the activity is suspicious.

---

# Query 2 — Identify Successful Authentication

## Purpose

Identify successful authentication events associated with the investigation.

## Splunk Query

```spl
index=phish001 event=authentication status=success
| table _time user src_ip location
| sort _time
```

## Screenshot

![Query 2 - Successful Authentication](./screenshots/Query-02.png)

## Event Details

- Timestamp: 2026-08-07 14:49:41 and 2026-08-07 14:51:03
- Username: alex.morgan
- Source IP: 203.0.113.45
- Location: unknown
- Authentication Status: Success
- Authentication Event: Successful authentication
- Other Relevant Information: Two successful authentication events were returned for the affected user.

## Analyst Analysis

This query identified two successful authentication events associated with
the user alex.morgan.

The events occurred at 14:49:41 and 14:51:03 on 2026-08-07. The presence of
multiple successful authentication events provides evidence of account
activity that should be correlated with the phishing timeline.

The source IP address and location should be reviewed in Splunk to determine
whether the authentication activity originated from an expected source.

---
# Query 3 — Investigate User Activity

## Purpose

Review activity associated with the affected user account and identify
authentication or other events that may be related to the phishing incident.

## Splunk Query

```spl
index=phish001 user=alex.morgan
| table _time event status src_ip url rule
| sort _time
```
## Screenshot

![Query 1 - Find All Case Activity](./screenshots/Query-03.png)

### Event Details

- Event ID: PHISH-001-USER-ACTIVITY
- Timestamp: 2026-08-07 14:44:32 to 14:56:44
- Username: alex.morgan
- Event Type: email_received, url_clicked, authentication, session_created, mailbox_rule_created
- Event Status: Successful and failed authentication activity observed
- Source IP:
  - 10.10.20.45 — URL click activity
  - 203.0.113.45 — Successful authentication and session activity
  - 198.51.100.77 — Failed authentication attempts
- URL: https://login.identity-check.example.test/verify
- Detection Rule: Move messages to RSS Feeds
- Other Relevant Information:
  - Phishing email received at 14:44:32.
  - Suspicious URL clicked at 14:47:08.
  - Successful authentication occurred at 14:49:41 and 14:51:03.
  - A session was created at 14:52:17.
  - A mailbox rule was created at 14:53:55.
  - Failed authentication attempts were observed at 14:55:12 and 14:56:44.

### Analyst Analysis

The activity for user alex.morgan shows a chronological sequence beginning with a phishing email, followed by a suspicious URL click and successful authentication activity.

Two successful authentication events were observed after the URL click. A session was subsequently created, followed by the creation of a mailbox rule. Additional failed authentication attempts were then observed from a different source IP address.

The sequence of events is consistent with potentially suspicious account activity following the phishing event. The authentication sources and mailbox rule activity should be further correlated with the other case evidence.

# Query 4 — Investigate Source IP Activity

## Purpose

Identify activity associated with a suspicious source IP address.

## Splunk Query

```spl
index=phish001 src_ip="203.0.113.45"
| table _time user event status src_ip
| sort _time
```

## Screenshot

![Query 4 - Source IP Activity](./screenshots/Query-04.png)

### Event Details

- Event ID: PHISH-001-AUTHENTICATION
- Timestamp:
  - 2026-08-07 14:49:41
  - 2026-08-07 14:51:03
  - 2026-08-07 14:52:17
- Username: alex.morgan
- Source IP: 203.0.113.45
- Event Type:
  - authentication
  - authentication
  - session_created
- Authentication Status: Success
- Related Activity: Two successful authentication events were followed by a session creation event.
- Other Relevant Information: All three events originate from the same source IP address.

### Analyst Analysis

The query identifies three events associated with user alex.morgan from source IP 203.0.113.45.

Two successful authentication events occurred at 14:49:41 and 14:51:03. These were followed by a session_created event at 14:52:17.

The sequence indicates that successful authentication was followed by the creation of an active session. Because this activity occurred in the context of the phishing investigation, the source IP and authentication events should be correlated with the phishing URL activity and other account activity to determine whether the access was authorized.
---

# Query 5 — Authentication Activity by Source IP

## Purpose

Identify authentication activity by user, source IP, and authentication
status.

## Splunk Query

```spl
index=phish001 event=authentication
| stats count by user src_ip status
| sort -count
```

## Screenshot

![Query 5 - Authentication Activity](./screenshots/Query-05.png)

## Event Details

- **Event ID:**
- **Username:**
- **Source IP:**
- **Authentication Status:**
- **Event Count:**
- **Suspicious Pattern:**
- **Other Relevant Information:**

## Analyst Analysis

This query summarizes authentication activity by user, source IP, and
status. The results can help identify repeated authentication attempts,
successful logins, or unusual authentication patterns.

---

# Query 6 — Authentication Timeline

## Purpose

Create a chronological view of authentication events associated with the
investigation.

## Splunk Query

```spl
index=phish001 event=authentication
| table _time user status src_ip location
| sort _time
```

## Screenshot

![Query 6 - Authentication Timeline](./screenshots/Query-06.png)

## Event Details

- **Event ID:**
- **Timestamp:**
- **Username:**
- **Authentication Status:**
- **Source IP:**
- **Location:**
- **Relationship to Phishing Event:**
- **Other Relevant Information:**

## Analyst Analysis

This query provides a chronological view of authentication activity. The
Event ID and timestamp help establish the sequence of events and determine
whether suspicious authentication occurred after the phishing activity.

---

# Investigation Findings

## Key Findings

- **Phishing Activity:**
- **Affected User:**
- **Successful Authentication:**
- **Suspicious Source IP:**
- **Geographic Information:**
- **Important Event IDs:**
- **Important Timeline Events:**

## Final Assessment

**Case Status:** [Confirmed Compromise / Suspicious Activity / No Evidence of Compromise]

**Affected User:** [User]

**Suspicious Source IP:** [IP Address]

**Primary Event ID:** [Event ID]

**Primary Evidence:** [Important evidence identified from Splunk]

**Recommended Action:** [Recommended response]

---

# Conclusion

The investigation used Splunk to correlate phishing-related activity with
authentication events, user activity, source IP addresses, Event IDs, and
timestamps.

The final conclusion should be based on the evidence observed in the Splunk
screenshots and the corresponding event analysis documented above.

