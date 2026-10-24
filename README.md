# BAZECORP | Security Operations Center

### Security Monitoring • Threat Detection • Incident Investigation • Incident Response

Welcome to the BAZECORP Security Operations Center (SOC) operations repository.

This repository documents security monitoring activities, threat detection, incident investigations, evidence analysis, incident handling, and response recommendations within the BAZECORP environment.

The objective is to maintain structured, evidence-based security records that support incident investigation, escalation, remediation, and continuous improvement of security operations.

---

## 🛡️ SOC Operations Overview

| Function | Description |
|---|---|
| Security Monitoring | Monitor endpoint and security events for suspicious activity. |
| Threat Detection | Review security alerts and investigate potentially malicious behavior. |
| Incident Investigation | Analyze authentication events, endpoint telemetry, and relevant evidence. |
| Incident Response | Document findings, escalation decisions, and recommended remediation. |
| Evidence Management | Preserve screenshots and investigation records for traceability. |
| Incident Documentation | Maintain structured reports and incident records for operational review. |

---

## 🧰 Security Monitoring Environment

The documented environment includes the following technologies:

- **Wazuh SIEM** — Security alert monitoring and event investigation.
- **Windows Server / Active Directory** — Windows authentication events and domain account activity.
- **Sysmon** — Endpoint telemetry supporting process and network activity investigations.
- **GLPI** — Incident ticketing, assignment, and investigation documentation.

*Technologies are listed according to their use in the documented investigations.*

---

## 🚨 Incident Reports

### IR-2026-001 — Joyce Finance Failed-Logon Investigation

**Incident date:** October 23, 2026  
**Affected account:** `BAZECORP\joyce.finance`  
**Endpoint:** `BAZECORP-SRV-01`  
**Wazuh agent ID:** `006`  
**Windows Security Event ID:** `4625`  
**Wazuh rule ID:** `60122`  
**Incident ticket:** GLPI #52  
**Investigation status:** Escalated for follow-up

#### Incident Summary

Wazuh identified four failed logon events associated with the `joyce.finance` Active Directory account on `BAZECORP-SRV-01` at approximately 20:56 on October 23, 2026.

The events were classified as logon failures associated with an unknown user or incorrect password. Detailed event evidence recorded the source address as `127.0.0.1`, indicating loopback activity on the endpoint.

#### Investigation Findings

- Four failed authentication events were identified for the account.
- Windows Security Event ID `4625` and Wazuh rule `60122` were associated with the alerts.
- The recorded source address was `127.0.0.1`.
- The available evidence does not establish whether Joyce personally initiated the attempts or whether another person or local process was responsible.
- No matching successful logon was identified in the searched Wazuh results for the relevant period.
- Nearby Sysmon activity was reviewed, but no direct relationship to the failed logons was established.

#### Recommended Response

1. Escalate the incident to the SOC lead and relevant IT administrators.
2. Contact Joyce to verify whether the authentication attempts were expected.
3. Request a password change in accordance with organizational procedures.
4. Maintain close monitoring of the account and relevant endpoint for further suspicious authentication activity.
5. Record follow-up actions and update the incident ticket as remediation progresses.

**Assessment:** The repeated authentication failures warrant escalation. Account compromise has not been confirmed by the available evidence.

**Tracking record:** GLPI ticket #52.

---

## 📸 Incident Evidence

The following evidence files will be displayed here after they are uploaded to this repository.

### Evidence 01 — Wazuh Failed-Logon Alerts

The Wazuh alert results showing four failed-logon events and their timestamps.

![Wazuh Failed-Logon Alerts](incidents/BAZECORP-IR-2026-001/evidence/01-wazuh-failed-logon-alerts.png)

### Evidence 02 — Joyce Account Search Results

The Wazuh search results filtered for the affected account and endpoint.

![Joyce Account Search Results](incidents/BAZECORP-IR-2026-001/evidence/02-wazuh-joyce-account-search.png)

### Evidence 03 — GLPI Incident Ticket

The incident ticket documenting the investigation, assignment, and incident details.

![GLPI Incident Ticket 52](incidents/BAZECORP-IR-2026-001/evidence/03-glpi-incident-ticket-52.png)

### Evidence 04 — Detailed Failed-Logon Event

The event fields showing the affected account, timestamp, source address, and authentication failure details.

![Windows Failed-Logon Event Details](incidents/BAZECORP-IR-2026-001/evidence/04-windows-failed-logon-event-details.png)

### Evidence 05 — Final Investigation Assessment

The GLPI follow-up record documenting the investigation findings, limitations, and escalation assessment.

![GLPI Investigation Assessment](incidents/BAZECORP-IR-2026-001/evidence/05-glpi-investigation-assessment.png)

---

## 📁 Repository Structure

```text
bazecorp-soc-operations/
├── README.md
└── incidents/
    └── BAZECORP-IR-2026-001/
        ├── README.md
        └── evidence/
            ├── 01-wazuh-failed-logon-alerts.png
            ├── 02-wazuh-joyce-account-search.png
            ├── 03-glpi-incident-ticket-52.png
            ├── 04-windows-failed-logon-event-details.png
            └── 05-glpi-investigation-assessment.png
