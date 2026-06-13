# Final SOC Triage Summary Report

> **Project Note:** This is a simulated final triage report created for cybersecurity portfolio development. It does not contain real customer data, private logs, credentials, malware, or confidential information.

## Report Overview

This report summarizes five simulated SOC alert triage scenarios reviewed as part of this SOC Alert Triage & Log Analysis Lab.

The goal of this report is to demonstrate how multiple alert types can be reviewed, documented, assigned severity, and communicated in a structured way.

## Alerts Reviewed

| Alert | Severity | Escalation Decision | Primary Risk |
|---|---|---|---|
| Phishing Email Alert | Medium | Conditional | Credential theft |
| Suspicious Login Alert | High | Yes | Account compromise |
| Endpoint Malware Alert | High | Yes | Malware execution |
| Brute-Force Authentication Alert | Medium | Conditional | Credential attack |
| Abnormal Network Activity Alert | Medium | Conditional | Suspicious outbound communication |

## Cross-Alert Observations

Several alerts share common investigation themes:

- Identity compromise risk
- Credential theft concerns
- Suspicious user activity
- Need for MFA validation
- Need for session revocation
- Importance of endpoint correlation
- Importance of checking scope across multiple users or hosts

## Highest Priority Alerts

### Suspicious Login Alert

This alert was rated High because it involved a successful login from an unfamiliar source. Successful suspicious logins may indicate active account compromise.

### Endpoint Malware Alert

This alert was rated High because it involved suspicious process execution, child process activity, temporary file creation, and outbound network communication.

## Conditional Escalation Alerts

### Phishing Email Alert

Escalation depends on whether the user clicked the link or entered credentials.

### Brute-Force Authentication Alert

Escalation depends on whether a successful login occurred, whether the account is privileged, or whether multiple users were targeted.

### Abnormal Network Activity Alert

Escalation depends on whether the destination is confirmed malicious or linked to suspicious endpoint process activity.

## Recommended SOC Actions

- [ ] Confirm user interaction for phishing alerts
- [ ] Review suspicious login activity
- [ ] Reset passwords when compromise is suspected
- [ ] Revoke active sessions after suspected credential exposure
- [ ] Review MFA status and enforcement
- [ ] Review mailbox rules and forwarding
- [ ] Isolate endpoints when malware execution is suspected
- [ ] Identify suspicious processes responsible for network connections
- [ ] Search for similar indicators across users and hosts
- [ ] Document all findings and escalation decisions

## MITRE ATT&CK Themes

| Technique Area | Related Alerts |
|---|---|
| Phishing | Phishing Email Alert, Suspicious Login Alert |
| Valid Accounts | Suspicious Login Alert |
| Brute Force | Brute-Force Authentication Alert |
| User Execution | Endpoint Malware Alert |
| Command and Control | Endpoint Malware Alert, Abnormal Network Activity Alert |
| Email Collection | Suspicious Login Alert |
| Application Layer Protocol | Abnormal Network Activity Alert |

## What This Report Demonstrates

This report demonstrates the ability to:

- Compare multiple alert types
- Prioritize alerts based on risk
- Document escalation reasoning
- Identify shared investigation themes
- Recommend containment actions
- Communicate findings clearly
- Apply structured SOC thinking across different scenarios

## Lessons Learned

Not every alert requires the same level of escalation, but every alert requires structured review.

The strongest signals usually come from combining multiple pieces of evidence. For example, a suspicious login becomes more serious when linked to phishing. Abnormal network activity becomes more serious when linked to endpoint malware behavior.

SOC triage is about understanding context, documenting evidence, and making clear decisions based on risk.
