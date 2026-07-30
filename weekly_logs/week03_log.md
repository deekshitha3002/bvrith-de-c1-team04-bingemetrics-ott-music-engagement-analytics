# Week 03 Log — Bronze Demo & Data Exploration

**Week:** 3  
**Date range:** 24/7/26 - 30/7.26
**Team:** 4
**Project:** BingeMetrics – OTT Music Engagement Analytics

---

## 1. Sprint Goal

Learn the Databricks Bronze ingestion workflow by adapting the provided PageLoop notebook to the BingeMetrics project. Explore the project data, perform basic data-quality checks, and create one Bronze demo table with a lineage demo view.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Uploaded project files to Databricks Volume | R Sanjana | Done | Databricks Volume |
| Loaded project data into Spark DataFrames | R Sanjana | Done | Week 3 notebook |
| Created temporary SQL views | R Sanjana | Done | Week 3 notebook |
| Explored schema, grain, counts, and value distributions | R Sanjana | Done | `week03_03_schemas.png`, `week03_04_grain_counts_values.png` |
| Performed basic data-quality and relationship checks | R Sanjana | Done | `week03_05_relationship_checks.png` |
| Created Bronze demo Delta table (`bingemetrics_bronze_demo_subscriptions`) | R Sanjana | Done | `week03_06_bronze_demo.png` |
| Verified Delta history | R Sanjana | Done | `week03_07_delta_history.png` |
| Created lineage demo view | R Sanjana | Done | Week 3 notebook |
| Captured Week 3 evidence screenshots | R Sanjana | Done | `screenshots/` folder |

---

## 3. Key Decisions

- Adapted the PageLoop Week 3 notebook to the BingeMetrics project by using the **subscriptions** dataset as the demonstration source.
- Limited the implementation to **one Bronze demo table and one lineage demo view**, following the Week 3 scope. Full Bronze ingestion for all project datasets is deferred to Week 4.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| No major blockers | Week 3 tasks completed successfully | None |

---

## 5. Evidence Added to GitHub

- Updated Week 3 notebook
- Added Week 3 evidence screenshots
- Added Bronze demo table and lineage demonstration

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | Assisted in adapting the PageLoop notebook queries from the library dataset to the BingeMetrics project and explained Databricks concepts. |
| What we changed after AI suggestion | Updated SQL queries, Bronze table creation, lineage demo view, and documentation to match the BingeMetrics dataset. |
| What we verified manually | Verified query outputs, table creation, Delta history, lineage view, and evidence screenshots in Databricks. |
| What we can explain without AI | The Databricks workflow, Spark DataFrames, temporary views, Bronze demo table creation, basic data-quality checks, and lineage concepts used in Week 3. |

---

## 7. Next Week Preparation

- Create official Bronze tables for all project source files.
- Implement repeatable Bronze ingestion and complete the Week 4 Bronze pipeline.
