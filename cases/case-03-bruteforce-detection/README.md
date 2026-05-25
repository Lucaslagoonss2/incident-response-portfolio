# 🚨 Case 03: Brute Force Detection & Authentication Analysis

**Date:** 2026-05-25  
**Analyst:** Lucas Rodrigues  
**Severity:** HIGH  
**Environment:** Windows Lab Environment  
**Tools:** Hydra, Windows Event Viewer, PowerShell, Wireshark, Sysmon

---

# 🧾 Incident Summary

A brute force authentication attack was identified against a Windows host during a controlled lab simulation.

Multiple failed authentication attempts were detected targeting a local user account through repeated password guessing activity.

The attack simulation was performed using Hydra in a controlled environment to emulate common credential access techniques observed in real-world intrusion attempts.

Initial investigation identified repeated failed logons, authentication anomalies and suspicious login patterns associated with brute force activity.

The incident was classified as HIGH severity due to the risk of credential compromise and unauthorized access.

---

# 🚨 Detection

## Initial Indicators

- Multiple failed authentication attempts
- Repeated username targeting
- Suspicious authentication patterns
- Rapid login failures
- Potential password guessing activity

---

# 🔍 Investigation & Analysis

## Observed Behavior

- Consecutive failed logons detected
- Repeated authentication attempts from same source
- User account enumeration behavior
- Possible brute force activity
- Authentication failure spikes observed

---

# 🧠 MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|----|
| Credential Access | Brute Force | T1110 |
| Credential Access | Password Guessing | T1110.001 |

---

# 🧪 IOC Extraction

| IOC Type | Value |
|----------|-------|
| Attack Type | Brute Force |
| Tool | Hydra |
| Event ID | 4625 |
| Technique | Password Guessing |
| Authentication Type | Failed Logon |

---

# 🔒 Containment Actions

- Monitored suspicious authentication attempts
- Recommended account lockout policies
- Reviewed authentication logs
- Investigated targeted accounts
- Recommended MFA implementation

---

# 📚 Lessons Learned

- Authentication monitoring is critical
- Failed logon analysis can identify attacks early
- Strong password policies reduce brute force risk
- MFA significantly improves account security

---

# 📸 Planned Evidence

- Hydra attack simulation
- Windows Event Viewer logs
- Event ID 4625 evidence
- Failed logon analysis
- Authentication timeline
- IOC correlation