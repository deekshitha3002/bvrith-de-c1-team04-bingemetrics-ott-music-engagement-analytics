# Week 04 Log — Source to Bronze

**Week:** 4  
**Date range:** 31/7/26 - 6/8.26
**Team:** 04 
**Project:** BingeMetrics – OTT Music Engagement Analytics

---

## 1. Sprint Goal

The goal of Week 4 was to ingest the approved source datasets into Bronze Delta
tables while preserving the source data and required lineage metadata.

We also validated source-to-Bronze row counts, metadata completeness, Delta
history, and controlled rerun stability using actual Databricks results.

---

## 2. Work Completeda

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Created and verified the approved source Volume and source files | Spriha Reddy Yamjala | Done | `week04_01_source_inventory.png` |
| Inspected source data, schema and record count before Bronze creation | Spriha Reddy Yamjala | Done | `week04_02_source_inspection.png` |
| Created the required Bronze Delta tables | Spriha Reddy Yamjala | Done | `week04_03_bronze_tables.png` |
| Verified Bronze table schema, business columns and technical metadata | Spriha Reddy Yamjala | Done | `week04_04_bronze_schema_metadata.png` |
| Reconciled source and Bronze row counts | Spriha Reddy Yamjala | Done | `week04_05_reconciliation.png` |
| Validated required metadata columns across Bronze tables | Spriha Reddy Yamjala | Done | `week04_06_metadata_validation.png` |
| Performed controlled rerun and verified stable counts | Spriha Reddy Yamjala | Done | `week04_07_repeat_run.png` |
| Inspected Delta table history | Spriha Reddy Yamjala | Done | `week04_08_delta_history.png` |
| Verified Bronze tables through Catalog Explorer | Spriha Reddy Yamjala | Done | `week04_09_catalog_view.png` |

---

## 3. Key Decisions

- Used the approved source files from the configured `week4_files` Volume as
  the input for Bronze ingestion.
- Created separate Bronze Delta tables for the approved source entities.
- Preserved the Bronze data and added the required ingestion metadata columns.
- Used source-to-Bronze count reconciliation to verify that rows were not lost
  during ingestion.
- Performed a controlled rerun and verified that the table counts remained
  stable.
- Used actual Databricks results for evidence rather than fabricated or copied
  results.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| No major blocker encountered during the Week 4 Bronze implementation. | No impact on completion. | None |

---

## 5. Evidence Added to GitHub

- `screenshots/week04_01_source_inventory.png`
- `screenshots/week04_02_source_inspection.png`
- `screenshots/week04_03_bronze_tables.png`
- `screenshots/week04_04_bronze_schema_metadata.png`
- `screenshots/week04_05_reconciliation.png`
- `screenshots/week04_06_metadata_validation.png`
- `screenshots/week04_07_repeat_run.png`
- `screenshots/week04_08_delta_history.png`
- `screenshots/week04_09_catalog_view.png`

- Week 4 Bronze/source-to-Bronze notebook updated and verified.
- Week 4 log updated with completed work and evidence.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI was used to understand the Week 4 requirements, organize the evidence checklist, and assist with SQL/query patterns and documentation. |
| What we changed after AI suggestion | Suggestions were compared with the internship instructions and the actual Databricks workspace before being used. Project-specific table names, columns and results were based on our actual implementation. |
| What we verified manually | We manually verified the source files, Bronze tables, schemas, metadata columns, source and Bronze counts, rerun results, Delta history and Catalog Explorer results in Databricks. |
| What we can explain without AI | We can explain the Source-to-Bronze flow, Bronze table creation, metadata/lineage purpose, count reconciliation, controlled rerun, and Delta table history. |

---

## 7. Next Week Preparation

- Review the approved project specification before starting transformations.
- Confirm the Week 4 Bronze tables, their schemas, lineage columns and baseline
  counts.
- Define the Bronze-to-Silver Candidate transformation mapping column by
  column.
- Identify the approved target data types, standardisation rules and
  calculated fields.
- Prepare the Week 5 `03_silver_transformations.ipynb` notebook.
