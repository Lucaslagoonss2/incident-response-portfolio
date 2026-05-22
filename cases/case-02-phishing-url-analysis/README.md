# 🚨 Case 02: Phishing URL Analysis

**Date:** 2026-05-22  
**Analyst:** Lucas Rodrigues  
**Severity:** MEDIUM  
**Environment:** Simulated SOC Investigation  
**Tools:** URLscan.io, VirusTotal, Wireshark, Browser Developer Tools

---

# 🧾 Incident Summary

The security team received reports from employees regarding suspicious emails impersonating an internal payroll update notification.

The phishing email contained a malicious URL designed to steal user credentials through a fake login portal.

The investigation focused on analyzing the phishing infrastructure, extracting IOCs and identifying attacker techniques.

---

# 🚨 Detection

## Suspicious Email

```text
From: hr-updates@noreply-payroll.xyz
Subject: Payroll System Update Required
Link: http://payroll-portal.secure-login.xyz/update.php
```

---

# 🔍 Initial Indicators

- Suspicious sender domain
- Unusual TLD (.xyz)
- Fake payroll impersonation
- Credential harvesting behavior
- External redirect attempts

---

#  Investigation & Analysis

## URL Analysis

The phishing page imitated a Microsoft login portal and attempted to collect employee credentials.

### Observed Behaviors

- Fake login form
- Credential POST requests
- Suspicious redirects
- Newly registered domain
- Self-signed SSL certificate

---

#  Threat Intelligence Findings

| Indicator | Value |
|-----------|-------|
| Phishing URL | payroll-portal.secure-login.xyz |
| Sender Email | hr-updates@noreply-payroll.xyz |
| Technique | Phishing |
| MITRE ID | T1566 |
| SSL Certificate | Self-Signed |

---

#  MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|----|
| Initial Access | Phishing | T1566 |
| Initial Access | Spearphishing Link | T1566.002 |
| Credential Access | Input Capture | T1056 |

---

#  IOC Extraction

| Type | Value |
|------|-------|
| Domain | secure-login.xyz |
| Email | hr-updates@noreply-payroll.xyz |
| URL Path | /update.php |
| Attack Type | Credential Harvesting |

---

#  Containment Actions

- Blocked phishing domain at firewall level
- Added malicious domain to email gateway blacklist
- Notified affected users
- Forced password reset procedures
- Recommended MFA enforcement

---

#  Lessons Learned

- User awareness training remains essential
- Email filtering rules should be improved
- External domain monitoring can reduce exposure
- MFA significantly reduces phishing impact

---

#  Evidence & Screenshots

Planned screenshots:
- Fake phishing page
- URLscan analysis
- VirusTotal domain reputation
- Browser network requests
- IOC extraction timeline