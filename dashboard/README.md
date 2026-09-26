# Power BI Dashboard Folder

Save the final Power BI file here.

Expected file:

```text
dashboard/powerbi_dashboard.pbix
```

Rules:

- Power BI must connect to Gold outputs only.
- Do not connect dashboard visuals directly to raw source files.
- Save dashboard screenshots in `screenshots/`.
- Explain dashboard insights in `docs/dashboard_insights.md`.

## Power BI File-Size Rule

Preferred submission is the PBIX file plus screenshots.

If the `.pbix` file becomes too large to manage cleanly in GitHub, keep the final screenshots and dashboard insight notes in this repo, and add a short note here explaining where the PBIX is stored for mentor review.

Do not keep uploading multiple heavy PBIX versions into GitHub.

## Week 9 Dashboard Refinement

The Week 9 dashboard was refined from the validated Week 8 Power BI dashboard.

### Final Dashboard

- Dashboard page: `BingeMetrics — Engagement Overview`
- KPI cards for overall engagement
- Daily Sessions trend
- Daily Consumption trend
- Content Performance table
- Genre filter for content-level analysis

### Gold Sources

The dashboard continues to use the approved Gold outputs:

- `workspace.default.gold_daily_engagement`
- `workspace.default.gold_content_performance`
- `workspace.default.gold_user_engagement`

The Gold tables remain independent because they have different grains and no unsafe relationships were introduced.

### Validation

Dashboard interactions and filtered values were tested manually.

For the Animation genre:

- Filter: `Animation`
- Measure: `total_sessions`
- Reconciled Gold value: **15,009**

The Power BI filtered Content Performance result matched the owning Gold-table query.

### Week 9 Evidence

Screenshots are stored in `screenshots/`:

- `week09_01_final_model.png`
- `week09_02_refined_page_01.png`
- `week09_04_filter_interaction.png`
- `week09_05_filtered_reconciliation.png`
- `week09_06_insights_evidence.png`

Detailed dashboard insights are documented in:

`docs/dashboard_insights.md`
