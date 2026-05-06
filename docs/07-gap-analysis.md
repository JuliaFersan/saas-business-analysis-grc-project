# 07 — Gap Analysis

## Overview

This gap analysis compares CloudBase's current security and governance posture against two frameworks:
- **ISO 27001:2022** (Information Security Management System)
- **NIST Cybersecurity Framework 2.0**

**Rating Scale:**
- 🔴 **Not Implemented** — No evidence of control existence
- 🟠 **Partially Implemented** — Some elements exist but incomplete or informal
- 🟡 **Planned** — Committed but not yet active
- 🟢 **Implemented** — Control is active and documented

---

## ISO 27001 Gap Analysis

### Clause 5 — Leadership

| Control Area | Current State | Gap | Priority |
|-------------|---------------|-----|----------|
| 5.1 Leadership commitment to ISMS | 🟠 Partial | No formal ISMS policy signed by leadership | High |
| 5.2 Information Security Policy | 🔴 Not Implemented | No documented IS policy exists | Critical |
| 5.3 Roles and responsibilities | 🟠 Partial | Informal; no documented IS roles | High |

---

### Annex A — Control Domains

#### A.5 — Information Security Policies

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.5.1 | Policies for information security | 🔴 Not Implemented | No formal IS policy |
| A.5.2 | Review of policies | 🔴 Not Implemented | No review cycle |

#### A.6 — Organization of Information Security

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.6.1 | Internal organization | 🟠 Partial | No ISMS roles formally assigned |
| A.6.3 | Information security in project management | 🔴 Not Implemented | Security not part of project lifecycle |

#### A.8 — Asset Management

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.8.1 | Inventory of assets | 🟠 Partial | Informal asset list exists in spreadsheet |
| A.8.2 | Classification of information | 🔴 Not Implemented | No data classification scheme |
| A.8.3 | Handling of assets | 🔴 Not Implemented | No formal handling procedures |

#### A.9 — Access Control *(Highest Gap Area)*

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.9.1.1 | Access control policy | 🔴 Not Implemented | No policy |
| A.9.1.2 | Access to networks | 🔴 Not Implemented | No segmentation |
| A.9.2.1 | User registration | 🟠 Partial | Informal via email |
| A.9.2.2 | User access provisioning | 🔴 Not Implemented | No formal process |
| A.9.2.3 | Privileged access | 🔴 Not Implemented | All users have admin |
| A.9.2.5 | Review of user access | 🔴 Not Implemented | No access reviews |
| A.9.4.2 | Secure log-on | 🟠 Partial | Password only; no MFA |

#### A.12 — Operations Security

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.12.4.1 | Event logging | 🔴 Not Implemented | No centralized logging |
| A.12.4.2 | Protection of log information | 🔴 Not Implemented | No logs to protect |
| A.12.4.3 | Admin and operator logs | 🔴 Not Implemented | — |
| A.12.4.4 | Clock synchronisation | 🟢 Implemented | AWS NTP in use |

#### A.16 — Incident Management

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.16.1.1 | Responsibilities and procedures | 🔴 Not Implemented | No IRP defined |
| A.16.1.2 | Reporting IS events | 🔴 Not Implemented | No reporting channel |
| A.16.1.5 | Response to IS incidents | 🔴 Not Implemented | — |

#### A.18 — Compliance

| Control | Description | Status | Gap |
|---------|-------------|--------|-----|
| A.18.1.1 | Identification of applicable legislation | 🟠 Partial | GDPR known but not fully addressed |
| A.18.1.3 | Protection of records | 🔴 Not Implemented | No retention policy |
| A.18.1.4 | Privacy and protection of PII | 🔴 Not Implemented | DPIA not completed |

---

## NIST CSF 2.0 Gap Analysis

| Function | Category | Current Maturity (1–5) | Target | Gap |
|----------|----------|----------------------|--------|-----|
| **GOVERN** | Organizational context | 1 | 3 | -2 |
| **GOVERN** | Risk management strategy | 1 | 3 | -2 |
| **IDENTIFY** | Asset management | 2 | 4 | -2 |
| **IDENTIFY** | Risk assessment | 1 | 4 | -3 |
| **PROTECT** | Identity management & access control | 1 | 4 | -3 |
| **PROTECT** | Awareness and training | 1 | 3 | -2 |
| **PROTECT** | Data security | 1 | 4 | -3 |
| **PROTECT** | Platform security | 2 | 3 | -1 |
| **DETECT** | Continuous monitoring | 1 | 4 | -3 |
| **DETECT** | Adverse event analysis | 1 | 3 | -2 |
| **RESPOND** | Incident management | 1 | 3 | -2 |
| **RECOVER** | Incident recovery | 1 | 3 | -2 |

**Overall maturity score: 1.2 / 5** → Target after roadmap: **3.0 / 5**

---

## Gap Summary

| Framework Area | # Controls Assessed | Implemented | Partial | Not Implemented |
|----------------|--------------------|-----------|---------|----|
| ISO 27001 Annex A | 24 | 2 (8%) | 5 (21%) | 17 (71%) |
| NIST CSF Functions | 12 | 0 (0%) | 2 (17%) | 10 (83%) |

**Highest priority gaps:** Access Control (A.9), Monitoring (A.12), Compliance (A.18), Incident Management (A.16)
