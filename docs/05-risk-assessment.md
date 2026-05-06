# 05 — Risk Assessment

## Overview

This risk assessment was conducted using a structured Impact × Likelihood matrix. Eight risks were identified through stakeholder interviews, process analysis, and review of current security posture.

**Scoring Scale:**
- **Likelihood:** 1 (Rare) → 5 (Almost Certain)
- **Impact:** 1 (Negligible) → 5 (Critical)
- **Risk Score:** Likelihood × Impact (1–25)

---

## Risk Register

| Risk ID | Risk Description | Category | Likelihood | Impact | Score | Rating | Owner |
|---------|------------------|----------|------------|--------|-------|--------|-------|
| RISK-01 | Unauthorized access to production data due to lack of RBAC and MFA | Security | 4 | 5 | 20 | 🔴 Critical | CTO |
| RISK-02 | Insider threat — current employees can access all client data without restriction | Security | 3 | 5 | 15 | 🔴 Critical | CTO |
| RISK-03 | GDPR regulatory fine due to incomplete compliance program | Compliance | 4 | 4 | 16 | 🔴 Critical | Legal/DPO |
| RISK-04 | Inability to detect or investigate a security incident due to lack of logging | Security | 4 | 4 | 16 | 🔴 Critical | Engineering |
| RISK-05 | Client churn due to slow, unstructured onboarding experience | Operational | 3 | 3 | 9 | 🟡 Medium | Head of Ops |
| RISK-06 | Failure to meet enterprise client security requirements, blocking sales | Business | 3 | 4 | 12 | 🟠 High | CEO |
| RISK-07 | Departed employee retaining system access (no offboarding process) | Security | 3 | 4 | 12 | 🟠 High | HR / IT |
| RISK-08 | Data breach via compromised account (no MFA, weak password policy) | Security | 3 | 5 | 15 | 🔴 Critical | CTO |

---

## Risk Matrix

```
         IMPACT
           1       2       3       4       5
         ┌───────┬───────┬───────┬───────┬───────┐
    5    │  5    │  10   │  15   │  20   │  25   │  ← RISK-01 (20)
         │       │       │ R2,R8 │       │       │
    4    │  4    │  8    │  12   │  16   │  20   │  ← RISK-03, RISK-04 (16)
         │       │       │ R6,R7 │ R3,R4 │ R1    │
L   3    │  3    │  6    │  9    │  12   │  15   │  ← RISK-02, RISK-08 (15)
I        │       │       │  R5   │       │ R2,R8 │
K   2    │  2    │  4    │  6    │  8    │  10   │
E        │       │       │       │       │       │
L   1    │  1    │  2    │  3    │  4    │  5    │
I        │       │       │       │       │       │
H        └───────┴───────┴───────┴───────┴───────┘
O
O   🔴 Critical (≥15)   🟠 High (10–14)   🟡 Medium (5–9)   🟢 Low (<5)
D
```

---

## Risk Detail

### RISK-01 — Unauthorized Access (Score: 20 | Critical)

**Description:** The absence of RBAC means any employee can access any system, including production databases containing client PII and financial data. Without MFA, a single compromised credential grants full access.

**Potential Impact:**
- Data breach affecting all ~85 clients
- Regulatory notification obligation under GDPR (72-hour window)
- Reputational damage and potential client loss

**Recommended Controls:** Implement RBAC model; enforce MFA for all accounts; apply principle of least privilege.

---

### RISK-02 — Insider Threat (Score: 15 | Critical)

**Description:** Current access model allows any internal user to read, copy, or modify sensitive client data without detection, as there is no audit logging.

**Potential Impact:**
- Deliberate or accidental data exfiltration
- Inability to detect or prove the incident after the fact

**Recommended Controls:** RBAC + centralized logging with access audit trail.

---

### RISK-03 — GDPR Non-Compliance (Score: 16 | Critical)

**Description:** CloudBase has not completed a DPIA, lacks formal data retention policies, and has no DSAR handling process. An ongoing regulatory inquiry increases the probability of formal action.

**Potential Impact:**
- Fines of up to €20M or 4% of global annual turnover (GDPR Art. 83)
- Mandatory corrective measures imposed by the DPA

**Recommended Controls:** Complete DPIA; define retention policies; implement DSAR process; appoint or formalize DPO role.

---

### RISK-04 — Incident Detection Gap (Score: 16 | Critical)

**Description:** No centralized logging or alerting means security incidents may go undetected for extended periods. When an incident is eventually discovered, there is no audit trail to support investigation.

**Potential Impact:**
- Extended breach duration, amplifying damage
- Inability to meet GDPR breach notification requirements
- No forensic evidence for incident response

**Recommended Controls:** Implement centralized logging (AWS CloudTrail + CloudWatch); configure anomaly alerts.

---

### RISK-05 — Client Churn from Poor Onboarding (Score: 9 | Medium)

**Description:** 18-day average onboarding time with no client visibility creates friction. Clients may perceive the platform as immature or difficult to work with.

**Recommended Controls:** Redesign onboarding process; implement ticketing with SLAs and client portal.

---

### RISK-06 — Enterprise Sales Blocked (Score: 12 | High)

**Description:** Enterprise clients increasingly require vendors to complete security questionnaires and demonstrate SOC 2 or ISO 27001 readiness. CloudBase cannot currently satisfy these requirements.

**Recommended Controls:** Implement the GRC program documented in this project as the foundation for eventual certification.

---

### RISK-07 — Ghost Accounts (Departed Employees) (Score: 12 | High)

**Description:** There is no offboarding process to revoke system access when employees leave. Former employees may retain active credentials to production systems.

**Recommended Controls:** Integrate HR system with IAM; automate access revocation on departure; conduct retroactive account audit.

---

### RISK-08 — Data Breach via Compromised Account (Score: 15 | Critical)

**Description:** Without MFA, a phishing attack or credential stuffing attempt could result in immediate full-access compromise of the platform.

**Recommended Controls:** Enforce MFA; implement password policy; consider passwordless authentication for admin accounts.
