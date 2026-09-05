# Week 05 Log — Silver Standardization

**Week:** 5  
**Date range:** 7/8/2026 - 14/8/2026  
**Team:** 4  
**Project:** BingeMetrics – OTT Music Engagement Analytics

---

## 1. Sprint Goal

Silver Standardization - Clean standardized Silver tables

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| ----------------------------------- | --------- | -------------------- | ----------------------------------- |
| Created Silver Users table           | Deekshitha Rathod | Done                 | silver_users           |
| Created Silver Subscriptions table   | Deekshitha Rathod | Done                 | silver_subscriptions   |
| Created Silver Sessions table        | Deekshitha Rathod | Done                 | silver_sessions        |
| Created Silver Content Catalog table | Deekshitha Rathod | Done                 | silver_content_catalog |
| Verified Silver tables                | Deekshitha Rathod | Done                 | verified tables/screenshots   |

---

## 3. Key Decisions

- Used the existing Bronze Delta tables as the source for the Silver layer.
- Removed duplicate records using available business IDs such as user_id, subscription_id, session_id, and content_id.
- Standardized relevant date, timestamp, status, and flag columns.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Some source columns may have different names or data types | Transformations may need adjustment | Verify source schemas |
| Optional columns may not exist in every dataset | Some transformations cannot be applied | Schema validation 

---

## 5. Evidence Added to GitHub

- Weekly_logs:week05 updated
- Silver tables Screenshots added
- Silver_transformations.ipynb Notebook updated

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped us understand the Bronze-to-Silver data transformation process and suggested suitable data-cleaning steps. |
| What we changed after AI suggestion | We modified the suggested code to match our project tables, column names, data types, and requirements. |
| What we verified manually | We checked the transformed data, table schemas, data types, duplicate records, NULL values, and output tables. |
| What we can explain without AI | We can explain the Bronze-to-Silver flow, data cleaning, standardization, deduplication, transformations, and Delta table creation. |

---

## 7. Next Week Preparation

- Review and validate the Silver tables with sample records.
- Identify relationships between the Silver tables.
- Prepare transformations required for the Gold layer.
- Start designing analytics-ready Gold tables.
