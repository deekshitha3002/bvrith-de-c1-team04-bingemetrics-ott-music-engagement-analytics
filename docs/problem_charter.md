# Problem Charter

**Week:** 1  
**Owner(s):** Deekshitha Rathod, R.Sanjana, Spriha Reddy  
**Project:** Bingemetrics ott music engagement analytics  

---

## 1. Problem Context

Streaming platforms like Netflix and Spotify generate millions of user interactions every day, such as playing content, pausing, skipping, completing a movie or song, and managing subscriptions. These events are stored across multiple data sources, including playback sessions, content catalogs, user profiles, and subscription records. Since this data is collected from different systems, it often contains duplicates, missing values, invalid records, and inconsistent formats, making it unreliable for business decisions.

This project builds a complete data engineering pipeline that ingests raw entertainment-platform data, cleans and validates it, combines related datasets, and produces trusted business metrics. The final output is a Power BI dashboard that helps stakeholders understand content performance, audience engagement, subscription health, and live playback activity using accurate and reliable data.

What real-world process or operation does this project represent?

It represents the data engineering workflow used by OTT and music streaming platforms to process user activity and generate reliable business insights.

What kinds of data are generated?

- Playback session data (plays, watch duration, completion, skips)
- Content metadata (title, genre, language, duration)
- User profile information
- Subscription details
- Live play event data (play, pause, skip, complete)

Why is raw data not enough?

Raw data may contain duplicate sessions, invalid durations, missing content references, inconsistent formats, malformed records, and schema changes. Without cleaning and validation, business metrics such as watch time, completion rate, and churn analysis would be inaccurate.

Who would use the final dashboard or metrics?

- Content Strategy Team to analyze popular content and genres
- Audience Growth Team to study user engagement and viewing behavior
- Subscription Management Team to identify churn risks and customer retention trends
- Product and Data Teams to access trusted, decision-ready metrics for reporting

---

## 2. Engineering Problem

The project must transform multiple raw entertainment-platform datasets—playback sessions, content catalog, users, subscriptions, and live play events—into trusted, analytics-ready outputs. Using Databricks, the team will build a Bronze → Silver → Data Quality → Gold pipeline that preserves raw data, cleans and standardizes records, validates data quality issues such as duplicates, invalid durations, missing references, and schema drift, and produces business metrics for content performance, audience engagement, subscription health, and live play activity. The final Gold tables will be used to power a Power BI dashboard and a streaming simulation for live engagement monitoring.


---

## 3. Users / Stakeholders

| User / Stakeholder | What they need from the data |
|--------------------|------------------------------|
| Content Strategy Lead | Analyze content popularity, watch hours, completion rates, and genre performance to guide content investments. |
| Audience Growth Analyst | Understand user engagement, viewing behavior, repeat sessions, and audience trends across different user segments. |
| Subscription Health Manager | Identify churn-risk users, monitor subscription activity, and evaluate customer retention patterns. |
| Product Data Lead | Access trusted, validated metrics for reporting and ensure dashboards are based on accurate, quality-checked data. |
| Business Management | View high-level KPIs and trends to support strategic decision-making and measure platform performance. |
---

## 4. Scope Inclusions

- Generate synthetic entertainment platform datasets
- Ingest raw data into the Bronze layer
- Clean and standardize data in the Silver layer
- Perform data quality checks and validation
- Create Gold tables with business metrics
- Build a Power BI dashboard using Gold data only
- Simulate live play-event streaming with Structured Streaming
- Maintain a GitHub repository with documentation and project evidence

---

## 5. Scope Exclusions

- No production OTT or music streaming application
- No real customer or copyrighted platform data
- No recommendation system or machine learning models
- No payment gateway or subscription billing system
- No production cloud deployment beyond project requirements
- No Kafka implementation (design concepts only)
- No dashboards built from Bronze or Silver data
- No copied, fabricated, or unexplained AI-generated work

---

## 6. Success Criteria

By the end of 12 weeks, the project is successful if:

- The pipeline can be explained end to end.
- The team can show Bronze, Silver, DQ, Gold, dashboard, and streaming evidence.
- All three students can explain the full project at a high level.
- GitHub contains weekly evidence and final submission files.
