# Alert 02: Suspicious Login Alert

> **Project Note:** This is a simulated SOC alert write-up created for cybersecurity portfolio development. No real customer data, logs, credentials, or private information are included.

## Alert Summary

| Field | Details |
|---|---|
| Alert Name | Suspicious Successful Login |
| Alert Type | Identity / Authentication |
| Severity | High |
| Status | Escalated for Review |
| Affected User | user@example.com |
| Source IP | 198.51.100.44 |
| Primary Concern | Possible unauthorized account access |

## Scenario

A successful login was observed from an unfamiliar IP address and location shortly after a suspected phishing email was reported.

The login occurred outside the user's normal activity pattern and may indicate credential compromise.

## Simulated Authentication Events

| Time | User | Source IP | Location | Result | Notes |
|---|---|---|---|---|---|
| 08:58 | user@example.com | 203.0.113.25 | Seattle, WA | Success | Expected location |
| 09:04 | user@example.com | 198.51.100.44 | Unknown Region | Success | Suspicious source |
| 09:06 | user@example.com | 198.51.100.44 | Unknown Region | Success | Repeated suspicious login |
| 09:45 | user@example.com | 203.0.113.25 | Seattle, WA | Success | Normal location resumed |

## Evidence Reviewed

| Evidence | Notes |
|---|---|
| Successful login | Login succeeded from suspicious source |
| Unfamiliar IP address | Source IP does not match expected user behavior |
| Unusual location | Location inconsistent with normal activity |
| Recent phishing report | Possible credential exposure |
| MFA status | Requires review |
| Active sessions | Should be reviewed and revoked if unauthorized |

## Indicators of Compromise

| Indicator | Type | Notes |
|---|---|---|
| 198.51.100.44 | IP Address | Suspicious source IP in simulated case |
| Unknown Region | Location | Unusual compared to normal user location |
| Successful login | Authentication Event | Higher risk than failed login |
| Recent phishing activity | User Report | Possible credential theft vector |

## Analysis

The successful login from an unfamiliar location is suspicious, especially because it occurred shortly after a phishing email was reported.

A successful authentication event from an unusual source can indicate that an attacker obtained valid credentials and accessed the account.

This alert should be treated as high severity until the user confirms whether the login was legitimate.

## Severity Reasoning

| Factor | Assessment |
|---|---|
| Successful suspicious login | Yes |
| Unusual source IP | Yes |
| Unusual location | Yes |
| Related phishing activity | Yes |
| Possible credential compromise | Yes |
| Severity | High |

## Recommended Actions

- [ ] Contact the user to confirm whether the login was expected
- [ ] Reset the user's password if unauthorized
- [ ] Revoke active sessions
- [ ] Review MFA status and enforcement
- [ ] Review mailbox rules and forwarding
- [ ] Check for additional suspicious sign-ins
- [ ] Search for similar activity across other users
- [ ] Escalate if unauthorized access is confirmed

## Escalation Decision

**Escalate:** Yes

**Reason:**

The alert involves a successful login from an unfamiliar source with possible connection to phishing activity. Successful suspicious logins should be escalated because they may indicate active account compromise.

## Partner-Friendly Summary

A successful login was observed from an unfamiliar location and IP address. Because this activity does not match the user's expected behavior, it may indicate unauthorized account access.

Recommended next steps are to confirm whether the login was expected, reset the password if unauthorized, revoke active sessions, review MFA, and check mailbox rules for suspicious changes.

## MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| Valid Accounts | Attacker may have used stolen credentials |
| Phishing | Credentials may have been obtained through phishing |
| Account Discovery | Attacker may review account details after login |
| Email Collection | Mailbox access may expose email content |

## Lessons Learned

Successful suspicious logins should be prioritized because they may indicate that an attacker has already gained access. Password reset alone may not be enough if active sessions remain valid, so session revocation and mailbox review are important containment steps.
