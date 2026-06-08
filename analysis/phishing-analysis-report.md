# Phishing Email Analysis Report

## Executive Summary

A suspicious email claiming to be from the Microsoft Security Team was analyzed. The email attempted to pressure the recipient into verifying their Microsoft 365 account through a suspicious external link.

The investigation found multiple phishing indicators, including a spoofed sender domain, failed email authentication checks, urgency-based language, and a suspicious verification URL. Based on the findings, this email is assessed as phishing.

---

## Email Overview

| Field | Value |
|---|---|
| Claimed Sender | Microsoft Security Team |
| Sender Address | security-alert@micros0ft-support.com |
| Recipient | employee@example.com |
| Subject | Urgent: Your Microsoft 365 Account Will Be Suspended |
| Date | 8 June 2026 |
| Attachment | None |
| Verdict | Phishing |

---

## Key Indicators of Phishing

### Suspicious Sender Domain

The sender address used the domain:

```text
micros0ft-support.com
```

### Failed Email Authentication

The email authentication results showed:

```text
spf=fail
dkim=none
dmarc=fail
```

This means the message failed important email security checks.

| Control | Result | Meaning |
|---|---|---|
| SPF | Fail | The sending server was not authorized to send email for the domain |
| DKIM | None | No valid digital signature was present |
| DMARC | Fail | The email failed domain alignment/authentication checks |

These failures strongly indicate that the email may be spoofed or sent from an unauthorized source.

### Urgency and Pressure Tactics

The email used urgent language such as:

```text
Your account access will be suspended within 24 hours
```

This is a common phishing technique designed to pressure the recipient into acting quickly without verifying the message.

### Suspicious URL

The email included the following defanged URL:

```text
hxxps://micros0ft-support[.]com/login/verify-account
```

The domain does not belong to Microsoft. The URL is likely designed to steal user credentials by imitating a Microsoft login page.

## Extracted IOCs

| IOC Type | Value |
|---|---|
| Sender Email | [security-alert@micros0ft-support.com](mailto:security-alert@micros0ft-support.com) |
| Reply-To Email | [support-verification@micros0ft-support.com](mailto:support-verification@micros0ft-support.com) |
| Domain | micros0ft-support.com |
| URL | hxxps://micros0ft-support[.]com/login/verify-account |
| Sending IP | 185.199.108.153 |

## Risk Assessment

| Category   | Assessment     |
| ---------- | -------------- |
| Likelihood | High           |
| Impact     | Medium to High |
| Risk Level | High           |

If a user entered credentials into the phishing site, the attacker could gain access to Microsoft 365 services such as Outlook, OneDrive, Teams, and SharePoint.

## Recommended SOC Actions

- Quarantine the email from all affected mailboxes.
- Block the suspicious domain at the email gateway, DNS filter, or proxy.
- Search email logs for other recipients who received the same message.
- Check whether any users clicked the link.
- Reset credentials for any user who interacted with the phishing page.
- Review Microsoft 365 sign-in logs for suspicious login attempts.
- Report the phishing domain to the relevant security team or abuse contact.
- Educate users about lookalike domains and urgency-based phishing.

## Final Verdict

The email is confirmed as phishing.

The main evidence includes a lookalike sender domain, failed SPF/DKIM/DMARC checks, urgency-based wording, and a suspicious credential-harvesting link.
