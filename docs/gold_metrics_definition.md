# Gold Metrics Definition

**Week:** 7  
**Purpose:** Define dashboard-ready Gold tables and KPI formulas.

---

## 1. Gold Table Catalog

| Gold Table Name | Grain | Source Table(s) | Purpose |
|---|---|---|---|
| `gold_users` | One row per user | `trusted_users` | User dimension |
| `gold_content` | One row per content item | `trusted_content` | Content dimension |
| `gold_subscriptions` | One row per subscription | `trusted_subscriptions` | Subscription analytics |
| `gold_sessions` | One row per session | `trusted_sessions` | Enriched session fact |
| `gold_user_engagement` | One row per user | `gold_sessions` | User engagement KPIs |
| `gold_content_performance` | One row per content item | `gold_sessions`, `gold_content` | Content performance KPIs |
| `gold_daily_engagement` | One row per day | `gold_sessions` | Daily engagement trends |

---

## 2. KPI Definitions

| KPI Name | Formula | Grain | Dashboard Page | Notes |
|---|---|---|---|---|
| Total Sessions | `COUNT(*)` | Daily / User / Content | Engagement Overview | Total number of sessions |
| Unique Users | `COUNT(DISTINCT user_id)` | Daily | Engagement Overview | Number of distinct users |
| Total Consumed Minutes | `SUM(consumed_seconds) / 60` | Daily / User / Content | Engagement Overview | Total engagement time |
| Average Session Duration | `AVG(consumed_seconds)` | Daily / User / Content | Engagement Overview | Average session duration |
| Completed Sessions | `SUM(CASE WHEN reported_completed_flag = true THEN 1 ELSE 0 END)` | Daily / User / Content | Engagement Overview | Number of completed sessions |
| Skipped Sessions | `SUM(CASE WHEN reported_skipped_flag = true THEN 1 ELSE 0 END)` | Daily / User / Content | Engagement Overview | Number of skipped sessions |
| Completion Rate % | `(Completed Sessions / Total Sessions) * 100` | Daily / Content | Content Analytics | Percentage of completed sessions |
| Unique Viewers | `COUNT(DISTINCT user_id)` | Content | Content Analytics | Number of unique viewers |

---

## 3. Validation Checks

Before using Gold tables in Power BI, verify:

- Gold row counts are reasonable.
- No unexpected nulls exist in key dashboard fields.
- Duplicate keys are checked.
- KPI totals match manual spot checks.
- `gold_sessions` row count matches the trusted session row count.
- No join multiplication occurs in `gold_sessions`.
- Power BI connects to Gold outputs only.
- Metric definitions are documented clearly.
- Gold tables contain dashboard-ready data.
