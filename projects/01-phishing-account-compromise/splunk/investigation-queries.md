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

- Timestamp:
- Event Type:
- Username:
- Source IP:
- Authentication Status:
- Location:
- URL / Rule:
- Other Relevant Information:

## Analyst Analysis

This query provides the initial timeline of events associated with the case.
The returned events should be reviewed chronologically to identify activity
that may be related to the phishing incident.

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

![Query 1 - Find All Case Activity](./screenshots/Query-02.png)

## Event Details

- Timestamp:
- Username:
- Source IP:
- Location:
- Authentication Status:
- Authentication Event:
- Other Relevant Information:

## Analyst Analysis

This query identifies successful authentication events associated with the
investigation. The results provide the timestamp, username, source IP
address, and location of successful authentication activity.

These events should be correlated with the phishing timeline to determine
whether the successful authentication occurred after the phishing activity
and whether the source IP or location appears unusual.
---


