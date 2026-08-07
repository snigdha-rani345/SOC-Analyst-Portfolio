# Splunk Investigation Queries

## Case ID

PHISH-001

## Investigation Objective

Use Splunk to determine whether the phishing email was followed by suspicious authentication activity.

## Query 1 — Find All Case Activity

```spl
index=phish001
| sort _time

index=phish001 event=authentication status=success
| table _time user src_ip location
| sort _time

index=phish001 user=alex.morgan
| table _time event status src_ip url rule
| sort _time

index=phish001 src_ip="203.0.113.45"
| table _time user event status src_ip
| sort _time
```
