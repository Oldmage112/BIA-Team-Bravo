# NS minimum Wage(2016-2026) and dictionary.csv

Dataset extracted from `NS minimum Wage(2016-2026) and dictionary.csv.xlsx`.

## Table of contents

- [Overview](#overview)
- [File contents](#file-contents)
- [Schema](#schema)
- [Data dictionary](#data-dictionary)
- [Coverage & granularity](#coverage--granularity)
- [Key domains (categorical values)](#key-domains-categorical-values)
- [Data quality notes](#data-quality-notes)
- [Quick start](#quick-start)

## Overview

Nova Scotia statutory minimum wage rates by effective date, including experience-level splits where applicable.

## File contents

- **Data sheet:** `NS minimum Wage(2016-2026)`
- **Dictionary sheet:** `Dictionary`

## Schema

**Rows:** 18

**Columns:**
- `Effective Date` (datetime64[ns]) — e.g., `2026-04-01 00:00:00`
- `Minimum Wage Rate` (float64) — e.g., `16.75`
- `Provincial Zone` (object) — e.g., `Not Applicable`
- `Gender` (object) — e.g., `All`
- `Age` (object) — e.g., `All`
- `Experience Level` (object) — e.g., `Not Applicable`
- `Effective Date - Year` (int64) — e.g., `2026`

## Data dictionary

| Column Name | Data Type | Description | Units | Allowed Values |
| --- | --- | --- | --- | --- |
| Effective Date | Date | Dates on when the minimum wage rate came into effect in Nova Scotia |  | Valid dates from 2016-04-01 to 2026-04-01 |
| Minimum Wage Rate | Numeric (Float) | Statutory minimum hourly wage rate | CAD per hour | Positive numeric values (e.g, 10.20, 15.70,16.75) |
| Provincial Zone | String | Geographic wage zone within the province |  | Not Applicable (province -wide rate) |
| Gender | String | Category to which the minimum wage applies |  | All |
| Age | String | Age group covered by the minimum wage rate |  | All |
| Experience Level | String | Worker experience classification used for wage differentiation in some years |  | Experienced, Inexperienced, Not applicable |
| Effective Date-Year | Integer | Calendar year taken from the effective date | Year | 2016-2026 |

## Coverage & granularity

- **Date range:** 2016-04-01 → 2026-04-01
- **Observation frequency:** changes occur on effective dates (not necessarily every month).
- **Minimum wage (CAD/hour):** min=10.20, max=16.75
- **Experience levels:** Experienced, Inexperienced, Not Applicable

## Key domains (categorical values)

### Provincial Zone

- Unique values: **1**
- Top values:
  - Not Applicable — 18

### Gender

- Unique values: **1**
- Top values:
  - All — 18

### Age

- Unique values: **1**
- Top values:
  - All — 18

### Experience Level

- Unique values: **3**
- Top values:
  - Not Applicable — 10
  - Experienced — 4
  - Inexperienced — 4

## Data quality notes

**Missing values (percent of rows):**
- No missing values detected in the data sheet.

**Duplicate rows:** 0

## Quick start

### Import into Power BI
1. **Home → Get data → Excel** and select this workbook.
2. Load the data sheet as a fact table (minimum wage rates).
3. Optionally load the Dictionary sheet for documentation.
4. Set the effective date column to **Date** type and relate it to your date dimension if you are modeling time.

### Example analysis ideas
- Plot minimum wage over time (step chart).
- Compare experienced vs inexperienced rates where available (2016–2019).
- Compute absolute and % changes between effective dates.