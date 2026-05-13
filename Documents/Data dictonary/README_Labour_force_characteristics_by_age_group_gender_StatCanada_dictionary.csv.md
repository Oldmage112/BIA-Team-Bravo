# Labour force characteristics by age group,gender StatCanada dictionary.csv

Dataset extracted from `Labour force characteristics by age group,gender StatCanada dictionary.csv.xlsx`.

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

This dataset is provided as an Excel workbook with a cleaned fact table and a companion data dictionary sheet.

## File contents

- **Data sheet:** long-form records (one row per observation).
- **Dictionary sheet:** definitions for each column, including units and allowed values (when provided).

## Schema

**Rows:** 568,215

**Columns:**
- `REF_DATE` (datetime64[ns]) — e.g., `2015-01-01 00:00:00`
- `GEO` (object) — e.g., `Canada`
- `Labour force characteristics` (object) — e.g., `Population`
- `Gender` (object) — e.g., `Total - Gender`
- `Age group` (object) — e.g., `15 to 24 years`
- `Statistics` (object) — e.g., `Estimate`
- `Data type` (object) — e.g., `Unadjusted`
- `VALUE` (float64) — e.g., `4397.6`

## Data dictionary

| ColumnName | Data Type | Description | Units | Allowed Values/Notes |
| --- | --- | --- | --- | --- |
| REF_Date | Date (YYYY-MM-DD) | Reference date for monthly observation |  | Monthly dates from 2015- 2026 |
| GEO | String | Geographic area where data is measured |  | Canada ( provinces and territories) |
| Labour Force characteristics | String | Labour market charcteristics being measured |  | Labour force |
| Gender | String | Gender grouping for the population |  | Total - Gender |
| Age Group | String | Age range of the population group |  | From 15 to 24 years |
| Statistics | String | Statistics Reported |  | Estimated |
| Data Type | String | Seasonal adjustment status |  | Unadjusted |
| Value | Numeric (Float) | Value of the labour force characteristics | Thousands of persons | Positivr numeric values, decimals allowed |

## Coverage & granularity

- **Date range:** 2015-01-01 → 2026-03-01 (monthly observations)
- **Geography field:** `GEO` (unique values: 11)
- **VALUE summary:** min=0.1, max=3.47e+04, mean=706

## Key domains (categorical values)

### GEO

- Unique values: **11**
- Top values:
  - Canada — 61,965
  - Newfoundland and Labrador — 50,625
  - Prince Edward Island — 50,625
  - Nova Scotia — 50,625
  - New Brunswick — 50,625
  - Quebec — 50,625
  - Ontario — 50,625
  - Manitoba — 50,625
  - Saskatchewan — 50,625
  - Alberta — 50,625
  - British Columbia — 50,625

### Labour force characteristics

- Unique values: **9**
- Top values:
  - Employment — 65,475
  - Population — 63,990
  - Labour force — 63,990
  - Unemployment rate — 63,990
  - Unemployment — 63,990
  - Participation rate — 63,990
  - Employment rate — 63,990
  - Part-time employment — 59,400
  - Full-time employment — 59,400

### Gender

- Unique values: **3**
- Top values:
  - Total - Gender — 192,375
  - Men+ — 187,920
  - Women+ — 187,920

### Age group

- Unique values: **9**
- Top values:
  - 15 years and over — 81,675
  - 15 to 24 years — 80,190
  - 15 to 64 years — 80,190
  - 25 to 54 years — 80,190
  - 25 years and over — 80,190
  - 55 years and over — 74,250
  - 15 to 19 years — 42,930
  - 20 to 24 years — 42,930
  - 55 to 64 years — 5,670

### Statistics

- Unique values: **1**
- Top values:
  - Estimate — 568,215

### Data type

- Unique values: **3**
- Top values:
  - Unadjusted — 323,595
  - Seasonally adjusted — 243,135
  - Trend-cycle — 1,485

## Data quality notes

**Missing values (percent of rows):**
- `VALUE`: 0.03%

**Duplicate rows:** 0

**Notes:**
- Values are marked as **Unadjusted** in the `Data type` column in this file.

## Quick start

### Import into Power BI
1. **Home → Get data → Excel** and select this workbook.
2. Load the **data sheet** as your fact table.
3. Optionally load the **Dictionary** sheet as a reference table for documentation.
4. Ensure the date field is typed as **Date** and build relationships to your date dimension if applicable.

### Example analysis ideas
- Trend lines over time (monthly).
- Compare geographies (province vs Canada).
- Compare categories (industry, age group, gender, characteristic).