# Annual Payday Loan Data Dictionary

Data dictionary extracted from `Annual Payday Loan Data Dictionary.csv`.

## Table of contents

- [Overview](#overview)
- [File contents](#file-contents)
- [Data dictionary](#data-dictionary)
- [Notes & assumptions](#notes--assumptions)
- [Quick start](#quick-start)

## Overview

This file documents the fields used in the annual payday loan dataset, including definitions, units, and validation notes.

## File contents

- **Type:** CSV (data dictionary only; no fact records).
- **Rows:** 17
- **Columns:** `Column Name`, `Data Type`, `Description`, `Units`, `Allowed Value/Notes`

## Data dictionary

| Column Name | Data Type | Description | Units | Allowed Value/Notes |
| --- | --- | --- | --- | --- |
| Period Covered | Text | Reporting period covered by the annual payday loan statistics (fiscal year, typically July 1 to June 30). |  | Text pattern like "July 1, YYYY - June 30, YYYY"; one row per annual period. |
| No. borrowers granted > 1 loan | Integer | Number of unique borrowers who were granted more than one payday loan during the period. | Borrowers (count) | Non-negative integer. |
| No. of repeat loans granted | Integer | Number of repeat payday loans granted during the period (loans issued to borrowers who took more than one loan). | Loans (count) | Non-negative integer. |
| No. borrowers granted repeat loans | Integer | Number of unique borrowers who were granted repeat loans during the period. | Borrowers (count) | Non-negative integer; distribution across repeat-frequency columns may sum to this value. |
| No. of 1 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 1 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 2 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 2 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 3 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 3 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 4 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 4 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 5 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 5 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 6 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 6 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 7 Time Repeat | Integer | Number of borrowers who repeated borrowing exactly 7 time(s) during the period. | Borrowers (count) | Non-negative integer; repeat-frequency distribution. |
| No. of 8+ Time Repeat | Integer | Number of borrowers who repeated borrowing eight or more times during the period. | Borrowers (count) | Non-negative integer; grouped upper tail of repeat-frequency distribution. |
| Total Loans Granted | Integer | Total number of payday loans granted during the period (all borrowers). | Loans (count) | Non-negative integer. |
| Average Amount Loan Granted | Numeric (float) | Average dollar amount of a loan granted during the period. | Dollars (CAD) | Typically positive; displayed to 2 decimal places. |
| Estimated Total Value of Loans Granted | Numeric (float) | Estimated total dollar value of all loans granted during the period. | Dollars (CAD) | Typically equals Total Loans Granted x Average Amount Loan Granted (approx.). |
| Default Rate | Numeric (float) | Default rate for loans in the period. | Percent (%) | Expressed as a percentage (e.g., 7.79 means 7.79%). |
| Average Amount Loan Defaulted | Numeric (float) | Average dollar amount of loans that defaulted during the period. | Dollars (CAD) | Displayed to 2 decimal places. |

## Notes & assumptions

- `Period Covered` is an annual fiscal reporting window (typically July 1 to June 30).
- Repeat-frequency fields (`No. of 1 Time Repeat` … `No. of 8+ Time Repeat`) describe the distribution of repeat borrowing frequency within a period.
- `Default Rate` is stored as a percentage value (e.g., `7.79` means `7.79%`).

## Quick start

### Import into Power BI
1. Load your annual payday loan fact table (if separate) as your primary dataset.
2. Load this CSV as a **reference table** to surface field definitions inside your model/documentation.

### Suggested model usage
- Use the dictionary to validate data types and units during ETL.
- Use `Period Covered` to map each record to a date dimension (start date / end date) if you need time intelligence.