# SOC Alert Triage & Log Analysis Lab

> **Project Note:** This is a simulated cybersecurity portfolio project created for educational and professional development purposes. It does not contain real customer data, private logs, credentials, malware, or confidential information.

## Project Overview

This project documents SOC-style alert triage and log analysis practice using simulated security events.

The purpose of this lab is to demonstrate entry-level SOC analyst and SOC support skills, including reviewing alert context, identifying indicators of compromise, assigning severity, documenting evidence, recommending containment steps, and communicating findings clearly.

This project is aligned with entry-level roles such as:

- SOC Support Specialist
- Cybersecurity Support Analyst
- SOC Analyst I
- IT Security Support Specialist
- Security Operations Associate
- Technical Support Engineer with security focus

## Project Goal

The goal of this project is to show how I approach different types of security alerts in a structured and repeatable way.

Each alert write-up includes:

- Alert summary
- Simulated evidence reviewed
- Indicators of compromise
- Analysis and severity reasoning
- Recommended containment actions
- Escalation decision
- Partner or customer-friendly explanation
- Lessons learned

## Alert Scenarios Included

| Alert | Focus Area |
|---|---|
| Phishing Email Alert | Email security, credential theft risk, user-reported phishing |
| Suspicious Login Alert | Identity compromise, abnormal sign-in behavior, MFA/session review |
| Endpoint Malware Alert | Endpoint security, suspicious process behavior, isolation decision |
| Brute-Force Authentication Alert | Repeated failed logins, account lockout risk, credential attack patterns |
| Abnormal Network Activity Alert | Suspicious outbound traffic, IP/domain review, network investigation |

## Skills Demonstrated

- SOC alert triage
- SIEM and log analysis concepts
- Phishing analysis
- Suspicious login investigation
- Endpoint malware alert review
- Brute-force authentication analysis
- Abnormal network activity review
- Indicator of compromise documentation
- Severity assessment
- Escalation reasoning
- Incident communication
- Technical documentation
- Partner-facing explanation

## Tools & Concepts Used

- SIEM dashboard concepts
- Windows event log concepts
- Authentication log review
- Endpoint telemetry concepts
- Email header and URL review concepts
- IP address and geolocation review
- Hash and domain reputation concepts
- MITRE ATT&CK mapping
- Cyber Kill Chain concepts
- Incident response lifecycle
- SOC documentation practices

## Repository Contents

| File | Purpose |
|---|---|
| [`docs/project-overview-and-takeaways.md`](docs/project-overview-and-takeaways.md) | Employer-facing overview of what the project demonstrates |
| [`templates/soc-investigation-template.md`](templates/soc-investigation-template.md) | Reusable SOC investigation template |
| [`alerts/01-phishing-email-alert.md`](alerts/01-phishing-email-alert.md) | Simulated phishing alert triage write-up |
| [`alerts/02-suspicious-login-alert.md`](alerts/02-suspicious-login-alert.md) | Simulated suspicious login investigation |
| [`alerts/03-endpoint-malware-alert.md`](alerts/03-endpoint-malware-alert.md) | Simulated endpoint malware alert review |
| [`alerts/04-brute-force-authentication-alert.md`](alerts/04-brute-force-authentication-alert.md) | Simulated brute-force authentication analysis |
| [`alerts/05-abnormal-network-activity-alert.md`](alerts/05-abnormal-network-activity-alert.md) | Simulated abnormal network traffic investigation |
| [`reports/final-triage-summary-report.md`](reports/final-triage-summary-report.md) | Final summary report across all alert scenarios |
| [`screenshots/`](screenshots/) | Folder for screenshots and documentation previews |
| [`notes/`](notes/) | Folder for extra investigation notes |
| [`resources/`](resources/) | Folder for supporting references or learning notes |

## General Triage Workflow

1. Review the alert name, source, severity, and affected asset.
2. Identify the affected user, host, IP address, domain, process, or file.
3. Review available context and simulated logs.
4. Identify indicators of compromise.
5. Determine whether the activity appears benign, suspicious, or malicious.
6. Assign severity based on confidence and potential impact.
7. Recommend containment or remediation actions.
8. Decide whether escalation is needed.
9. Document the investigation clearly.
10. Provide a short customer or partner-friendly explanation.

## Severity Rating Guide

| Severity | Criteria |
|---|---|
| Low | Suspicious but low-confidence activity with limited impact |
| Medium | Suspicious activity affecting one user or asset with possible security impact |
| High | Likely compromise, malware execution, successful suspicious login, or active incident |
| Critical | Widespread compromise, ransomware, major outage, or confirmed business impact |

## What This Project Shows

This project demonstrates my ability to:

- Review alerts in a structured way
- Document investigation findings
- Identify suspicious patterns
- Explain risk clearly
- Recommend containment actions
- Understand when escalation is needed
- Write clear internal and partner-facing notes
- Apply SOC concepts to realistic security scenarios

## Lessons Learned

SOC work requires more than recognizing suspicious activity. It also requires clear documentation, calm communication, evidence-based reasoning, and the ability to explain technical findings in a way that helps others take action.

This project helped reinforce how different alert types require different investigation questions while still following a consistent triage structure.
