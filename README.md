# Active Directory Security Lab (Red & Blue Team)

A comprehensive Purple Team repository focused on simulating Active Directory attack vectors, analyzing telemetry, and implementing enterprise-grade defensive hardening controls. 

This repository serves as a centralized toolkit and reference guide for cybersecurity professionals to understand both how Active Directory is exploited and how to secure it against modern adversaries.

##  Disclaimer

The content, scripts, and utilities provided in this repository are strictly for educational purposes, authorized penetration testing, and defensive research. Archiving, testing, or executing these tools against systems without explicit, written permission from the system owner is illegal. The author assumes no liability for misinterpretation or misuse of this information.

---

## 🛠️ Repository Structure

```text
├── .github/
├── 🔴-Offensive-Assessments/   # Attack simulation scripts, enumeration, and payloads
│   ├── Enumeration/
│   └── Exploitation-Planners/
├── 🔵-Defensive-Hardening/     # GPO templates, tiering models, and configuration baselines
│   ├── Hardening-Scripts/
│   └── Group-Policies/
├── 🟣-Detection-Engineering/   # SIEM dashboards, Sigma rules, and event log hunting queries
└── README.md
```

---

## 🔴 Offensive Security Capabilities (Red Team)

This section focuses on identifying misconfigurations, mapping attack paths, and validating domain vulnerabilities.

### Covered Attack Vectors & Simulations
* **Domain Enumeration:** BloodHound data collection scripts and automated LDAP querying.
* **Credential Access:** Simulation playbooks for Kerberoasting, AS-REP Roasting, and targeted LSASS dumping configurations.
* **Privilege Escalation & Persistence:** Documentation and scripts for exploiting weak ACLs, unconstrained delegations, and malicious Group Policy Objects.

---

## 🔵 Defensive Posture & Mitigations (Blue Team)

This section provides actionable infrastructure-as-code and configuration guidelines to reduce the attack surface of the Active Directory environment.

### Implemented Controls
* **Tiered Administrative Model:** Architecture baselines for implementing an explicit Tier 0/1/2 administrative isolation boundaries.
* **GPO Hardening Baselines:** Pre-configured Group Policy objects for disabling LLMNR/NBT-NS, enforcing SMB signing, and restricting local administrator access.
* **Account Hardening:** Auditing scripts to flag stale accounts, passwords that never expire, and accounts with reversible encryption enabled.

---

## 🟣 Detection Engineering (Purple Team)

Bridging the gap between attack and defense by translating exploitation telemetry into robust monitoring controls.

* **Log Source Optimization:** Advanced Audit Policy Configuration checklists to ensure critical events (e.g., Event ID 4624, 4768, 4769) are captured.
* **Threat Hunting Queries:** Tailored Splunk/KQL queries designed to pinpoint abnormal Kerberos ticket requests and unauthorized replication attempts (DCShadow/DCSync).

---

##  Getting Started

### OpSec & Safety Checklist
Before running any automated script from this repository, ensure you adhere to strict Operational Security protocols:
1. **Never** run offensive utilities or unverified scripts directly in a production environment.
2. Ensure your `.gitignore` is configured to prevent accidental commits of sensitive data (`NTDS.dit`, private keys, local passwords).
3. Always verify script parameters to ensure traffic is strictly routed within your designated sandbox network.

---

## 🤝 Contributing

Contributions to improve both the offensive simulations and defensive playbooks are highly welcome! Please submit a Pull Request or open an Issue to suggest updates, point out structural bugs, or add new detection rules.
