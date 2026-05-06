# 06 — Controls & Mitigation

## Overview

This document maps each identified risk to recommended controls, classifying them by control type and implementation priority. Controls are aligned with ISO 27001 Annex A and NIST CSF functions.

---

## Control Classification

| Type | Description |
|------|-------------|
| **Preventive** | Prevents the risk from occurring |
| **Detective** | Detects when a risk event has occurred |
| **Corrective** | Reduces the impact after a risk event |
| **Administrative** | Policies, procedures, training |

---

## Risk-to-Control Mapping

### RISK-01 & RISK-02 — Unauthorized Access / Insider Threat

| Control ID | Control | Type | ISO 27001 | NIST CSF | Priority |
|------------|---------|------|-----------|----------|----------|
| CTRL-01 | Implement RBAC model with 5 defined roles | Preventive | A.9.1.2 | PR.AC-4 | Critical |
| CTRL-02 | Enforce MFA for all user accounts | Preventive | A.9.4.2 | PR.AC-7 | Critical |
| CTRL-03 | Apply principle of least privilege to all access grants | Preventive | A.9.1.2 | PR.AC-6 | Critical |
| CTRL-04 | Implement centralized access logging and audit trail | Detective | A.12.4.1 | DE.CM-3 | Critical |
| CTRL-05 | Conduct quarterly access reviews | Administrative | A.9.2.5 | PR.AC-1 | High |

---

### RISK-03 — GDPR Non-Compliance

| Control ID | Control | Type | ISO 27001 | NIST CSF | Priority |
|------------|---------|------|-----------|----------|----------|
| CTRL-06 | Complete Data Protection Impact Assessment (DPIA) | Administrative | A.18.1.4 | ID.GV-3 | Critical |
| CTRL-07 | Define and implement data retention and deletion policies | Administrative | A.18.1.3 | PR.IP-6 | Critical |
| CTRL-08 | Establish DSAR handling process with 30-day SLA | Administrative | A.18.1.4 | RS.CO-3 | Critical |
| CTRL-09 | Maintain a Data Processing Register | Administrative | A.18.1.4 | ID.AM-3 | High |
| CTRL-10 | Update privacy notices to reflect current data processing | Administrative | A.18.1.4 | ID.GV-1 | High |
| CTRL-11 | Formalize or appoint DPO role | Administrative | A.6.1.1 | ID.GV-2 | High |

---

### RISK-04 — Incident Detection Gap

| Control ID | Control | Type | ISO 27001 | NIST CSF | Priority |
|------------|---------|------|-----------|----------|----------|
| CTRL-12 | Implement centralized logging (AWS CloudTrail + CloudWatch) | Detective | A.12.4.1 | DE.AE-3 | Critical |
| CTRL-13 | Configure alerts for anomalous access patterns | Detective | A.12.4.2 | DE.CM-7 | Critical |
| CTRL-14 | Define and document incident response procedure | Corrective | A.16.1.1 | RS.RP-1 | High |
| CTRL-15 | Retain audit logs for minimum 12 months | Administrative | A.12.4.1 | PR.PT-1 | High |

---

### RISK-05 — Client Onboarding Inefficiency

| Control ID | Control | Type | Priority |
|------------|---------|------|----------|
| CTRL-16 | Implement ticketing system for onboarding workflow | Preventive | High |
| CTRL-17 | Define SLAs for each onboarding stage | Administrative | High |
| CTRL-18 | Eliminate duplicate data entry through CRM integration | Preventive | Medium |
| CTRL-19 | Build client portal for onboarding status visibility | Preventive | Medium |

---

### RISK-06 — Enterprise Sales Blocked

| Control ID | Control | Type | Priority |
|------------|---------|------|----------|
| CTRL-20 | Build GRC documentation package for security questionnaires | Administrative | High |
| CTRL-21 | Define roadmap toward ISO 27001 or SOC 2 certification | Administrative | Medium |

---

### RISK-07 — Ghost Accounts

| Control ID | Control | Type | Priority |
|------------|---------|------|----------|
| CTRL-22 | Integrate HR system with IAM for automated offboarding | Preventive | High |
| CTRL-23 | Conduct retroactive audit of all active accounts | Detective | Critical |
| CTRL-24 | Define offboarding checklist and SLA (access revoked within 24h) | Administrative | Critical |

---

### RISK-08 — Compromised Account / Data Breach

| Control ID | Control | Type | Priority |
|------------|---------|------|----------|
| CTRL-25 | Enforce MFA (shared with CTRL-02) | Preventive | Critical |
| CTRL-26 | Implement password complexity and rotation policy | Preventive | High |
| CTRL-27 | Evaluate passwordless authentication for admin accounts | Preventive | Medium |
| CTRL-28 | Conduct phishing awareness training for all staff | Administrative | High |

---

## Control Implementation Summary

| Priority | Count | Controls |
|----------|-------|----------|
| Critical | 11 | CTRL-01, 02, 03, 04, 06, 07, 08, 12, 13, 23, 24 |
| High | 12 | CTRL-05, 09, 10, 11, 14, 15, 16, 17, 20, 22, 26, 28 |
| Medium | 5 | CTRL-18, 19, 21, 27 + retroactive audits |

**Total controls defined: 28**
