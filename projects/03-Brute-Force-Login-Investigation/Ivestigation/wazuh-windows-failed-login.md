# Windows Failed Logon Evidence

## Event Summary

This evidence was collected from the Windows endpoint monitored by Wazuh.

- **Event Type:** Failed Windows Logon
- **Windows Event ID:** 4625
- **Agent:** Windows
- **Agent ID:** 004
- **Detection Platform:** Wazuh
- **Authentication Result:** Failed
- **Purpose:** Controlled SOC lab investigation

## Investigation Evidence

The following screenshot shows the Windows failed-logon event detected by Wazuh.

![Windows Failed Logon Event](../Evidence/wazuh-windows-failed-login.png)

## Important Event Details

| Field | Value |
|---|---|
| Event ID | 4625 |
| Account | `<account shown in event>` |
| Source IP | `<source IP shown in event>` |
| Timestamp | `<timestamp shown in event>` |
| Logon Type | `<logon type shown in event>` |
| Failure Reason | `<failure reason shown in event>` |
| Host | Windows endpoint |

## Analysis

Event ID 4625 indicates that a Windows logon attempt failed.

A single failed authentication event does not by itself prove a brute-force attack. Multiple failed attempts occurring repeatedly within a short period, especially from the same source IP or against multiple accounts, would provide stronger evidence of brute-force behavior.

## SOC Assessment

The event is classified as:

**Failed Authentication Attempt — Requires Correlation**

Additional 4625 events should be correlated by:

- Source IP address
- Target username
- Number of attempts
- Time interval
- Target host
- Any subsequent successful Event ID 4624

## Evidence Status

- [x] Windows agent active
- [x] Wazuh receiving Windows telemetry
- [x] Failed-logon event identified
- [ ] Multiple failed attempts correlated
- [ ] Successful login correlation performed
- [ ] Final brute-force determination completed

## Conclusion

The observed Event ID 4625 confirms a failed Windows authentication attempt. Further event correlation is required before conclusively classifying the activity as a brute-force attack.
