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
