# Alert 04: Brute-Force Authentication Alert

> **Project Note:** This is a simulated SOC alert write-up created for cybersecurity portfolio development. No real customer data, logs, credentials, or private information are included.

## Alert Summary

| Field | Details |
|---|---|
| Alert Name | Multiple Failed Login Attempts |
| Alert Type | Authentication / Brute Force |
| Severity | Medium |
| Status | Investigated |
| Affected User | admin@example.com |
| Source IP | 198.51.100.77 |
| Primary Concern | Repeated failed login attempts against a user account |

## Scenario

A SIEM-style alert was generated after multiple failed login attempts were observed against a single account within a short period.

The activity may indicate a brute-force attempt, password spraying, or a misconfigured service repeatedly attempting authentication.

## Simulated Authentication Events

| Time | User | Source IP | Result | Notes |
|---|---|---|---|---|
| 13:01 | admin@example.com | 198.51.100.77 | Failed | Invalid password |
| 13:02 | admin@example.com | 198.51.100.77 | Failed | Invalid password |
| 13:03 | admin@example.com | 198.51.100.77 | Failed | Invalid password |
| 13:04 | admin@example.com | 198.51.100.77 | Failed | Invalid password |
| 13:05 | admin@example.com | 198.51.100.77 | Failed | Invalid password |
| 13:07 | admin@example.com | 198.51.100.77 | Blocked | Account protection triggered |

## Evidence Reviewed

| Evidence | Notes |
|---|---|
| Repeated failed logins | Multiple attempts within short period |
| Same source IP | Attempts came from one source |
| Affected account | Admin-style account increases concern |
| Successful login | No successful login observed |
| Account lockout/block | Protection appears to have triggered |
| Other users affected | Requires environment-wide search |

## Indicators of Compromise

| Indicator | Type | Notes |
|---|---|---|
| 198.51.100.77 | IP Address | Source of repeated failed attempts |
| admin@example.com | User Account | Targeted account |
| Multiple failed logins | Authentication Pattern | Possible brute-force activity |
| Account protection triggered | Control Event | Indicates repeated failure threshold reached |

## Analysis

The alert shows repeated failed authentication attempts against an account that may have elevated privileges.

No successful login was observed in this simulated case, which lowers immediate compromise confidence. However, the targeted account name increases risk and should be reviewed carefully.

This could be malicious brute-force activity, password spraying, or a misconfigured service.

## Severity Reasoning

| Factor | Assessment |
|---|---|
| Repeated failed logins | Yes |
| Successful login observed | No |
| Privileged account targeted | Possible |
| Account protection triggered | Yes |
| Multiple users affected | Unknown |
| Severity | Medium |

## Recommended Actions

- [ ] Confirm whether the account is privileged
- [ ] Check whether any successful login followed the failed attempts
- [ ] Review whether other users were targeted by the same source IP
- [ ] Block or monitor the source IP if confirmed malicious
- [ ] Confirm account lockout and MFA policies
- [ ] Validate whether a misconfigured service caused the attempts
- [ ] Escalate if successful login occurs or multiple accounts are targeted

## Escalation Decision

**Escalate:** Conditional

**Reason:**

Escalate if the targeted account is privileged, if a successful login occurs, if multiple users are targeted, or if the activity continues after controls trigger.

## Partner-Friendly Summary

Multiple failed login attempts were observed against one account from the same source. No successful login was observed in this simulated case, but the activity may indicate a brute-force attempt.

Recommended next steps are to confirm whether the account is privileged, check for successful logins, review whether other users were targeted, and validate account protection controls.

## MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| Brute Force | Repeated authentication attempts may indicate password guessing |
| Password Spraying | Activity may be part of a broader credential attack |
| Valid Accounts | Successful login would indicate possible credential compromise |

## Lessons Learned

Failed login alerts require context. Multiple failures may not always mean compromise, but failed attempts against privileged accounts or followed by successful login activity should be escalated quickly.
