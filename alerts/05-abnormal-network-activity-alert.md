# Alert 05: Abnormal Network Activity Alert

> **Project Note:** This is a simulated SOC alert write-up created for cybersecurity portfolio development. No real customer data, packet captures, credentials, or private information are included.

## Alert Summary

| Field | Details |
|---|---|
| Alert Name | Suspicious Outbound Network Connection |
| Alert Type | Network / Possible Command and Control |
| Severity | Medium |
| Status | Investigated |
| Affected Host | DESKTOP-042 |
| Destination IP | 203.0.113.88 |
| Primary Concern | Suspicious outbound traffic from workstation |

## Scenario

A network monitoring alert identified repeated outbound connections from a workstation to an unfamiliar external IP address.

The activity occurred shortly after suspicious endpoint behavior was observed on the same host, increasing concern that the outbound traffic may be related to malware or unauthorized communication.

## Simulated Network Events

| Time | Source Host | Source IP | Destination IP | Port | Protocol | Notes |
|---|---|---|---|---|---|---|
| 10:16 | DESKTOP-042 | 10.0.0.42 | 203.0.113.88 | 443 | HTTPS | First outbound connection |
| 10:18 | DESKTOP-042 | 10.0.0.42 | 203.0.113.88 | 443 | HTTPS | Repeated connection |
| 10:20 | DESKTOP-042 | 10.0.0.42 | 203.0.113.88 | 443 | HTTPS | Continued beacon-like activity |
| 10:25 | DESKTOP-042 | 10.0.0.42 | 203.0.113.88 | 443 | HTTPS | Requires endpoint correlation |

## Evidence Reviewed

| Evidence | Notes |
|---|---|
| Repeated outbound connections | Connections repeated over short time period |
| Unknown destination | Destination not identified as known business service |
| Same affected host | Host also appeared in endpoint alert scenario |
| Common HTTPS port | Port 443 can be used by legitimate or malicious traffic |
| Process responsible | Requires endpoint process correlation |
| Domain reputation | Requires review if domain is available |

## Indicators of Compromise

| Indicator | Type | Notes |
|---|---|---|
| 203.0.113.88 | IP Address | Simulated suspicious destination |
| DESKTOP-042 | Host | Source of repeated outbound connections |
| Port 443 | Network Port | Common web traffic port; requires context |
| Repeated connections | Pattern | May indicate beaconing or automated communication |

## Analysis

The repeated outbound connections are suspicious because they involve an unfamiliar destination and occur shortly after suspicious endpoint activity on the same host.

The use of HTTPS does not confirm malicious behavior by itself. However, when combined with endpoint execution activity, the network behavior should be reviewed as potentially related to malware communication.

The next step is to correlate the traffic with endpoint process activity and determine whether the destination is known, expected, or malicious.

## Severity Reasoning

| Factor | Assessment |
|---|---|
| Repeated outbound traffic | Yes |
| Unknown destination | Yes |
| Related endpoint alert | Yes |
| Confirmed malicious reputation | Unknown |
| Data exfiltration confirmed | No |
| Severity | Medium, escalate to High if linked to malware |

## Recommended Actions

- [ ] Identify the process responsible for the connection
- [ ] Review destination IP/domain reputation
- [ ] Check whether destination is business-related
- [ ] Correlate with endpoint alert activity
- [ ] Review DNS and HTTP/S logs if available
- [ ] Block destination if confirmed malicious
- [ ] Isolate endpoint if malware communication is suspected
- [ ] Search for other hosts connecting to same destination
- [ ] Escalate if traffic is linked to malware or data exfiltration

## Escalation Decision

**Escalate:** Conditional

**Reason:**

Escalate if the destination is confirmed malicious, if traffic is linked to suspicious process activity, if multiple hosts are communicating with the same destination, or if data exfiltration is suspected.

## Partner-Friendly Summary

A workstation was observed making repeated outbound connections to an unfamiliar external destination. This may be legitimate traffic, but because it occurred near suspicious endpoint activity, further review is recommended.

Recommended next steps are to identify the responsible process, review the destination reputation, check whether other hosts are making similar connections, and isolate the endpoint if the activity is linked to malware.

## MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| Application Layer Protocol | HTTPS may be used for external communication |
| Command and Control | Repeated outbound traffic may indicate beaconing |
| Exfiltration Over Web Service | External communication may require data exposure review |
| Ingress Tool Transfer | Related endpoint activity may involve downloaded payloads |

## Lessons Learned

Network alerts require context. An outbound HTTPS connection is not automatically malicious, but repeated connections to an unfamiliar destination become more concerning when tied to suspicious endpoint activity.
