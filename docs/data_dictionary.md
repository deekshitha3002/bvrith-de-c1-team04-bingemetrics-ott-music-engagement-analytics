# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name            | Grain                        |                           Purpose | Approx. Rows | Notes             |
| -------------------- | ---------------------------- | --------------------------------: | -----------: | ----------------- |
| sessions.parquet     | One row per playback session | Stores viewing/listening sessions |     ~250,000 | Main fact table   |
| users.csv            | One row per user             |           Stores user information |      ~40,000 | Dimension table   |
| subscriptions.csv    | One row per subscription     |       Stores subscription details |      ~55,000 | Linked with users |
| content_catalog.json | One row per content item     |     Stores movie/song information |       ~5,000 | Dimension table   |
| play_event.json      | One row per event            |              Streaming simulation |       Varies | Used in Week 10   |

---

## 2. Raw File Schema: sessions.parquet

| Field Name      | Data Type | Required? | Example             | Description        |
| --------------- | --------- | --------- | ------------------- | ------------------ |
| session_id      | String    | Yes       | SES000001           | Unique session ID  |
| user_id         | String    | Yes       | USR00125            | User identifier    |
| content_id      | String    | Yes       | CNT00045            | Content identifier |
| device          | String    | Yes       | Mobile              | Device used        |
| start_time      | Timestamp | Yes       | 2026-07-01 09:30:00 | Session start      |
| end_time        | Timestamp | Yes       | 2026-07-01 10:05:00 | Session end        |
| watch_seconds   | Integer   | Yes       | 2100                | Total watch time   |
| completion_rate | Float     | Yes       | 92.5                | Percentage watched |
| skip_flag       | Boolean   | No        | False               | Whether skipped    |

---

## 3. Raw File Schema: users.csv

| Field Name     | Data Type | Required? | Example    | Description       |
| -------------- | --------- | --------- | ---------- | ----------------- |
| user_id        | String    | Yes       | USR00125   | Unique user ID    |
| age_band       | String    | Yes       | 18-24      | Age group         |
| region         | String    | Yes       | South      | User region       |
| signup_date    | Date      | Yes       | 2025-04-12 | Registration date |
| primary_device | String    | Yes       | Smart TV   | Preferred device  |

---

## 4. Reference File Schema (content_catalog.json)
| Field Name       | Data Type | Required? | Example        | Description      |
| ---------------- | --------- | --------- | -------------- | ---------------- |
| content_id       | String    | Yes       | CNT00045       | Content ID       |
| title            | String    | Yes       | The Silent Sky | Movie/Song title |
| genre            | String    | Yes       | Drama          | Content genre    |
| language         | String    | Yes       | English        | Language         |
| duration_minutes | Integer   | Yes       | 125            | Content duration |
| release_year     | Integer   | Yes       | 2023           | Release year     |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_sessions
```
| Silver Field        | Data Type | Source Mapping           | Business Meaning      |
| ------------------- | --------- | ------------------------ | --------------------- |
| session_id          | String    | sessions.session_id      | Unique session        |
| user_id             | String    | sessions.user_id         | User identifier       |
| content_id          | String    | sessions.content_id      | Content identifier    |
| watch_seconds       | Integer   | sessions.watch_seconds   | Watch duration        |
| completion_rate     | Float     | sessions.completion_rate | Completion percentage |
| subscription_status | String    | subscriptions.status     | Active/Cancelled      |
| genre               | String    | content_catalog.genre    | Genre of content      |
| region              | String    | users.region             | User location         |

---

## 6. Streaming Event Schema
| Field Name      | Data Type | Required? | Example             | Description                              |
| --------------- | --------- | --------- | ------------------- | ---------------------------------------- |
| event_id        | String    | Yes       | EVT000001           | Unique event ID                          |
| event_timestamp | Timestamp | Yes       | 2026-07-03T10:15:00 | Event time                               |
| session_id      | String    | Yes       | SES000001           | Session identifier                       |
| user_id         | String    | Yes       | USR00125            | User identifier                          |
| content_id      | String    | Yes       | CNT00045            | Content identifier                       |
| event_type      | String    | Yes       | play                | Event type (play, pause, skip, complete) |
| watch_seconds   | Integer   | No        | 120                 | Seconds watched                          |
| device          | String    | Yes       | Mobile              | Device used                              |
