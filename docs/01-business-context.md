# 01 — Business Context

## Company Overview

**CloudBase Ltda** is a fictional mid-sized SaaS company founded in 2018, headquartered in Lisbon, Portugal. It provides a subscription management and analytics platform to B2B clients, primarily in the financial services and retail sectors across Europe.

- **Employees:** ~120
- **Clients:** ~85 B2B clients (SMEs and enterprise accounts)
- **Data handled:** Customer PII, financial subscription data, usage analytics
- **Revenue model:** Monthly and annual SaaS subscriptions
- **Regulatory exposure:** GDPR (EU), NIS2 (critical infrastructure clients)

---

## Current Situation

CloudBase has grown rapidly over the past three years, acquiring clients faster than its internal processes and security posture could scale. The platform was initially built with speed-to-market in mind, and governance, risk management, and compliance were deprioritized.

As of the assessment date, the company is facing three converging pressures:

1. **Enterprise clients are requesting security questionnaires and audit evidence** — CloudBase cannot yet respond adequately.
2. **A GDPR inquiry was initiated** by a European regulatory body following a minor data incident (unauthorized internal access to client records).
3. **Operational inefficiencies** are increasing support costs and slowing client onboarding.

---

## Key Business Challenges

### 1. Lack of Access Control
There is no Role-Based Access Control (RBAC) model in place. All internal users access production systems with admin-level credentials. Multi-Factor Authentication (MFA) is not enforced. This creates significant insider threat exposure and violates the principle of least privilege.

### 2. Manual Onboarding Process
New client onboarding is handled entirely via email and spreadsheet. There is no defined workflow, SLA, or handoff process between Sales, Implementation, and Support. Average onboarding time is 18 business days — industry benchmark for similar platforms is 7–10 days.

### 3. No Formal Risk Management Framework
There is no risk register, no recurring risk review cycle, and no defined risk appetite. Security and operational decisions are made reactively rather than proactively.

### 4. Limited Monitoring and Audit Capabilities
There are no centralized logs, no SIEM, and no alerting for suspicious access patterns. Audit trails are incomplete, making incident investigation difficult.

### 5. Regulatory Non-Compliance (GDPR)
CloudBase processes personal data of European residents and has not completed a Data Protection Impact Assessment (DPIA). Data retention policies are undefined, and there is no formal process for handling Data Subject Access Requests (DSARs).

---

## Business Objectives

The following objectives were defined in collaboration with the executive sponsor and department heads:

| Priority | Objective | Success Metric |
|----------|-----------|----------------|
| Critical | Achieve GDPR baseline compliance | Pass regulatory review; complete DPIA |
| High | Implement access control model | RBAC + MFA deployed within 90 days |
| High | Reduce onboarding time | Target: ≤ 10 business days |
| Medium | Establish risk management framework | Risk register active; quarterly reviews |
| Medium | Improve audit and monitoring capabilities | Centralized logging within 6 months |

---

## Constraints and Assumptions

**Constraints:**
- Budget is limited; solutions must be prioritized by risk reduction value
- Engineering team has limited availability; process and governance changes should minimize tech dependency where possible
- The company does not have a dedicated security team

**Assumptions:**
- Executive leadership is committed to the improvement program
- The regulatory inquiry provides a 6-month window before formal action
- Cloud infrastructure is hosted on AWS (existing tooling can be leveraged)
