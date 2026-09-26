# Week 08 Log — Gold Hand-off to Power BI

**Week:** 8  
**Date range:** 12-09-2026 to 19-09-2026  
**Team:** Team 04  
**Project:** BingeMetrics – OTT & Music Engagement Analytics

---

## 1. Sprint Goal

Validate the approved Gold tables, create controlled Power BI-ready exports, and build the first working Power BI dashboard using only approved Gold data.

Reconcile key dashboard values against the owning Gold tables and establish a stable foundation for Week 9 dashboard refinement and insight generation.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Selected approved Gold tables for Power BI | R Sanjana | Done | Week 8 notebook |
| Validated Gold table grain, keys and row counts | R Sanjana | Done | Week 8 notebook |
| Created controlled CSV exports for selected Gold tables | R Sanjana | Done | `data_sample/gold_exports/` |
| Validated CSV read-back schemas and row counts | R Sanjana | Done | Week 8 notebook |
| Reconciled exported business totals to Gold | R Sanjana | Done | Week 8 notebook |
| Imported Gold exports into Power BI | R Sanjana | Done | Power BI model |
| Verified three Gold tables remain independent | R Sanjana | Done | Power BI model |
| Created KPI cards for engagement metrics | R Sanjana | Done | Power BI dashboard |
| Created Daily Sessions trend visual | R Sanjana | Done | Power BI dashboard |
| Created Daily Consumption trend visual | R Sanjana | Done | Power BI dashboard |
| Created Content Performance table | R Sanjana | Done | Power BI dashboard |
| Reconciled dashboard KPI values with Gold values | R Sanjana | Done | Power BI validation |

### Selected Gold tables

- `gold_daily_engagement` — one row per `session_date`
- `gold_content_performance` — one row per `content_id`
- `gold_user_engagement` — one row per `user_id`

### Export validation results

- Daily Engagement: 91 rows
- Content Performance: 3,400 rows
- User Engagement: 24,999 rows
- All selected Gold keys had zero null keys and zero duplicate keys.
- Export ordering was deterministic by the declared grain key.
- Exported business totals matched their respective Gold tables.

---

## 3. Key Decisions

- Used only approved Gold tables as the Power BI source.
- Selected three report-ready Gold aggregate tables instead of importing every available Gold table.
- Created a separate controlled export for each selected Gold table.
- Kept the three Power BI tables independent because they have different grains and no required safe relationship.
- Did not flatten the Gold tables into a single CSV.
- Used existing Gold measures directly rather than creating unsupported KPIs in Power BI.
- Preserved Gold values without manually correcting CSV values.
- Built the first dashboard around engagement and content-performance business questions rather than creating one visual per Gold table.
- Kept Week 9 dashboard refinement and insight storytelling outside the Week 8 scope.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Spark DataFrameWriter could not directly create CSV folders under the Databricks Workspace path | Required an alternative controlled export method | Resolved using Python file I/O with the validated Gold DataFrames |
| CSV read-back represented decimal minute values as floating-point values | Produced insignificant floating-point display differences such as `6241936.650000003` | No manual correction; Gold values were preserved |
| Multiple Gold tables have different grains | Direct relationships could introduce incorrect aggregation | Tables were kept independent |

No unresolved blockers remain for Week 8.

---

## 5. Evidence Added to GitHub

- `notebooks/06_powerbi_export.ipynb`
- `data_sample/gold_exports/gold_daily_engagement/gold_daily_engagement.csv`
- `data_sample/gold_exports/gold_content_performance/gold_content_performance.csv`
- `data_sample/gold_exports/gold_user_engagement/gold_user_engagement.csv`
- `dashboard/powerbi_dashboard.pbix`
- `dashboard/README.md`
- `screenshots/week08_*`
- `weekly_logs/week08_log.md`

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted with interpreting the Week 8 workflow, structuring validation steps, explaining Power BI modelling choices, and guiding the Gold-to-Power BI reconciliation process. |
| What we changed after AI suggestion | The team adapted the suggested workflow to the actual BingeMetrics Gold tables, repository structure, Databricks Workspace path, and Power BI model. |
| What we verified manually | Gold row counts, grain and key checks, export row counts, schemas, business totals, deterministic ordering, Power BI table independence, dashboard values, and visual outputs were manually checked. |
| What we can explain without AI | The team can explain the Gold table grains, export process, Power BI source mapping, relationship decision, dashboard KPIs, and how dashboard values were reconciled back to Gold. |

---

## 7. Next Week Preparation

- Continue using the same Power BI model and approved Gold sources.
- Refine dashboard layout, visual hierarchy, labels, formatting and usability.
- Test slicers, filters and visual interactions.
- Reconcile important filtered dashboard values against their owning Gold tables.
- Identify evidence-backed engagement and content-performance insights.
- Create `docs/dashboard_insights.md`.
- Prepare the dashboard for Week 9 presentation and storytelling.
