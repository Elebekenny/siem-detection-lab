# Red Team Attack Chain with SIEM Detection and Wireshark Analysis

This project simulates a full adversary kill chain in a Windows/Linux hybrid lab environment. It demonstrates offensive techniques using Metasploit, Mimikatz, and PowerShell, alongside defensive detection and hunting using Splunk, Sysmon, and Wireshark.

---

## 🎯 Objective

To simulate an advanced persistent threat (APT)-style intrusion using common TTPs (tactics, techniques, and procedures) and detect those activities using SIEM tools, network forensics, and log analysis mapped to the MITRE ATT&CK framework.

---

## 🧱 Lab Setup

- **Attacker Machine**: Kali Linux
- **Victim Machines**:
  - Windows 10 (target workstation)
  - Windows Server 2019 with Active Directory
- **SIEM Setup**: Splunk (with Sysmon log ingestion via Winlogbeat)
- **Optional Tools**: BloodHound + Neo4j for AD enumeration

---

## 🛠️ Tools Used

- Metasploit Framework
- PowerShell & Nishang Scripts
- Mimikatz
- Sysmon + Winlogbeat + Splunk
- Wireshark
- CrackMapExec
- BloodHound & SharpHound

---

## 🔥 Attack Chain Simulated

| Phase               | Techniques/Tools Used                               | MITRE ID          |
|---------------------|------------------------------------------------------|-------------------|
| Initial Access       | Phishing payload (PowerShell reverse shell)         | T1566 / T1059.001 |
| Execution            | Encoded PowerShell via IEX                          | T1059             |
| Credential Dumping   | Mimikatz NTLM hash dump                             | T1003             |
| Lateral Movement     | SMB/RDP using dumped credentials                    | T1021             |
| Privilege Escalation | Unquoted Service Path (winPEAS)                     | T1543             |
| Post-Exploitation    | BloodHound AD enumeration and exfil simulation      | T1482 / T1041     |

---

## 📂 Project Structure

```
siem-detection-lab/
├── attack_simulation/
│   ├── phishing_payload/
│   ├── privilege_escalation/
│   └── lateral_movement/
├── siem_logs/
├── detection_rules/
├── wireshark_traces/
├── threat_hunting_report.md
├── remediation_plan.md
└── README.md
```

---

## 🧪 Detection Techniques

- Created custom Splunk alerts to detect:
  - Encoded PowerShell
  - Unusual outbound RDP
  - Credential dumping behavior (LSASS access)
- Used Wireshark to capture reverse shell traffic and SMB enumeration
- Mapped all findings to MITRE ATT&CK for traceability

---

## 📄 Deliverables

- `threat_hunting_report.md`: Timeline of attack stages with IOCs and logs
- `remediation_plan.md`: SIEM tuning recommendations + hardening advice
- `detection_rules/`: Sample Splunk query rules (SPL) and Sigma formats
- `wireshark_traces/`: PCAPs of attack traffic

---

## 📊 Value to Employers

This project demonstrates:
- Full red-to-blue visibility
- Strong familiarity with SIEM workflows
- A real-world understanding of detection engineering
- The ability to operationalize MITRE ATT&CK data

---

## 👨‍💻 Author

**Elebe Kehinde Martins**  
Pentester turned Cloud Security Engineer | DevSecOps Trainee | SIEM Detection Specialist  
GitHub: [github.com/Elebekenny](https://github.com/Elebekenny)

---

## 📝 License

For educational and professional portfolio use only. Built in a closed test lab. No production use permitted.
