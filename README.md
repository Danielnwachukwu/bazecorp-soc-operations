# BAZECORP | Security Operations Center

### Security Monitoring • Threat Detection • Incident Investigation • Incident Response

Welcome to the BAZECORP Security Operations Center (SOC) operations repository.

This repository documents security monitoring activities, threat detection, incident investigations, evidence analysis, incident escalation, and remediation recommendations within the BAZECORP environment.

Our objective is to maintain structured, evidence-based security records that support incident handling, escalation, remediation, and continuous improvement.

---

## 🛡️ SOC Operations Overview

| Function | Description |
|---|---|
| Security Monitoring | Monitor endpoint and security events for suspicious activity. |
| Threat Detection | Review security alerts and investigate potentially suspicious behavior. |
| Incident Investigation | Analyze authentication events and endpoint telemetry. |
| Incident Response | Document findings, escalation decisions, and remediation recommendations. |
| Evidence Management | Preserve screenshots and investigation records for traceability. |
| Incident Documentation | Maintain structured incident reports and operational records. |

---

## 🧰 Security Monitoring Environment

- **Wazuh SIEM** — Security alert monitoring and event investigation.
- **Windows Server / Active Directory** — Windows authentication events and domain account activity.
- **Sysmon** — Endpoint telemetry supporting process and network activity investigations.
- **GLPI** — Incident ticketing, assignment, and investigation documentation.

---

## 🚨 Incident Report

### BAZECORP-IR-2026-001 — Joyce Finance Failed-Logon Investigation

| Field | Details |
|---|---|
| Incident Date | October 23, 2026 |
| Affected Account | `BAZECORP\joyce.finance` |
| Department | Finance |
| Endpoint | `BAZECORP-SRV-01` |
| Wazuh Agent ID | `006` |
| Windows Security Event ID | `4625` |
| Wazuh Rule ID | `60122` |
| GLPI Ticket | `#52` |
| Disposition | Escalated for follow-up |

### Incident Summary

Wazuh identified four failed logon events associated with the Active Directory account `joyce.finance` on `BAZECORP-SRV-01` at approximately 20:56 on October 23, 2026.

The events were recorded as Windows Security Event ID `4625` and generated Wazuh alerts under rule ID `60122`.

The recorded source address was `127.0.0.1`, indicating loopback activity on the endpoint. This evidence does not establish whether Joyce personally initiated the attempts or whether another person or local process was responsible.

### Key Findings

- Four failed authentication events were identified.
- The affected account was `BAZECORP\joyce.finance`.
- The recorded source address was `127.0.0.1`.
- No matching successful logon was identified in the searched Wazuh results for the relevant period.
- Nearby Sysmon activity was reviewed, but no direct relationship to the failed logons was established.
- Account compromise was not confirmed by the available evidence.

### Recommended Response

1. Escalate the incident to the SOC lead and relevant IT administrators.
2. Contact Joyce to verify whether the authentication attempts were expected.
3. Request a password change in accordance with organizational procedures.
4. Maintain close monitoring of the account and relevant endpoint for further suspicious authentication activity.
5. Document remediation and follow-up actions in GLPI ticket `#52`.

**Assessment:** The repeated authentication failures warrant escalation. The available evidence does not confirm account compromise.

---

## 📸 Incident Evidence

The following screenshots provide visual evidence supporting the investigation. Select an image to view it at full size.

### Evidence 01 — Wazuh Failed-Logon Alerts

Wazuh alert results showing the four failed-logon events, timestamps, severity, and rule ID.

![Evidence 01 — Wazuh Failed-Logon Alerts](./BAZECORP-IR-2026-001_Evidence-01_Wazuh-Failed-Logon-Alerts%281%29.png)

### Evidence 02 — Joyce Account Search Results

Wazuh search results filtered for the affected account and endpoint.

![Evidence 02 — Joyce Account Search Results](./BAZECORP-IR-2026-001_Evidence-02_Wazuh-Joyce-Failed-Logon-Search.png)

### Evidence 03 — GLPI Incident Ticket

GLPI ticket `#52`, documenting the incident summary, affected account, investigation details, and assignment to the BAZECORP SOC Team.

![Evidence 03 — GLPI Incident Ticket 52](./BAZECORP-IR-2026-001_Evidence-03_GLPI-Incident-Ticket-52%281%29.png)

### Evidence 04 — Detailed Windows Failed-Logon Event

Windows event details showing the affected account, event timestamp, source address, and authentication failure information.

![Evidence 04 — Windows Failed-Logon Event Details](./BAZECORP-IR-2026-001_Evidence-04_Windows-Failed-Logon-Joyce-Details%281%29.png)

### Evidence 05 — Final Investigation Assessment

GLPI follow-up documenting the investigation findings, limitations, escalation recommendation, and proposed remediation.

![Evidence 05 — GLPI Investigation Assessment](./BAZECORP-IR-2026-001_Evidence-05_GLPI-Investigation-Assessment%281%29.png)

---

## 📁 Repository Structure

```text
bazecorp-soc-operations/
├── README.md
├── BAZECORP-IR-2026-001_Evidence-01_Wazuh-Failed-Logon-Alerts(1).png
├── BAZECORP-IR-2026-001_Evidence-02_Wazuh-Joyce-Failed-Logon-Search.png
├── BAZECORP-IR-2026-001_Evidence-03_GLPI-Incident-Ticket-52(1).png
├── BAZECORP-IR-2026-001_Evidence-04_Windows-Failed-Logon-Joyce-Details(1).png
└── BAZECORP-IR-2026-001_Evidence-05_GLPI-Investigation-Assessment(1).png
