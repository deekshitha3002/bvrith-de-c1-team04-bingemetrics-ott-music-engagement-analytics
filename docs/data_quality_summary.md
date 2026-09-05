# Data Quality Summary

**Week:** 6  
**Purpose:** Summarize the data quality checks, failures, and business impact for the BingeMetrics project.

---

## 1. Quality Rule Results

| Rule ID | Rule Name | Severity | Passed Count | Failed Count | Business Impact |
|---|---|---|---:|---:|---|
| DQ-CNT-001 | Content data quality validation | Critical | 2,980 | 10 | Invalid content records affect content analysis |
| DQ-USR-001 | User data quality validation | Critical | 24,975 | 0 | Invalid user records affect user-level metrics |
| DQ-SUB-001 | Subscription data quality validation | Critical | 34,755 | 225 | Invalid subscriptions affect subscription analysis |
| DQ-SES-001 | Session ID and duplicate validation | Critical | 249,701 | 0 | Missing or duplicate sessions affect usage metrics |
| DQ-SES-002 | Session reference validation | Critical | 249,701 | 0 | Invalid references affect joins and session analysis |
| DQ-SES-003 | Session chronology and date-window validation | Major | 249,701 | 0 | Invalid timestamps affect time-based metrics |
| DQ-SES-004 | Duration and playback validation | Major | 249,701 | 0 | Incorrect playback data affects engagement metrics |
| DQ-SES-005 | Session outcome consistency validation | Major | 249,701 | 0 | Incorrect completion/skip data affects viewing behaviour |

> The rule-failure scorecard shows 10 failures for Content and 225 failures for Subscriptions, while all five Session rules and the Users rule have 0 failures. :contentReference[oaicite:1]{index=1}

---

## 2. Failed Record Examples

| Rule ID | Sample Record ID | Failure Reason | Action / Handling |
|---|---|---|---|
| DQ-CNT-001 | `[record_key from quarantine_content]` | Content record failed the approved content-quality checks | Routed to Quarantine for correction and reprocessing |
| DQ-SUB-001 | `[record_key from quarantine_subscriptions]` | Subscription record failed the approved subscription-quality checks | Routed to Quarantine for correction and reprocessing |

---

## 3. What Should Block Gold Metrics?

- **DQ-CNT-001** – Critical content-quality issues.
- **DQ-USR-001** – Critical user-quality issues.
- **DQ-SUB-001** – Critical subscription issues.
- **DQ-SES-001** – Missing or duplicate session records.
- **DQ-SES-002** – Invalid session references.
- **DQ-SES-003 to DQ-SES-005** – Flag affected session and engagement metrics.

---

## 4. Quality Summary

The Week 6 BingeMetrics notebook evaluates eight approved Data Quality rules across Content, Users, Subscriptions and Sessions. The checks follow the required dependency order before session reference validation. :contentReference[oaicite:2]{index=2}

The results identified **10 failed Content records** and **225 failed Subscription records**. Users and Sessions passed all their applicable DQ rules. :contentReference[oaicite:3]{index=3}

Valid records are routed to Trusted tables and failed records are routed to Quarantine tables. Multiple failures are retained together on the same physical Quarantine row. :contentReference[oaicite:4]{index=4}

### Final Routing Counts

| Entity | Candidate | Trusted | Quarantine |
|---|---:|---:|---:|
| Content | 2,990 | 2,980 | 10 |
| Users | 24,975 | 24,975 | 0 |
| Subscriptions | 34,980 | 34,755 | 225 |
| Sessions | 249,701 | 249,701 | 0 |

The reconciliation passed for **all four entities**, with zero row variance and zero Trusted–Quarantine overlap. :contentReference[oaicite:5]{index=5}

Therefore:

**Candidate = Trusted + Quarantine** for Content, Users, Subscriptions and Sessions, with reconciliation status **PASS** for all four entities.
