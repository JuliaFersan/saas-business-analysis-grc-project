# 04 — Requirements

## Overview

This document presents the functional and non-functional requirements identified through stakeholder interviews, process analysis, and the gap assessment. Requirements are prioritized using the MoSCoW method.

---

## Functional Requirements

### Access Control (AC)

| ID | Requirement | Priority | Stakeholder |
|----|-------------|----------|-------------|
| AC-01 | The system must support Role-Based Access Control (RBAC) with at least 5 predefined roles | Must Have | CTO, Legal |
| AC-02 | Multi-Factor Authentication (MFA) must be enforced for all user accounts | Must Have | CTO, CEO |
| AC-03 | Access provisioning must follow a documented approval workflow | Must Have | Head of Ops |
| AC-04 | Quarterly access reviews must be conducted and documented | Must Have | Legal/DPO |
| AC-05 | An automated offboarding process must revoke access within 24 hours of departure | Must Have | Engineering |
| AC-06 | Admin-level access must require a secondary approval beyond the direct manager | Should Have | CTO |
| AC-07 | The system should support Single Sign-On (SSO) integration | Could Have | Engineering |

### Client Onboarding (CO)

| ID | Requirement | Priority | Stakeholder |
|----|-------------|----------|-------------|
| CO-01 | The onboarding workflow must be managed through a ticketing system with defined stages | Must Have | Head of Ops |
| CO-02 | Each onboarding stage must have a defined SLA with automated escalation | Must Have | Head of Ops |
| CO-03 | Data entry must occur once at deal closure and propagate to all downstream systems | Must Have | Engineering |
| CO-04 | Clients must have access to a portal showing real-time onboarding status | Should Have | Sales |
| CO-05 | Automated welcome email and credentials must be sent within 24 hours of provisioning | Must Have | Support |
| CO-06 | The system should generate an onboarding checklist for each new client | Should Have | Operations |

### Compliance & Data Protection (CDP)

| ID | Requirement | Priority | Stakeholder |
|----|-------------|----------|-------------|
| CDP-01 | A Data Protection Impact Assessment (DPIA) must be completed for all processing activities | Must Have | Legal/DPO |
| CDP-02 | Data retention policies must be defined and implemented for all data categories | Must Have | Legal/DPO |
| CDP-03 | A process for handling Data Subject Access Requests (DSARs) must be defined with 30-day SLA | Must Have | Legal/DPO |
| CDP-04 | A Data Processing Register must be maintained and reviewed quarterly | Must Have | Legal/DPO |
| CDP-05 | Privacy notices must be updated to reflect current data processing activities | Must Have | Legal/DPO |

### Monitoring & Audit (MA)

| ID | Requirement | Priority | Stakeholder |
|----|-------------|----------|-------------|
| MA-01 | Centralized logging must capture all access events to production systems | Must Have | CTO |
| MA-02 | Alerts must be configured for anomalous access patterns (e.g., off-hours admin access) | Must Have | Engineering |
| MA-03 | Audit logs must be retained for a minimum of 12 months | Must Have | Legal/DPO |
| MA-04 | Monthly security reports must be generated and reviewed by the CTO | Should Have | CEO |

---

## Non-Functional Requirements

| ID | Requirement | Category | Priority |
|----|-------------|----------|----------|
| NFR-01 | Solutions must be implementable within existing AWS infrastructure where possible | Feasibility | Must Have |
| NFR-02 | New processes must not increase Engineering team workload by more than 15% during implementation | Performance | Must Have |
| NFR-03 | All documentation must be maintained in a version-controlled repository | Maintainability | Must Have |
| NFR-04 | RBAC configuration must be auditable and exportable for compliance reporting | Auditability | Must Have |
| NFR-05 | Access provisioning to new employees must complete within 1 business day | Performance | Should Have |
| NFR-06 | Security controls must not degrade platform uptime below 99.5% SLA | Reliability | Must Have |

---

## Requirements Traceability Matrix (Excerpt)

| Requirement | Business Objective | Risk Addressed | Deliverable |
|-------------|-------------------|----------------|-------------|
| AC-01, AC-02 | Strengthen access control | RISK-01 (Unauthorized access) | RBAC design doc |
| CO-01, CO-02 | Reduce onboarding time | RISK-05 (Client churn) | Onboarding process flow |
| CDP-01 to CDP-05 | GDPR compliance | RISK-03 (Regulatory fine) | DPIA document |
| MA-01, MA-02 | Improve audit capability | RISK-04 (Incident detection) | Logging architecture |
