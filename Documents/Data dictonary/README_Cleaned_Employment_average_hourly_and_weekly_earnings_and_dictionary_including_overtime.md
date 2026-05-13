# Cleaned Employment, average hourly and weekly earnings and dictionary  (including overtime),

Dataset extracted from `Cleaned Employment, average hourly and weekly earnings and dictionary  (including overtime),.xlsx`.

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

**Rows:** 20,482

**Columns:**
- `REF_DATE` (datetime64[ns]) — e.g., `2015-01-01 00:00:00`
- `GEO` (object) — e.g., `Canada`
- `Estimate` (object) — e.g., `Average weekly earnings including overtime for all employees`
- `UOM` (object) — e.g., `Dollars`
- `VALUE` (float64) — e.g., `948.5`

## Data dictionary

| Column Name | Data Type | Description | Units | Allowed Values/Notes |
| --- | --- | --- | --- | --- |
| REF_DATE | Date | Referencing monthly data for observation |  | YYYY-MM-DD, dates ranging from 2015-01-01 to 2026-01-01 |
| GEO | String | Geographic area where data is reported |  | Canada ( inclusive of provinces and territories) |
| Estimate | String | Description of statistical measure being reported |  | Average of weekly earnings- including average hourly earnings, overtime and employment |
| UOM (unit of measure) | String | Unit of measure that corresponds to the estimate |  | Dollars, Persons , Hours |
| Value | Numeric | Recored value estimate | Depends on the UOM (hours, wages, employees | Positive numbers, intergers for persons/employees, decimals for hours/wages in dollars |

## Coverage & granularity

- **Date range:** 2015-01-01 → 2026-01-01 (monthly observations)
- **Geography field:** `GEO` (unique values: 14)
- **VALUE summary:** min=19.6, max=1.83e+07, mean=6.39e+05

## Key domains (categorical values)

### GEO

- Unique values: **14**
- Top values:
  - Canada — 1,463
  - Newfoundland and Labrador — 1,463
  - Prince Edward Island — 1,463
  - Nova Scotia — 1,463
  - New Brunswick — 1,463
  - Quebec — 1,463
  - Ontario — 1,463
  - Manitoba — 1,463
  - Saskatchewan — 1,463
  - Alberta — 1,463
  - British Columbia — 1,463
  - Yukon — 1,463
  - Northwest Territories — 1,463
  - Nunavut — 1,463

### Estimate

- Unique values: **11**
- Top values:
  - Average weekly earnings including overtime for all employees — 1,862
  - Average weekly earnings including overtime for hourly employees — 1,862
  - Average weekly earnings including overtime for salaried employees — 1,862
  - Average hourly earnings including overtime for hourly employees — 1,862
  - Average hourly earnings including overtime for salaried employees — 1,862
  - Employment for all employees, industrial aggregate including unclassified — 1,862
  - Employment for salaried employees — 1,862
  - Employment for hourly paid employees — 1,862
  - Average weekly hours including overtime for hourly employees — 1,862
  - Standard work week excluding overtime for salaried employees (exclude overtime) — 1,862
  - Employment for all employees — 1,862

### UOM

- Unique values: **3**
- Top values:
  - Dollars — 9,310
  - Persons — 7,448
  - Hours — 3,724

## Data quality notes

**Missing values (percent of rows):**
- `VALUE`: 0.04%

**Duplicate rows:** 0

**Notes:**
- Units are provided in the `UOM` column (e.g., Dollars).

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