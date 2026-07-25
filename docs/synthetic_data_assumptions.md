# Synthetic Data Assumptions

**Week:** 2  
**Purpose:** Document how educational data is created.

---

## 1. Synthetic Data Boundary

This project uses synthetic educational data only. It must not be presented as real company, customer, citizen, player, patient, government, or platform data.

---

## 2. Domain Assumptions

| Area              | Assumption                                                                  |
| ----------------- | --------------------------------------------------------------------------- |
| Geography / Scope | Fictional global OTT and music streaming platform users                     |
| Time Period       | January 2025 – December 2025                                                |
| Source Systems    | Playback sessions, user profiles, content catalog, and subscription records |
| Event Types       | Play, Pause, Skip, Complete                                                 |
| Reference Data    | Genres, content types, languages, subscription plans, devices               |

---

## 3. Data Volume Assumptions

| File                   | Approximate Rows | Reason                                       |
| ---------------------- | ---------------: | -------------------------------------------- |
| `sessions.parquet`     |         ~250,000 | Large playback session dataset for analytics |
| `users.csv`            |          ~40,000 | User profile information                     |
| `subscriptions.csv`    |          ~55,000 | Subscription details and plan history        |
| `content_catalog.json` |           ~5,000 | Movies, TV shows, songs, and podcasts        |
| `play_event.json`      |           Varies | Streaming events used in Week 10 simulation  |

---

## 4. Controlled Data Quality Issues
| Issue Type                | Approx. Share | Why Include It                     |
| ------------------------- | ------------: | ---------------------------------- |
| Duplicate Session IDs     |     0.2%–0.5% | Test duplicate detection           |
| Missing Values            |         1%–3% | Test completeness checks           |
| Invalid Content IDs       |       0.5%–1% | Test referential integrity         |
| Impossible Watch Duration |     0.1%–0.5% | Test validation rules              |
| Timestamp Inconsistencies |     0.1%–0.3% | Test chronological validation      |
| Schema Drift (Streaming)  |  Small sample | Test streaming pipeline robustness |

---

## 5. Manual Verification

Before using generated data, the team must check:

- Row counts are reasonable.
- Key fields exist.
- Dates and numeric values look realistic.
- Controlled defects exist but do not dominate the dataset.
- Source files are different enough to require real standardization.
