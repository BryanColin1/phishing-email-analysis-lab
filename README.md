# Phishing Email Analysis Lab

## Overview

This project simulates a phishing email investigation from the perspective of a junior SOC analyst. It includes email header review, phishing indicators, extracted IOCs, risk assessment, and recommended containment/remediation actions.

## Scenario

A user reports a suspicious email claiming that their Microsoft 365 account will be suspended unless they verify their identity. The email is reviewed to determine whether it is legitimate, suspicious, or malicious.

## Skills Demonstrated

* Phishing email analysis
* Email header review
* SPF, DKIM, and DMARC interpretation
* IOC extraction
* URL defanging
* Risk assessment
* SOC-style incident documentation
* Recommended containment and remediation

## Repository Structure

```text
phishing-email-analysis-lab/
│
├── README.md
├── samples/
│   └── sample-phishing-email.txt
│
├── analysis/
│   └── phishing-analysis-report.md
│
├── iocs/
│   └── extracted-iocs.md
│
└── screenshots/
    └── 
```

## Key Findings

| Finding | Explanation |
|---|---|
| Suspicious sender domain | The email used a lookalike domain designed to imitate Microsoft |
| Failed SPF | The sending server was not authorized to send email for the domain |
| Missing DKIM | No valid digital signature was present |
| Failed DMARC | Domain authentication failed |
| Suspicious URL | The link directed to a non-Microsoft domain |
| Urgent wording | The message pressured the user to act within 24 hours |

## Extracted IOCs

| IOC Type | Value |
|---|---|
| Sender Email | [security-alert@micros0ft-support.com](mailto:security-alert@micros0ft-support.com) |
| Reply-To Email | [support-verification@micros0ft-support.com](mailto:support-verification@micros0ft-support.com) |
| Domain | micros0ft-support.com |
| URL | hxxps://micros0ft-support[.]com/login/verify-account |
| IP Address | 185.199.108.153 |

## Final Verdict

The email is assessed as phishing.

The message contains multiple indicators of malicious intent, including a lookalike sender domain, failed authentication checks, urgency-based social engineering, and a suspicious credential-harvesting link.

## Recommended Response

- Quarantine the email
- Block the suspicious domain
- Search mail logs for additional recipients
- Check whether any users clicked the link
- Reset credentials for affected users
- Review Microsoft 365 sign-in activity
- Educate users about phishing indicators
