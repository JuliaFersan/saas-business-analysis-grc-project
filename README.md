# SaaS Platform Optimization: Business Analysis & GRC Assessment
> A structured, end-to-end Business Analysis and GRC project simulating a real-world SaaS company scenario — built to demonstrate practical BA and GRC skills in a hiring context.

---

## Company: CloudBase Ltda (Fictional)

CloudBase is a mid-sized SaaS provider managing subscription services and sensitive customer data for B2B clients across Europe. Facing rapid growth, a GDPR inquiry, and enterprise clients demanding security evidence, the company needed a structured approach to governance, risk, and compliance.

---

## Visual Summary

| Risk Matrix | Implementation Roadmap |
|-------------|----------------------|
| ![Risk Matrix](images/risk_matrix.svg) | ![Roadmap](images/roadmap.svg) |

---

## Key Problems Identified

| # | Challenge | Severity |
|---|-----------|----------|
| 1 | No RBAC or MFA — all users had admin access | 🔴 Critical |
| 2 | No centralized logging or incident detection | 🔴 Critical |
| 3 | GDPR non-compliance (no DPIA, no retention policy) | 🔴 Critical |
| 4 | Manual onboarding — 18 days avg (benchmark: 7–10) | 🟠 High |
| 5 | No offboarding process — ghost accounts in production | 🟠 High |
| 6 | No risk management framework | 🔴 Critical |

---

## Project Scope

- Business context analysis and problem framing  
- Stakeholder identification, influence mapping, and RACI matrix  
- As-Is and To-Be process mapping (BPMN notation)  
- Functional and non-functional requirements (MoSCoW)  
- Risk register with 8 identified risks (Impact × Likelihood)  
- 28 controls mapped to ISO 27001 Annex A and NIST CSF  
- Gap analysis across 14 control domains  
- Strategic recommendations and 12-month implementation roadmap  

---

## 📁 Project Deliverables

| File | Description |
|------|-------------|
| [`01_business_context.md`](docs/01_business_context.md) | Company overview, challenges, objectives, constraints |
| [`02_stakeholder_analysis.md`](docs/02_stakeholder_analysis.md) | Stakeholder map, Power/Interest grid, RACI matrix |
| [`03_process_mapping.md`](docs/03_process_mapping.md) | As-Is and To-Be BPMN flows (onboarding + access provisioning) |
| [`04_requirements.md`](docs/04_requirements.md) | Functional and non-functional requirements (MoSCoW) |
| [`05_risk_assessment.md`](docs/05_risk_assessment.md) | Risk register — 8 risks with full detail and scoring |
| [`06_controls_mitigation.md`](docs/06_controls_mitigation.md) | 28 controls mapped to ISO 27001 and NIST CSF |
| [`07_gap_analysis.md`](docs/07_gap_analysis.md) | Gap analysis across ISO 27001 and NIST CSF 2.0 |
| [`08_recommendations_roadmap.md`](docs/08_recommendations_roadmap.md) | Prioritized recommendations + 3-phase roadmap |

---

## Key Outcomes

- **8 critical risks identified** — 5 rated Critical, 2 High, 1 Medium  
- **28 controls defined** — mapped to ISO 27001 Annex A and NIST CSF  
- **RBAC model designed** — 5 roles, least-privilege, MFA enforcement  
- **Onboarding redesigned** — from 18 days to a target of ≤10 business days  
- **GDPR remediation roadmap** — 5 priority actions toward baseline compliance  
- **NIST maturity target** — from 1.2/5 (current) to 3.0/5 (after roadmap)  
- **ISO 27001 coverage** — from 8% to a projected ~65% after 12 months  

---

## Tools & Frameworks

| Category | Detail |
|----------|--------|
| Process Mapping | BPMN 2.0 notation (Draw.io) |
| Risk Methodology | Impact × Likelihood matrix |
| Security Framework | ISO 27001:2022 (Annex A controls) |
| Risk Framework | NIST Cybersecurity Framework 2.0 |
| Access Model | Role-Based Access Control (RBAC) |
| Compliance | GDPR (EU), NIS2 |
| Documentation | Markdown, structured requirements (MoSCoW) |
| Version Control | GitHub |

---

##  Why This Project

This project simulates the kind of engagement a junior BA or GRC analyst might be handed on their first week: a company that grew fast, deprioritized governance, and is now facing the consequences. The goal was to work through it systematically — from stakeholder mapping to a deliverable roadmap — using the same frameworks referenced in job descriptions.

It is fictional, but built with the same structure and rigour I would apply in a real environment.

---

## Author

**Julia Sampaio**  
Aspiring Business Analyst & GRC Professional  
📍 Portugal · Open to remote and international opportunities

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/juliafersan)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?style=flat&logo=github)](https://github.com/JuliaFersan)
