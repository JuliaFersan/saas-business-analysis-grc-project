# 03 — Process Mapping

## Overview

This document presents the As-Is and To-Be process maps for the two most critical processes identified during the analysis:

1. **Client Onboarding Process** — highest inefficiency and client satisfaction impact
2. **User Access Provisioning** — highest security risk exposure

Processes are described in BPMN notation (swimlane format). Visual diagrams are available in the `/images` folder.

---

## Process 1: Client Onboarding

### As-Is Process (Current State)

**Duration:** 18 business days (average)
**Pain points:** Manual handoffs via email, no SLA, repeated data entry, no visibility into status

```
[Sales]        [Operations]      [Engineering]     [Support]
   │                │                  │               │
   ▼                │                  │               │
Close Deal          │                  │               │
   │                │                  │               │
   ▼                │                  │               │
Send email ────────►│                  │               │
to Ops              │                  │               │
                    ▼                  │               │
                 Create                │               │
                 spreadsheet           │               │
                    │                  │               │
                    ▼                  │               │
                 Manual email ────────►│               │
                 to Engineering        │               │
                                       ▼               │
                                    Provision          │
                                    account            │
                                       │               │
                                       ▼               │
                                    Email ────────────►│
                                    to Support         │
                                                       ▼
                                                   Manual          
                                                   welcome email   
                                                   to client       
```

**Identified Issues:**
- 4 manual handoffs with no tracking
- No defined SLA at any stage
- Data re-entered 3 times across systems
- No client visibility into onboarding status
- Average delay between steps: 2–4 business days

---

### To-Be Process (Target State)

**Target Duration:** ≤ 10 business days
**Improvements:** Ticketing system, automated notifications, defined SLAs, client portal status

```
[Sales]        [Operations]      [Engineering]     [Client Portal]
   │                │                  │               │
   ▼                │                  │               │
Close Deal          │                  │               │
   │                │                  │               │
   ▼                │                  │               │
Create ticket  ────►│                  │               │
in CRM              │                  │               │
                    ▼                  │               │
                 Automated             │               │
                 task assignment       │               │
                    │                  │               │
                    ▼                  │               │
                 SLA: 2 days ─────────►│               │
                 provision             │               │
                                       ▼               │
                                   Automated ─────────►│
                                   account + portal    │
                                   access              ▼
                                                   Client receives
                                                   welcome email +
                                                   portal access
                                                   (Day 3)
```

**Improvements:**
- Single data entry point (CRM → all systems)
- Automated handoffs with SLA timers
- Client portal for real-time onboarding visibility
- Estimated onboarding time: 7–10 business days

---

## Process 2: User Access Provisioning

### As-Is Process (Current State)

**Risk level:** Critical — no least-privilege principle applied

```
[HR / Manager]     [IT/Engineering]
      │                  │
      ▼                  │
New employee joins        │
      │                  │
      ▼                  │
Verbal or email ─────────►│
request                   │
                          ▼
                      Admin creates
                      account with
                      full access
                          │
                          ▼
                      No documentation
                      No review cycle
```

**Issues:**
- All users receive admin-level access by default
- No approval workflow
- No periodic access reviews
- MFA not enforced
- No offboarding process (departed employees may retain access)

---

### To-Be Process (Target State)

```
[HR System]      [Manager]       [IT/Security]    [IAM System]
     │               │                │               │
     ▼               │                │               │
Employee joins        │                │               │
auto-triggers         │                │               │
     │               │                │               │
     ▼               │                │               │
Access Request ──────►│                │               │
form generated        ▼                │               │
                  Manager             │               │
                  approves role ──────►│               │
                                       ▼               │
                                   Maps to ───────────►│
                                   RBAC role           │
                                                       ▼
                                                  Provision with
                                                  least-privilege
                                                  + MFA enforced
                                                       │
                                                       ▼
                                                  Quarterly
                                                  access review
                                                  scheduled
```

**RBAC Model Defined:**

| Role | Access Level | Systems |
|------|-------------|---------|
| Support Agent | Read-only | CRM, ticketing |
| Account Manager | Read/Write | CRM, client portal |
| Engineer | Read/Write | Dev/staging environments only |
| Admin | Full access | Requires 2nd approval + MFA |
| Executive | Dashboard view | Reporting tools only |
