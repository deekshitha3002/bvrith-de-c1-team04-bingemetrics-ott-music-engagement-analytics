# Week 06 Log — Data Quality Checks

**Week:** 6  
**Date range:** 31/8/2026 - 6/9/2026  
**Team:** 4  
**Project:** BingeMetrics – OTT Music Engagement Analytics

---

## 1. Sprint Goal

Implement and validate the Week 6 Data Quality checks for the BingeMetrics project, ensuring that Candidate data is properly classified into Trusted and Quarantine tables based on the approved DQ rules.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Confirmed Candidate input tables | Deekshitha Rathod | Done | `week06_confirm_candidate_inputs.png` |
| Implemented Content DQ checks | Deekshitha Rathod | Done | `week06_contentDQ.png` |
| Implemented Users DQ checks | Deekshitha Rathod | Done | Data Quality Notebook |
| Implemented Subscriptions DQ checks | Deekshitha Rathod | Done | Data Quality Notebook |
| Implemented Sessions DQ checks | Deekshitha Rathod | Done | `week06_sessionDQ.png` |
| Created Trusted & Quarantine outputs | Deekshitha Rathod | Done | Data Quality Notebook |
| Performed reconciliation | Deekshitha Rathod | Done | `week06_reconciliation.png` |

---

## 3. Key Decisions

- Followed the dependency order of Content → Users → Subscriptions → Sessions.
- Used Trusted records for reference validation in downstream Sessions checks.
- Kept all applicable failed rule IDs and failure reasons for each physical record.
- Used dq_status to route records into Trusted (PASS) or Quarantine (FAIL).
- Added a physical record_key to track individual records through the DQ process.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Differences in column names between source tables | Could cause column reference errors | Verify Silver table schemas |
| Session validation depends on Trusted reference tables | DQ checks must run in dependency order | Ensure previous DQ stages complete successfully |
| Some approved dictionary values were not explicitly provided | Values should not be assumed | Follow project-approved configuration |

---
## 5. Evidence Added to GitHub

- Data Quality Notebook added
- Candidate input validation screenshots
- Content DQ execution screenshot
- Sessions DQ execution screenshot
- DQ Scorecard screenshot
- Reconciliation screenshot
- Trusted and Quarantine output evidence
---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped us understand the Week 6 Data Quality requirements and suggested approaches for implementing DQ rules, Trusted/Quarantine routing and reconciliation. |
| What we changed after AI suggestion | We modified the suggested code to match our BingeMetrics tables, column names, DQ rule IDs and project requirements. |
| What we verified manually | We verified table schemas, column mappings, DQ conditions, failed rule IDs, DQ status, Trusted/Quarantine outputs and reconciliation results. |
| What we can explain without AI | We can explain the DQ validation process, rule execution, dependency checks, Trusted/Quarantine routing, metadata and reconciliation. |


---

## 7. Next Week Preparation

- Use the Trusted datasets as the source for creating Gold layer tables.
- Design business-focused Gold tables for transaction risk monitoring and fraud analysis.
- Create aggregated metrics and KPIs for dashboards and reporting.
- Ensure that Quarantine records are excluded from Gold layer calculations unless corrected and revalidated.
