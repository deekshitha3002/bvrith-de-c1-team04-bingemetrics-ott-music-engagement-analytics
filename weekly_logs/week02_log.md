# Week 02 Log — Dataset Design + Data Dictionary

**Week:** 2  
**Date range:** 17/7/2026 - 24/7/2026
**Team:** 4 
**Project:** BingeMetrics - OTT & Music Engagement Analytics

---

## 1. Sprint Goal

The goal of this sprint is to design and document the dataset structure for the BingeMetrics project. This includes preparing the data dictionary, defining the source files and their schemas, documenting synthetic data assumptions, and organizing the sample datasets for the project.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Updated `docs/data_dictionary.md`  | Deekshitha Rathod | Done | `docs/data_dictionary.md` |
| Updated `docs/synthetic_data_assumptions.md` | Deekshitha Rathod | Done | `docs/synthetic_data_assumptions.md` |
| Updated `src/generate_synthetic_data.py` | Deekshitha Rathod | Done | `src/generate_synthetic_data.py` |
| Added small raw sample files to `data_sample/raw/` | Deekshitha Rathod | Done | `data_sample/raw/` |
| Reviewed dataset design and documented primary/foreign key relationships | Deekshitha Rathod | Done | `docs/data_dictionary.md` |
| Captured Week 2 evidence screenshots | Deekshitha Rathod | Done | `week02_data_dictionary_completed.png`, `week02_raw_sample_files.png` |
---

## 3. Key Decisions

- Used the official BingeMetrics Student Data Pack as the source dataset.
- Documented the data dictionary and synthetic data assumptions based on the project requirements.

---

## 4. Blockers / Risks
| Blocker                                    | Impact                               | Help Needed                                         |
| ------------------------------------------ | ------------------------------------ | --------------------------------------------------- |
| Understanding the project folder structure | Delayed organizing the project files | Referred to the project brief and mentor guidelines |

---

## 5. Evidence Added to GitHub

- File updated
- Screenshot added


---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped prepare the data dictionary, synthetic data assumptions, and weekly log content. |
| What we changed after AI suggestion | Updated the templates with project-specific file names and field details for the BingeMetrics project. |
| What we verified manually | Verified the source files, folder structure, and project requirements using the official data pack and project brief. |
| What we can explain without AI | We can explain the dataset structure, source files, data dictionary, and synthetic data assumptions used in the project. |

---

## 7. Next Week Preparation

- Set up the Databricks environment and load the source data files.
- Explore the dataset by checking the schema, row counts, and basic data quality issues before starting Bronze layer ingestion.
