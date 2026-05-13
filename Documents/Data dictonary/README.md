# Dataset Documentation

This repository contains five cleaned datasets related to labour market conditions, wages, and payday lending in Canada, primarily covering 2015–2026. Each section below documents the schema, data dictionary, coverage, and usage notes for one dataset.

## Table of Contents

- [1. Labour Force Characteristics by Age Group & Gender](#1-labour-force-characteristics-by-age-group--gender)
- [2. Employment by Industry](#2-employment-by-industry)
- [3. Employment — Average Hourly & Weekly Earnings (Including Overtime)](#3-employment--average-hourly--weekly-earnings-including-overtime)
- [4. Nova Scotia Minimum Wage (2016–2026)](#4-nova-scotia-minimum-wage-20162026)
- [5. Annual Payday Loan Data](#5-annual-payday-loan-data)

---

## 1. Labour Force Characteristics by Age Group & Gender

**Source file:** `Labour force characteristics by age group,gender StatCanada dictionary.csv.xlsx`

### Overview

Long-form monthly observations of Canadian labour market characteristics, broken down by geography, gender, and age group. Sourced from Statistics Canada.

### Schema

**Rows:** 568,215

| Column | Data Type | Description | Units | Notes |
|---|---|---|---|---|
| `REF_DATE` | Date (YYYY-MM-DD) | Reference date for monthly observation | — | Monthly dates, 2015–2026 |
| `GEO` | String | Geographic area where data is measured | — | Canada, provinces and territories |
| `Labour force characteristics` | String | Labour market characteristic being measured | — | See key domains below |
| `Gender` | String | Gender grouping for the population | — | Total - Gender, Men+, Women+ |
| `Age group` | String | Age range of the population group | — | e.g., 15 to 24 years |
| `Statistics` | String | Type of statistic reported | — | Estimate |
| `Data type` | String | Seasonal adjustment status | — | Unadjusted, Seasonally adjusted, Trend-cycle |
| `VALUE` | Numeric (Float) | Value of the labour force characteristic | Thousands of persons | Positive; decimals allowed |

### Coverage & Granularity

- **Date range:** 2015-01-01 → 2026-03-01 (monthly)
- **Geographies:** 11 (Canada + 10 provinces)
- **VALUE:** min=0.1, max=34,700, mean=706

### Key Domains

**Labour force characteristics** (9 unique values): Employment, Population, Labour force, Unemployment rate, Unemployment, Participation rate, Employment rate, Part-time employment, Full-time employment

**Gender** (3 values): Total - Gender, Men+, Women+

**Age group** (9 values): 15 years and over, 15 to 24 years, 15 to 64 years, 25 to 54 years, 25 years and over, 55 years and over, 15 to 19 years, 20 to 24 years, 55 to 64 years

**Data type** (3 values): Unadjusted (323,595 rows), Seasonally adjusted (243,135), Trend-cycle (1,485)

### Data Quality Notes

- Missing values in `VALUE`: 0.03%
- Duplicate rows: 0

---

## 2. Employment by Industry

**Source file:** `Cleaned Employment by industry and dictionary.csv.xlsx`

### Overview

Monthly employment counts by industry sector and geography across Canada, classified using the North American Industry Classification System (NAICS).

### Schema

**Rows:** 65,205

| Column | Data Type | Description | Units | Notes |
|---|---|---|---|---|
| `REF_DATE` | Date (YYYY-MM-DD) | Reference date for monthly observation | — | Monthly dates (yyyy-mm-dd) |
| `GEO` | String | Geographic area where data is applied | — | Canada, provinces |
| `North American Industry Classification System` | String | Industry or job sector classification | — | e.g., Construction, Manufacturing |
| `Statistics` | String | Type of statistic reported | — | Estimate |
| `Data type` | String | Seasonal adjustment status | — | Seasonally adjusted, Unadjusted, Trend-cycle |
| `VALUE` | Float | Employment count for given industry and date | Thousands of persons | Positive numeric values |

### Coverage & Granularity

- **Date range:** 2015-01-01 → 2026-03-01 (monthly)
- **Geographies:** 11 (Canada + 10 provinces)
- **VALUE:** min=0.2, max=21,400, mean=627

### Key Domains

**NAICS industries** (21 unique values, selected): Total employed all industries, Goods-producing sector, Agriculture, Forestry/fishing/mining/quarrying/oil and gas, Utilities, Construction, Manufacturing, Services-producing sector, Wholesale and retail trade, Transportation and warehousing, Finance/insurance/real estate/rental and leasing, Professional/scientific and technical services, Business/building and other support services

**Data type** (3 values): Seasonally adjusted (31,185 rows), Unadjusted (31,185), Trend-cycle (2,835)

### Data Quality Notes

- Missing values in `VALUE`: 0.04%
- Duplicate rows: 0

---

## 3. Employment — Average Hourly & Weekly Earnings (Including Overtime)

**Source file:** `Cleaned Employment, average hourly and weekly earnings and dictionary (including overtime).xlsx`

### Overview

Monthly estimates of average earnings and employment across Canada, broken down by earnings type (hourly vs. weekly), employee type (all, hourly-paid, salaried), and geography.

### Schema

**Rows:** 20,482

| Column | Data Type | Description | Units | Notes |
|---|---|---|---|---|
| `REF_DATE` | Date (YYYY-MM-DD) | Reference date for monthly observation | — | 2015-01-01 to 2026-01-01 |
| `GEO` | String | Geographic area where data is reported | — | Canada, provinces and territories |
| `Estimate` | String | Description of statistical measure being reported | — | See key domains below |
| `UOM` | String | Unit of measure corresponding to the estimate | — | Dollars, Persons, Hours |
| `VALUE` | Float | Recorded value of the estimate | Depends on UOM | Positive; integers for persons, decimals for wages/hours |

### Coverage & Granularity

- **Date range:** 2015-01-01 → 2026-01-01 (monthly)
- **Geographies:** 14 (Canada + 13 provinces/territories)
- **VALUE:** min=19.6, max=18,300,000, mean=639,000

### Key Domains

**Estimate** (11 unique values): Average weekly earnings including overtime (all/hourly/salaried employees), Average hourly earnings including overtime (hourly/salaried employees), Employment (all/salaried/hourly-paid employees, industrial aggregate), Average weekly hours including overtime for hourly employees, Standard work week excluding overtime for salaried employees

**UOM** (3 values): Dollars (9,310 rows), Persons (7,448), Hours (3,724)

### Data Quality Notes

- Missing values in `VALUE`: 0.04%
- Duplicate rows: 0

---

## 4. Nova Scotia Minimum Wage (2016–2026)

**Source file:** `NS minimum Wage(2016-2026) and dictionary.csv.xlsx`

### Overview

Nova Scotia statutory minimum wage rates by effective date, including experience-level splits where applicable (2016–2019).

### Schema

**Rows:** 18

| Column | Data Type | Description | Units | Notes |
|---|---|---|---|---|
| `Effective Date` | Date (YYYY-MM-DD) | Date the minimum wage rate came into effect | — | 2016-04-01 to 2026-04-01 |
| `Minimum Wage Rate` | Numeric (Float) | Statutory minimum hourly wage rate | CAD per hour | e.g., 10.20, 15.70, 16.75 |
| `Provincial Zone` | String | Geographic wage zone within the province | — | Not Applicable (province-wide rate) |
| `Gender` | String | Category to which the minimum wage applies | — | All |
| `Age` | String | Age group covered by the rate | — | All |
| `Experience Level` | String | Worker experience classification | — | Experienced, Inexperienced, Not Applicable |
| `Effective Date - Year` | Integer | Calendar year of the effective date | Year | 2016–2026 |

### Coverage & Granularity

- **Date range:** 2016-04-01 → 2026-04-01
- **Observation frequency:** Per effective date (not monthly)
- **Minimum wage range:** $10.20 – $16.75 CAD/hour
- **Experience levels:** Experienced (4 rows), Inexperienced (4 rows), Not Applicable (10 rows)

### Data Quality Notes

- No missing values detected
- Duplicate rows: 0

---

## 5. Annual Payday Loan Data

**Source file:** `Annual Payday Loan Data Dictionary.csv`

### Overview

Annual statistics on payday lending activity, including borrower counts, repeat borrowing frequency, loan volumes, average loan amounts, and default rates. Reporting periods follow a fiscal year (typically July 1 – June 30).

### Schema

**Rows:** 17 (data dictionary only — no fact records in this file)

| Column Name | Data Type | Description | Units | Notes |
|---|---|---|---|---|
| `Period Covered` | Text | Reporting fiscal year (July 1 – June 30) | — | e.g., "July 1, YYYY - June 30, YYYY" |
| `No. borrowers granted > 1 loan` | Integer | Unique borrowers granted more than one loan | Borrowers (count) | Non-negative integer |
| `No. of repeat loans granted` | Integer | Repeat loans granted during the period | Loans (count) | Non-negative integer |
| `No. borrowers granted repeat loans` | Integer | Unique borrowers who received repeat loans | Borrowers (count) | Non-negative integer |
| `No. of 1 Time Repeat` | Integer | Borrowers who repeated exactly 1 time | Borrowers (count) | Repeat-frequency distribution |
| `No. of 2 Time Repeat` | Integer | Borrowers who repeated exactly 2 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 3 Time Repeat` | Integer | Borrowers who repeated exactly 3 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 4 Time Repeat` | Integer | Borrowers who repeated exactly 4 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 5 Time Repeat` | Integer | Borrowers who repeated exactly 5 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 6 Time Repeat` | Integer | Borrowers who repeated exactly 6 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 7 Time Repeat` | Integer | Borrowers who repeated exactly 7 times | Borrowers (count) | Repeat-frequency distribution |
| `No. of 8+ Time Repeat` | Integer | Borrowers who repeated 8 or more times | Borrowers (count) | Upper tail of frequency distribution |
| `Total Loans Granted` | Integer | Total payday loans granted during the period | Loans (count) | Non-negative integer |
| `Average Amount Loan Granted` | Numeric (Float) | Average dollar value of a granted loan | Dollars (CAD) | 2 decimal places |
| `Estimated Total Value of Loans Granted` | Numeric (Float) | Estimated total value of all loans granted | Dollars (CAD) | ≈ Total Loans × Average Amount |
| `Default Rate` | Numeric (Float) | Loan default rate for the period | Percent (%) | e.g., 7.79 means 7.79% |
| `Average Amount Loan Defaulted` | Numeric (Float) | Average dollar amount of defaulted loans | Dollars (CAD) | 2 decimal places |

### Notes & Assumptions

- `Period Covered` follows a fiscal year window (July 1 – June 30).
- Repeat-frequency columns (`No. of 1 Time Repeat` … `No. of 8+ Time Repeat`) together form a distribution that sums to `No. borrowers granted repeat loans`.
- `Default Rate` is stored as a plain percentage value (e.g., `7.79` = 7.79%).

---

## General Usage Notes

All datasets use a **long (tidy) format**: one row per observation. For time-series analysis, ensure date columns are typed correctly before loading.

### Importing into Power BI

1. **Home → Get data → Excel / CSV** and select the relevant file.
2. Load the data sheet as your fact table.
3. Load the dictionary sheet (where available) as a reference table for documentation.
4. Set date columns to the **Date** type and relate them to a shared date dimension if building a multi-table model.

### Suggested Analysis Ideas

- Trend lines of employment and earnings over time (monthly).
- Compare labour force characteristics across provinces and territories.
- Overlay Nova Scotia minimum wage changes against average hourly earnings.
- Examine repeat payday borrowing patterns and default rates over fiscal years.
- Cross-reference employment by industry with labour force participation by age/gender.
