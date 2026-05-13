# Cleaned Employment by industry and dictionary.csv

Dataset extracted from `Cleaned Employment by industry and dictionary.csv.xlsx`.

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

**Rows:** 65,205

**Columns:**
- `REF_DATE` (datetime64[ns]) — e.g., `2015-01-01 00:00:00`
- `GEO` (object) — e.g., `Canada`
- `North American Industry Classification System` (object) — e.g., `Total employed, all industries`
- `Statistics` (object) — e.g., `Estimate`
- `Data type` (object) — e.g., `Seasonally adjusted`
- `VALUE` (float64) — e.g., `17813.1`

## Data dictionary

| Column Name | Data Type | Description | Units | Allowed Value/Notes |
| --- | --- | --- | --- | --- |
| REF_DATE | Date | Reference date of the employment observation |  | Monthly Dates (yyyy-mm-dd) |
| GEO | String | Geographic area where the data is applied |  | Canada |
| North American Industry Classification System | String | Industry or Job sector classification |  | Construction, Manufacturing, Service Industry, |
| Statistics | String | Statistics Reported |  | Estimated |
| Data Type | String | Seasonal adjustment status |  | Seasonal Adjustments |
| VALUE | Float | Employment count for given industry and date | Thousands of people | Positive Numeric Values |

## Coverage & granularity

- **Date range:** 2015-01-01 → 2026-03-01 (monthly observations)
- **Geography field:** `GEO` (unique values: 11)
- **VALUE summary:** min=0.2, max=2.14e+04, mean=627

## Key domains (categorical values)

### GEO

- Unique values: **11**
- Top values:
  - Canada — 8,505
  - Newfoundland and Labrador — 5,670
  - Prince Edward Island — 5,670
  - Nova Scotia — 5,670
  - New Brunswick — 5,670
  - Quebec — 5,670
  - Ontario — 5,670
  - Manitoba — 5,670
  - Saskatchewan — 5,670
  - Alberta — 5,670
  - British Columbia — 5,670

### North American Industry Classification System

- Unique values: **21**
- Top values:
  - Total employed, all industries — 3,105
  - Goods-producing sector — 3,105
  - Agriculture — 3,105
  - Forestry, fishing, mining, quarrying, oil and gas — 3,105
  - Utilities — 3,105
  - Construction — 3,105
  - Manufacturing — 3,105
  - Services-producing sector — 3,105
  - Wholesale and retail trade — 3,105
  - Wholesale trade — 3,105
  - Retail trade — 3,105
  - Transportation and warehousing — 3,105
  - Finance, insurance, real estate, rental and leasing — 3,105
  - Professional, scientific and technical services — 3,105
  - Business, building and other support services — 3,105

### Statistics

- Unique values: **1**
- Top values:
  - Estimate — 65,205

### Data type

- Unique values: **3**
- Top values:
  - Seasonally adjusted — 31,185
  - Unadjusted — 31,185
  - Trend-cycle — 2,835

## Data quality notes

**Missing values (percent of rows):**
- `VALUE`: 0.04%

**Duplicate rows:** 0

**Notes:**
- Most series are labeled **Seasonally adjusted** in the `Data type` column.

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