# SOC Investigation Template

> **Purpose:** This template provides a repeatable structure for documenting SOC alerts and cybersecurity investigations.

## Alert Summary

| Field | Details |
|---|---|
| Alert Name |  |
| Alert Type |  |
| Date / Time |  |
| Severity | Low / Medium / High / Critical |
| Status | Open / Investigating / Escalated / Contained / Closed |
| Affected User |  |
| Affected Host |  |
| Source IP |  |
| Destination IP / Domain |  |
| Related Indicators |  |

## Initial Triage Questions

- What triggered the alert?
- Who or what asset is affected?
- Is this activity expected or unusual?
- Is there evidence of compromise?
- Are multiple users or systems affected?
- Is containment required?
- Should this be escalated?

## Evidence Reviewed

| Evidence Type | Notes |
|---|---|
| Authentication Logs |  |
| Endpoint Activity |  |
| Email Details |  |
| Network Connections |  |
| File Hashes |  |
| URLs / Domains |  |
| User Report |  |
| Related Alerts |  |

## Indicators of Compromise

| Indicator | Type | Notes |
|---|---|---|
|  | IP Address |  |
|  | Domain |  |
|  | URL |  |
|  | File Hash |  |
|  | Process |  |
|  | User Account |  |
|  | Hostname |  |

## Analysis

Explain what the evidence suggests.

Consider:

- Does the activity match normal behavior?
- Is there a known business reason for the activity?
- Are there signs of credential theft?
- Are there signs of malware execution?
- Are there signs of lateral movement?
- Are there repeated attempts or persistence indicators?
- What is the most likely explanation?

## Severity Reasoning

| Severity | Criteria |
|---|---|
| Low | Suspicious but low-confidence activity with limited impact |
| Medium | Suspicious activity affecting one user or asset with possible security impact |
| High | Likely compromise, malware execution, successful suspicious login, or active incident |
| Critical | Widespread compromise, ransomware, major outage, or confirmed business impact |

## Recommended Actions

- [ ] Validate whether the activity was expected
- [ ] Contact affected user or partner if needed
- [ ] Reset password if identity compromise is suspected
- [ ] Revoke active sessions if account compromise is suspected
- [ ] Isolate endpoint if malware is suspected
- [ ] Block malicious URL, domain, IP, or hash if confirmed
- [ ] Search for similar indicators across the environment
- [ ] Escalate to SOC or incident response team if needed
- [ ] Document all actions taken

## Escalation Decision

**Escalate:** Yes / No

**Reason:**

Explain why the issue should or should not be escalated.

## Partner-Friendly Summary

Write a short explanation that a non-technical customer or partner could understand.

## Closure Criteria

This investigation can be closed when:

- [ ] Alert has been reviewed
- [ ] Evidence has been documented
- [ ] Severity has been assigned
- [ ] Recommended actions have been provided
- [ ] Escalation decision has been documented
- [ ] Stakeholders have been updated
- [ ] No additional suspicious activity is observed

## Lessons Learned

Document what this alert reinforced or taught.
