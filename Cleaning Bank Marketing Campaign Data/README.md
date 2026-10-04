# Bank Marketing Campaign Data Cleaning

A data preparation and ETL project based on the DataCamp project: [Cleaning Bank Marketing Campaign Data](https://app.datacamp.com/learn/projects/1613). This project processes, cleans, and restructures raw bank marketing campaign data (`bank_marketing.csv`) into three separate, schema-aligned CSV tables designed for relational database storage (e.g., PostgreSQL).

---

## 📌 Project Overview

The goal is to prepare raw marketing campaign data for database ingestion by handling data types, cleaning categorical values, creating standardized datetime fields, and splitting data into logical relational entities:
- **`client.csv`**: Demographic and loan status information.
- **`campaign.csv`**: Contact details and marketing outreach performance metrics.
- **`economics.csv`**: Key macroeconomic indicators during the outreach period.

---

## 🛠️ Data Transformation & Cleaning Steps

1. **Client Table (`client.csv`)**:
   - Replaced `.` with `_` in `job` and `education` fields.
   - Replaced `'unknown'` values in `education` with `NaN`.
   - Converted `credit_default` and `mortgage` to boolean flags (`True` for `'yes'`, `False` otherwise).

2. **Campaign Table (`campaign.csv`)**:
   - Converted `previous_outcome` (`'success'`) and `campaign_outcome` (`'yes'`) to boolean flags.
   - Synthesized `last_contact_date` (`YYYY-MM-DD`) from `day`, `month`, and the fixed year `2022`.

3. **Economics Table (`economics.csv`)**:
   - Extracted `client_id`, `cons_price_idx`, and `euribor_three_months`.
