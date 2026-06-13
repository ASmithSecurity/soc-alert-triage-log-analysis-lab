# Alert 01: Phishing Email Alert

> **Project Note:** This is a simulated SOC alert write-up created for cybersecurity portfolio development. No real customer data, emails, credentials, or private information are included.

## Alert Summary

| Field | Details |
|---|---|
| Alert Name | User-Reported Suspicious Email |
| Alert Type | Phishing |
| Severity | Medium |
| Status | Investigated / Escalation Recommended if User Interacted |
| Affected User | user@example.com |
| Affected Asset | User Mailbox |
| Primary Concern | Credential theft or malicious link interaction |

## Scenario

A user reported receiving a suspicious email that appeared to impersonate a trusted service provider. The email used urgent language and contained a link directing the user to a fake login page.

The user was unsure whether the email was legitimate and submitted it for review.

## Simulated Email Details

| Field | Details |
|---|---|
| Sender Display Name | Microsoft Security Team |
| Sender Address | security-alert@example-login.com |
| Subject | Urgent: Password Expiration Notice |
| Link Display Text | Review Account Security |
| URL Destination | hxxps://example-login-security[.]com |
| Attachment | None |
| User Interaction | Unknown |

## Evidence Reviewed

| Evidence | Notes |
|---|---|
| Sender address | Domain does not match expected Microsoft domain |
| Subject line | Uses urgent language to pressure user action |
| Link destination | Suspicious external domain |
| Email body | Requests credential-related action |
| Attachment | No attachment observed |
| User interaction | Requires confirmation |

## Indicators of Compromise

| Indicator | Type | Notes |
|---|---|---|
| security-alert@example-login.com | Email Address | Suspicious sender address |
| hxxps://example-login-security[.]com | URL | Possible credential harvesting page |
| example-login-security[.]com | Domain | Suspicious lookalike domain |
| Urgent password notice | Social Engineering | Attempts to pressure user |

## Analysis

The email contains multiple phishing indicators, including a suspicious sender domain, urgent language, and a link leading to a non-official login domain.

The alert should be treated as suspicious. Severity depends on whether the user clicked the link or entered credentials.

If the user only received the email and did not interact with it, the severity may remain Medium. If the user clicked the link or submitted credentials, the incident should be escalated as a potential identity compromise.

## Severity Reasoning

| Factor | Assessment |
|---|---|
| Suspicious sender | Yes |
| Suspicious URL | Yes |
| Credential theft risk | Yes |
| User interaction confirmed | Unknown |
| Scope | Single reported user |
| Severity | Medium, escalate to High if credentials were entered |

## Recommended Actions

- [ ] Confirm whether the user clicked the link
- [ ] Confirm whether credentials were entered
- [ ] Search for similar emails across other mailboxes
- [ ] Block suspicious sender, URL, or domain if confirmed malicious
- [ ] Remove the email from affected mailboxes if needed
- [ ] Reset password if credentials were entered
- [ ] Review recent sign-in activity
- [ ] Confirm MFA is enabled
- [ ] Educate user on phishing indicators

## Escalation Decision

**Escalate:** Conditional

**Reason:**

Escalate if the user clicked the link, entered credentials, or if similar emails were delivered to multiple users.

## Partner-Friendly Summary

The reported email shows signs of phishing, including a suspicious sender address, urgent password-related language, and a link to a non-official login page.

Recommended next steps are to confirm whether the user interacted with the link, search for similar emails, block the suspicious domain if confirmed malicious, and reset the user's password if credentials were entered.

## MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| Phishing | Email attempts to trick user into clicking a malicious link |
| Credential Harvesting | Link may lead to a fake login page designed to steal credentials |
| User Execution | User interaction may trigger compromise risk |

## Lessons Learned

Phishing alerts require both technical review and user confirmation. A suspicious email may remain a medium-risk event unless user interaction or credential exposure is confirmed. Clear follow-up questions are critical for determining severity and next steps.
