# Dashboard Insights

**Week:** 9  
**Purpose:** Explain the key observations from the refined Power BI dashboard and provide traceability to the owning Gold table.

---

## 1. Dashboard Page

| Page | Purpose | Main Visuals |
|---|---|---|
| BingeMetrics — Engagement Overview | Show the overall engagement picture, daily engagement trends, and content performance | KPI cards, Daily Sessions line chart, Daily Consumption line chart, Content Performance table |

---

## 2. Key Insights

### Insight 1 — Animation Content Sessions

**Question/Decision:**  
How many sessions are associated with Animation content?

**Observation:**  
When the dashboard is filtered to the Animation genre, the Content Performance table shows **15,009 total sessions**.

**Filter/Time Scope:**  
Genre = Animation

**Visual/Page:**  
BingeMetrics — Engagement Overview — Content Performance table

**Owning Gold:**  
`workspace.default.gold_content_performance`

**Measure/Field:**  
`total_sessions`

**Evidence:**  
The Power BI filtered value was reconciled against the Gold table using:

```sql
SELECT
    SUM(total_sessions) AS total_sessions
FROM workspace.default.gold_content_performance
WHERE genre = 'Animation';
---

## 3. How the Dashboard Uses Gold Tables

| Dashboard Page / Visual | Gold Table Used                              | Important Fields                                                                                                               |
| ----------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| KPI Cards               | `workspace.default.gold_daily_engagement`    | `total_sessions`, `total_consumed_minutes`, `completed_sessions`, `skipped_sessions`                                           |
| Daily Sessions          | `workspace.default.gold_daily_engagement`    | `session_date`, `total_sessions`                                                                                               |
| Daily Consumption       | `workspace.default.gold_daily_engagement`    | `session_date`, `total_consumed_minutes`                                                                                       |
| Content Performance     | `workspace.default.gold_content_performance` | `content_id`, `content_type`, `genre`, `total_sessions`, `unique_viewers`, `total_consumed_minutes`, `completion_rate_percent` |


---

## 4. Power BI Validation

 Dashboard uses approved Gold outputs only.
 Dashboard filters were tested.
 KPI totals were reconciled against Gold checks.
 Filtered Content Performance value was reconciled against the owning Gold table.
 Screenshots are saved in screenshots/.
 Dashboard insights are traceable to the relevant Gold table and visual.
