# Data Quality Summary

**Week:** 6  
**Purpose:** Summarize the data quality checks, failures, and their business impact for the BingeMetrics project.

---

## 1. Quality Rule Results

| Rule ID | Rule Name | Severity | Passed Count | Failed Count | Business Impact |
|---|---|---|---:|---:|---|
| DQ-CNT-001 | Content data validity check | Critical | [count] | [count] | Invalid content data affects content analysis and recommendations |
| DQ-USR-001 | User data validity check | Critical | [count] | [count] | Invalid user records affect user-based metrics |
| DQ-SUB-001 | Subscription validity check | Critical | [count] | [count] | Invalid subscriptions affect subscription and revenue metrics |
| DQ-SES-001 | Session ID and duplicate check | Critical | [count] | [count] | Duplicate or missing session IDs distort usage metrics |
| DQ-SES-002 | Session reference validation | Critical | [count] | [count] | Invalid references affect user, content and subscription joins |
| DQ-SES-003 | Session timestamp validation | Major | [count] | [count] | Invalid timestamps affect time-based analysis |
| DQ-SES-004 | Playback duration validation | Major | [count] | [count] | Incorrect playback values affect engagement metrics |
| DQ-SES-005 | Session outcome consistency | Major | [count] | [count] | Incorrect completion/skip data affects viewing behaviour analysis |

---

## 2. Failed Record Examples

| Rule ID | Sample Record ID | Failure Reason | Action / Handling |
|---|---|---|---|
| [Rule ID] | `[record_key]` | [Failure reason] | Record routed to Quarantine for correction and reprocessing |

---

## 3. What Should Block Gold Metrics?

The following rules should block or flag Gold table generation when critical data-quality issues are present:

- **DQ-CNT-001** – Invalid content records can affect content-based metrics.
- **DQ-USR-001** – Invalid user records can affect user-level metrics.
- **DQ-SUB-001** – Invalid subscription records can affect subscription metrics.
- **DQ-SES-001** – Missing or duplicate session IDs can distort usage metrics.
- **DQ-SES-002** – Invalid session references can affect joins and business metrics.
- **DQ-SES-003, DQ-SES-004 and DQ-SES-005** should flag affected engagement metrics.

---

## 4. Quality Summary

The Week 6 Data Quality pipeline was implemented for the BingeMetrics project.  
Data was validated using the approved Content, Users, Subscriptions and Sessions rules.  
Critical and major quality issues were identified through the DQ checks.  
Valid records were routed to Trusted tables, while failed records were routed to Quarantine tables.  
DQ metadata such as status, failed rule IDs, failure reasons and severity was recorded.  
The DQ Scorecard was used to review rule-level failures.  
Reconciliation was performed to verify the Candidate data was properly divided between Trusted and Quarantine outputs.  
Critical failures should be reviewed before generating Gold-level business metrics.
