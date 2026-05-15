# DAX Measure Dictionary

This document provides a comprehensive reference for all DAX measures used in the Power BI data model. It includes each measure's source table, DAX calculation, and a plain-language explanation of what it computes.

## Table of contents

- [Conventions](#conventions)
- [Measures](#measures)
  - [Dim Effective Date](#dim-effective-date)
  - [Dim MinimumWage Rate](#dim-minimumwage-rate)
  - [Fact Annual Payday Loan](#fact-annual-payday-loan)
  - [Fact Employment average hourly and weekly earnings](#fact-employment-average-hourly-and-weekly-earnings)
  - [Fact Employment by industry](#fact-employment-by-industry)
  - [Fact LabourForce characteristics by age group gender](#fact-labourforce-characteristics-by-age-group-gender)
  - [Fact NS minimum Wage](#fact-ns-minimum-wage)
- [Common calculation patterns](#common-calculation-patterns)

## Conventions

- Each measure is documented with its source table, DAX calculation, and a plain-language explanation.
- DAX is shown in fenced code blocks using the `DAX` language hint for readability.
- Measure names are reproduced exactly as they appear in the model.

## Measures

## Dim Effective Date

**Measures in this table**
- [Count of Effective Date](#count-of-effective-date)

### Count of Effective Date

**Source table:** `Dim Effective Date`

**Explanation:** Counts the number of non-blank effective dates in the Dim Effective Date table.

**Calculation:**

```DAX
COUNTA('Dim Effective Date'[Effective Date])
```

## Dim MinimumWage Rate

**Measures in this table**
- [Average of Minimum Wage Rate](#average-of-minimum-wage-rate)
- [Count of Minimum Wage Rate](#count-of-minimum-wage-rate)
- [Sum of Minimum Wage Rate](#sum-of-minimum-wage-rate)

### Average of Minimum Wage Rate

**Source table:** `Dim MinimumWage Rate`

**Explanation:** Calculates the average minimum wage rate across all records in the Dim MinimumWage Rate table.

**Calculation:**

```DAX
AVERAGE('Dim MinimumWage Rate'[Minimum Wage Rate])
```

### Count of Minimum Wage Rate

**Source table:** `Dim MinimumWage Rate`

**Explanation:** Counts the number of non-blank minimum wage rate records in the Dim MinimumWage Rate table.

**Calculation:**

```DAX
COUNTA('Dim MinimumWage Rate'[Minimum Wage Rate])
```

### Sum of Minimum Wage Rate

**Source table:** `Dim MinimumWage Rate`

**Explanation:** Returns the sum of all minimum wage rates across records in the Dim MinimumWage Rate table.

**Calculation:**

```DAX
SUM('Dim MinimumWage Rate'[Minimum Wage Rate])
```

## Fact Annual Payday Loan

**Measures in this table**
- [2 Time Repeat Retention](#2-time-repeat-retention)
- [2 Time Repeat Retention YoY % Change](#2-time-repeat-retention-yoy-change)
- [3 Time Repeat Retention](#3-time-repeat-retention)
- [3 Time Repeat Retention YoY % Change](#3-time-repeat-retention-yoy-change)
- [4 Time Repeat Retention](#4-time-repeat-retention)
- [4 Time Repeat Retention YoY % Change](#4-time-repeat-retention-yoy-change)
- [5 Time Repeat Retention](#5-time-repeat-retention)
- [5 Time Repeat Retention YoY % Change](#5-time-repeat-retention-yoy-change)
- [6 Time Repeat Retention](#6-time-repeat-retention)
- [6 Time Repeat Retention YoY % Change](#6-time-repeat-retention-yoy-change)
- [7 Time Repeat Retention](#7-time-repeat-retention)
- [7 Time Repeat Retention YoY % Change](#7-time-repeat-retention-yoy-change)
- [8 Time Repeat Retention](#8-time-repeat-retention)
- [8 Time Repeat Retention YoY % Change](#8-time-repeat-retention-yoy-change)
- [Average Loan Defaulted](#average-loan-defaulted)
- [Average Loan Defaulted YoY % Change](#average-loan-defaulted-yoy-change)
- [Average Loan Granted](#average-loan-granted)
- [Average Loan Granted / Defaulted](#average-loan-granted-defaulted)
- [Average Loan Granted / Defaulted YoY % Change](#average-loan-granted-defaulted-yoy-change)
- [Average Loan Granted YoY % Change](#average-loan-granted-yoy-change)
- [Default Rates](#default-rates)
- [Default Rates YoY % Change](#default-rates-yoy-change)
- [NS Population](#ns-population)
- [Number of Repeat Borrowers](#number-of-repeat-borrowers)
- [Number of Repeat Borrowers YoY % Change](#number-of-repeat-borrowers-yoy-change)
- [Number of Repeat Loans Granted](#number-of-repeat-loans-granted)
- [Number of Repeat Loans Granted YoY % Change](#number-of-repeat-loans-granted-yoy-change)
- [People 1 Time Repeat](#people-1-time-repeat)
- [People 2 Time Repeat](#people-2-time-repeat)
- [People 3 Time Repeat](#people-3-time-repeat)
- [People 4 Time Repeat](#people-4-time-repeat)
- [People 5 Time Repeat](#people-5-time-repeat)
- [People 6 Time Repeat](#people-6-time-repeat)
- [People 7 Time Repeat](#people-7-time-repeat)
- [People 8+ Time Repeat](#people-8-time-repeat)
- [People Granted > 1 Loan](#people-granted-1-loan)
- [Percent People 1 Time Repeat](#percent-people-1-time-repeat)
- [Percent People 1 Time Repeat YoY % Change](#percent-people-1-time-repeat-yoy-change)
- [Percent People 2 Time Repeat](#percent-people-2-time-repeat)
- [Percent People 2 Time Repeat YoY % Change](#percent-people-2-time-repeat-yoy-change)
- [Percent People 3 Time Repeat](#percent-people-3-time-repeat)
- [Percent People 3 Time Repeat YoY % Change](#percent-people-3-time-repeat-yoy-change)
- [Percent People 4 Time Repeat](#percent-people-4-time-repeat)
- [Percent People 4 Time Repeat YoY % Change](#percent-people-4-time-repeat-yoy-change)
- [Percent People 5 Time Repeat](#percent-people-5-time-repeat)
- [Percent People 5 Time Repeat YoY % Change](#percent-people-5-time-repeat-yoy-change)
- [Percent People 6 Time Repeat](#percent-people-6-time-repeat)
- [Percent People 6 Time Repeat YoY % Change](#percent-people-6-time-repeat-yoy-change)
- [Percent People 7 Time Repeat](#percent-people-7-time-repeat)
- [Percent People 7 Time Repeat YoY % Change](#percent-people-7-time-repeat-yoy-change)
- [Percent People 8+ Time Repeat](#percent-people-8-time-repeat)
- [Percent People 8+ Time Repeat YoY % Change](#percent-people-8-time-repeat-yoy-change)
- [Percent Repeat Borrowers](#percent-repeat-borrowers)
- [Percent Repeat Borrowers YoY % Change](#percent-repeat-borrowers-yoy-change)
- [Repeat Loans Granted](#repeat-loans-granted)
- [Repeat Loans Granted YoY % Change](#repeat-loans-granted-yoy-change)
- [Total Number of Loans](#total-number-of-loans)
- [Total Number of Loans YoY % Change](#total-number-of-loans-yoy-change)
- [Total Repeat Loans / Total Loans](#total-repeat-loans-total-loans)
- [Total Repeat Loans / Total Loans YoY % Change](#total-repeat-loans-total-loans-yoy-change)
- [Total Value of Loans Granted](#total-value-of-loans-granted)
- [Total Value of Loans YoY % Change](#total-value-of-loans-yoy-change)

### 2 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between borrowers who took a loan once and those who took it a second time, calculated as the difference divided by the 1-time repeat count.

**Calculation:**

```DAX
Divide([People 1 Time Repeat] - [People 2 Time Repeat],[People 1 Time Repeat])
```

### 2 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [2 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [2 Time Repeat Retention] -
CALCULATE ( [2 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [2 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 3 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 2-time and 3-time repeat borrowers, calculated as the difference divided by the 2-time repeat count.

**Calculation:**

```DAX
Divide([People 2 Time Repeat] - [People 3 Time Repeat],[People 2 Time Repeat])
```

### 3 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [3 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [3 Time Repeat Retention] -
CALCULATE ( [3 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [3 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 4 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 3-time and 4-time repeat borrowers.

**Calculation:**

```DAX
Divide([People 3 Time Repeat] - [People 4 Time Repeat],[People 3 Time Repeat])
```

### 4 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [4 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [4 Time Repeat Retention] -
CALCULATE ( [4 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [4 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 5 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 4-time and 5-time repeat borrowers.

**Calculation:**

```DAX
Divide([People 4 Time Repeat] - [People 5 Time Repeat],[People 4 Time Repeat])
```

### 5 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [5 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [5 Time Repeat Retention] -
CALCULATE ( [5 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [5 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 6 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 5-time and 6-time repeat borrowers.

**Calculation:**

```DAX
Divide([People 5 Time Repeat] - [People 6 Time Repeat],[People 5 Time Repeat])
```

### 6 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [6 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [6 Time Repeat Retention] -
CALCULATE ( [6 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [6 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 7 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 6-time and 7-time repeat borrowers.

**Calculation:**

```DAX
Divide([People 6 Time Repeat] - [People 7 Time Repeat],[People 6 Time Repeat])
```

### 7 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [7 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [7 Time Repeat Retention] -
CALCULATE ( [7 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [7 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### 8 Time Repeat Retention

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Measures the retention rate between 7-time and 8+-time repeat borrowers.

**Calculation:**

```DAX
Divide([People 7 Time Repeat] - [People 8+ Time Repeat],[People 7 Time Repeat])
```

### 8 Time Repeat Retention YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [8 Time Repeat Retention], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [8 Time Repeat Retention] -
CALCULATE ( [8 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [8 Time Repeat Retention], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Average Loan Defaulted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the average dollar amount of loans defaulted per record in the Fact Annual Payday Loan table.

**Calculation:**

```DAX
AVERAGE('Fact Annual Payday Loan'[Average Amount Loan Defaulted])
```

### Average Loan Defaulted YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Average Loan Defaulted], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Average Loan Defaulted] -
CALCULATE ( [Average Loan Defaulted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Average Loan Defaulted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Average Loan Granted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the average dollar amount of loans granted per record in the Fact Annual Payday Loan table.

**Calculation:**

```DAX
AVERAGE('Fact Annual Payday Loan'[Average Amount Loan Granted])
```

### Average Loan Granted / Defaulted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the ratio of the average loan granted to the average loan defaulted, indicating the proportion of granted loan value at risk of default.

**Calculation:**

```DAX
DIVIDE([Average Loan Granted],[Average Loan Defaulted])
```

### Average Loan Granted / Defaulted YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Average Loan Granted / Defaulted], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Average Loan Granted / Defaulted] -
CALCULATE ( [Average Loan Granted / Defaulted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Average Loan Granted / Defaulted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Average Loan Granted YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Average Loan Granted], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Average Loan Granted] -
CALCULATE ( [Average Loan Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Average Loan Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Default Rates

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the average default rate across payday loan records in the Fact Annual Payday Loan table.

**Calculation:**

```DAX
AVERAGE('Fact Annual Payday Loan'[Default Rate])
```

### Default Rates YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Default Rates], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Default Rates] -
CALCULATE ( [Default Rates], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Default Rates], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### NS Population

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Retrieves the maximum population value for Nova Scotia from the DimPopulationbyMonthProvince table, filtered to the Nova Scotia geography.

**Calculation:**

```DAX
CALCULATE(Max(DimPopulationbyMonthProvince[VALUE]), DimPopulationbyMonthProvince[Geography] = "Nova Scotia")
```

### Number of Repeat Borrowers

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the proportion of borrowers who were granted repeat loans relative to Nova Scotia's population.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. borrowers granted repeat loans]), [NS Population])
```

### Number of Repeat Borrowers YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Number of Repeat Borrowers], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Number of Repeat Borrowers] -
CALCULATE ( [Number of Repeat Borrowers], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Number of Repeat Borrowers], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Number of Repeat Loans Granted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the total count of repeat loans granted by summing the repeat loans column in the Fact Annual Payday Loan table.

**Calculation:**

```DAX
Sum('Fact Annual Payday Loan'[No. of repeat loans granted])
```

### Number of Repeat Loans Granted YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Number of Repeat Loans Granted], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Number of Repeat Loans Granted] -
CALCULATE ( [Number of Repeat Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Number of Repeat Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) ,0)
```

### People 1 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly once, expressed in thousands (divided by 1,000).

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 1 Time Repeat]),1000)
```

### People 2 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly twice, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 2 Time Repeat]),1000)
```

### People 3 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly 3 times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 3 Time Repeat]),1000)
```

### People 4 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly 4 times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 4 Time Repeat]),1000)
```

### People 5 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly 5 times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 5 Time Repeat]),1000)
```

### People 6 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly 6 times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 6 Time Repeat]),1000)
```

### People 7 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan exactly 7 times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 7 Time Repeat]),1000)
```

### People 8+ Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Returns the number of borrowers who took a loan 8 or more times, expressed in thousands.

**Calculation:**

```DAX
Divide(Sum('Fact Annual Payday Loan'[No. of 8+ Time Repeat]),1000)
```

### People Granted > 1 Loan

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Proportion of borrowers who received more than one payday loan relative to the NS population.

**Calculation:**

```DAX
DIVIDE(Sum('Fact Annual Payday Loan'[No. borrowers granted > 1 loan]), [NS Population])
```

### Percent People 1 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 1-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 1 Time Repeat],[NS Population])
```

### Percent People 1 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 1 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 1 Time Repeat] -
CALCULATE ( [Percent People 1 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 1 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 2 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 2-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 2 Time Repeat],[NS Population])
```

### Percent People 2 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 2 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 2 Time Repeat] -
CALCULATE ( [Percent People 2 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 2 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 3 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 3-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 3 Time Repeat],[NS Population])
```

### Percent People 3 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 3 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 3 Time Repeat] -
CALCULATE ( [Percent People 3 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 3 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 4 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 4-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 4 Time Repeat],[NS Population])
```

### Percent People 4 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 4 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 4 Time Repeat] -
CALCULATE ( [Percent People 4 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 4 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 5 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 5-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 5 Time Repeat],[NS Population])
```

### Percent People 5 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 5 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 5 Time Repeat] -
CALCULATE ( [Percent People 5 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 5 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 6 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 6-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 6 Time Repeat],[NS Population])
```

### Percent People 6 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 6 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 6 Time Repeat] -
CALCULATE ( [Percent People 6 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 6 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 7 Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 7-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 7 Time Repeat],[NS Population])
```

### Percent People 7 Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 7 Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 7 Time Repeat] -
CALCULATE ( [Percent People 7 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 7 Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent People 8+ Time Repeat

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The share of 8+-time repeat borrowers (in thousands) relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([People 8+ Time Repeat],[NS Population])
```

### Percent People 8+ Time Repeat YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent People 8+ Time Repeat], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent People 8+ Time Repeat] -
CALCULATE ( [Percent People 8+ Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent People 8+ Time Repeat], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Percent Repeat Borrowers

**Source table:** `Fact Annual Payday Loan`

**Explanation:** The proportion of repeat borrowers relative to the Nova Scotia population.

**Calculation:**

```DAX
DIVIDE([Number of Repeat Borrowers],[NS Population])
```

### Percent Repeat Borrowers YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Percent Repeat Borrowers], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Percent Repeat Borrowers] -
CALCULATE ( [Percent Repeat Borrowers], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Percent Repeat Borrowers], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Repeat Loans Granted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Total count of repeat loans granted — equivalent to Number of Repeat Loans Granted; sums the repeat loans column directly.

**Calculation:**

```DAX
Sum('Fact Annual Payday Loan'[No. of repeat loans granted])
```

### Repeat Loans Granted YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Repeat Loans Granted], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Repeat Loans Granted] -
CALCULATE ( [Repeat Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Repeat Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Total Number of Loans

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Sums the total loans granted column to give the overall count of payday loans issued.

**Calculation:**

```DAX
Sum('Fact Annual Payday Loan'[Total Loans Granted])
```

### Total Number of Loans YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Total Number of Loans], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Number of Loans] -
CALCULATE ( [Total Number of Loans], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Total Number of Loans], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Total Repeat Loans / Total Loans

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the ratio of total loans to repeat loans granted, indicating what proportion of all loans are repeat loans.

**Calculation:**

```DAX
DIVIDE([Total Number of Loans],[Repeat Loans Granted])
```

### Total Repeat Loans / Total Loans YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Total Repeat Loans / Total Loans], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Repeat Loans / Total Loans] -
CALCULATE ( [Total Repeat Loans / Total Loans], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Total Repeat Loans / Total Loans], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Total Value of Loans Granted

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Sums the estimated total value of loans granted in the Fact Annual Payday Loan table.

**Calculation:**

```DAX
Sum('Fact Annual Payday Loan'[Estimated Total Value of Loans Granted])
```

### Total Value of Loans YoY % Change

**Source table:** `Fact Annual Payday Loan`

**Explanation:** Calculates the year-over-year percentage change in [Total Value of Loans], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Value of Loans Granted] -
CALCULATE ( [Total Value of Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Total Value of Loans Granted], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

## Fact Employment average hourly and weekly earnings

**Measures in this table**
- [Avg Weekly Earnings](#avg-weekly-earnings)
- [Avg Weekly Earnings (Hourly)](#avg-weekly-earnings-hourly)
- [Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)](#avg-weekly-earnings-hourly-avg-weekly-earnings-salaried)
- [Avg Weekly Earnings (Salaried)](#avg-weekly-earnings-salaried)
- [Earnings (Hourly) / Earnings (Salaried) MoM % Growth](#earnings-hourly-earnings-salaried-mom-growth)
- [Earnings (Hourly) / Earnings (Salaried) YoY % Growth](#earnings-hourly-earnings-salaried-yoy-growth)
- [Earnings (Hourly) MoM % Growth](#earnings-hourly-mom-growth)
- [Earnings (Hourly) YoY % Growth](#earnings-hourly-yoy-growth)
- [Earnings (Salaried) MoM % Growth](#earnings-salaried-mom-growth)
- [Earnings (Salaried) YoY % Growth](#earnings-salaried-yoy-growth)
- [Earnings MoM % Growth](#earnings-mom-growth)
- [Earnings YoY % Growth](#earnings-yoy-growth)
- [Earnings YTD](#earnings-ytd)
- [Province Earnings Rank](#province-earnings-rank)
- [Total Employment Earnings](#total-employment-earnings)

### Avg Weekly Earnings

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Returns the average weekly earnings (including overtime) for all employees, filtered to the relevant earning type in the Dim EarningType dimension.

**Calculation:**

```DAX
CALCULATE ( AVERAGE ( 'Fact Employment average hourly and weekly earnings'[VALUE] ), 'Dim EarningType'[Earning Type] = "Average weekly earnings including overtime for all employees" )
```

### Avg Weekly Earnings (Hourly)

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Returns the average weekly earnings (including overtime) specifically for hourly employees.

**Calculation:**

```DAX
CALCULATE ( AVERAGE ( 'Fact Employment average hourly and weekly earnings'[VALUE] ), 'Dim EarningType'[Earning Type] = "Average weekly earnings including overtime for hourly employees" )
```

### Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the ratio of average weekly earnings for hourly employees versus salaried employees.

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Hourly)],[Avg Weekly Earnings (Salaried)],0)
```

### Avg Weekly Earnings (Salaried)

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Returns the average weekly earnings (including overtime) specifically for salaried employees.

**Calculation:**

```DAX
CALCULATE ( AVERAGE ( 'Fact Employment average hourly and weekly earnings'[VALUE] ), 'Dim EarningType'[Earning Type] = "Average weekly earnings including overtime for salaried employees" )
```

### Earnings (Hourly) / Earnings (Salaried) MoM % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the month-over-month percentage change in [Earnings (Hourly) / Earnings (Salaried)], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)] -
CALCULATE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)),
CALCULATE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)))
```

### Earnings (Hourly) / Earnings (Salaried) YoY % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the year-over-year percentage change in [Earnings (Hourly) / Earnings (Salaried)], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)] -
CALCULATE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, YEAR)),
CALCULATE([Avg Weekly Earnings (Hourly) / Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, YEAR)))
```

### Earnings (Hourly) MoM % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the month-over-month percentage change in [Earnings (Hourly)], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Hourly)] -
CALCULATE([Avg Weekly Earnings (Hourly)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)),
CALCULATE([Avg Weekly Earnings (Hourly)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)))
```

### Earnings (Hourly) YoY % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the year-over-year percentage change in [Earnings (Hourly)], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Hourly)] -
CALCULATE([Avg Weekly Earnings (Hourly)], DATEADD('Dim Date'[REF_DATE], -1, Year)),
CALCULATE([Avg Weekly Earnings (Hourly)], DATEADD('Dim Date'[REF_DATE], -1, Year)))
```

### Earnings (Salaried) MoM % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the month-over-month percentage change in [Earnings (Salaried)], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Salaried)] -
CALCULATE([Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)),
CALCULATE([Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, MONTH)))
```

### Earnings (Salaried) YoY % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the year-over-year percentage change in [Earnings (Salaried)], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings (Salaried)] -
CALCULATE([Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, YEAR)),
CALCULATE([Avg Weekly Earnings (Salaried)], DATEADD('Dim Date'[REF_DATE], -1, YEAR)))
```

### Earnings MoM % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the month-over-month percentage change in [Earnings], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings] -
CALCULATE([Avg Weekly Earnings], DATEADD('Dim Date'[REF_DATE], -1, MONTH)),
CALCULATE([Avg Weekly Earnings], DATEADD('Dim Date'[REF_DATE], -1, MONTH)))
```

### Earnings YoY % Growth

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Calculates the year-over-year percentage change in [Earnings], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE([Avg Weekly Earnings] -
CALCULATE([Avg Weekly Earnings], DATEADD('Dim Date'[REF_DATE], -1, YEAR)),
CALCULATE([Avg Weekly Earnings], DATEADD('Dim Date'[REF_DATE], -1, YEAR)))
```

### Earnings YTD

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Returns the year-to-date total of average weekly earnings using TOTALYTD over the date dimension.

**Calculation:**

```DAX
TOTALYTD([Avg Weekly Earnings], 'Dim Date'[REF_DATE])
```

### Province Earnings Rank

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Ranks all provinces by average weekly earnings in descending order using RANKX, removing geography filter context with ALL.

**Calculation:**

```DAX
RANKX(ALL('Dim Geo'[Geogrphy]), [Avg Weekly Earnings],,DESC)
```

### Total Employment Earnings

**Source table:** `Fact Employment average hourly and weekly earnings`

**Explanation:** Sums the VALUE column in the average hourly and weekly earnings fact table, aggregating total earnings across all types in context.

**Calculation:**

```DAX
SUM('Fact Employment average hourly and weekly earnings'[VALUE])
```

## Fact Employment by industry

**Measures in this table**
- [Industry Employment Percentage](#industry-employment-percentage)
- [Industry Employment Rank](#industry-employment-rank)
- [Industry Employment Rate MoM % Change](#industry-employment-rate-mom-change)
- [Industry Employment Rate YoY % Change](#industry-employment-rate-yoy-change)
- [Industry Share by Province](#industry-share-by-province)
- [Industry Share by Province MoM % Change](#industry-share-by-province-mom-change)
- [Industry Share by Province YoY % Change](#industry-share-by-province-yoy-change)
- [Industry Share of Total Employment](#industry-share-of-total-employment)
- [Industry Share of Total Employment MoM % Change](#industry-share-of-total-employment-mom-change)
- [Industry Share of Total Employment YoY % Change](#industry-share-of-total-employment-yoy-change)
- [Percentage MoM % Change](#percentage-mom-change)
- [Total Employed (All Industries)](#total-employed-all-industries)
- [Total Employed Industry (Canada)](#total-employed-industry-canada)
- [Total Employment](#total-employment)
- [Total Employment MoM % Change](#total-employment-mom-change)
- [Total Employment YoY % Change](#total-employment-yoy-change)

### Industry Employment Percentage

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the proportion of industry employment relative to the total population by province, using average values from both the industry fact table and the population dimension.

**Calculation:**

```DAX
DIVIDE( AVERAGE( 'Fact Employment by industry'[VALUE] ), Average( 'DimPopulationbyMonthProvince'[VALUE] ) )
```

### Industry Employment Rank

**Source table:** `Fact Employment by industry`

**Explanation:** Ranks all industries by their total employment in descending order using RANKX with DENSE ranking, removing all industry filter context with ALL.

**Calculation:**

```DAX
RANKX( ALL ( 'Dim Industry'[Industry]), CALCULATE ( [Total Employment] ), , DESC, DENSE )
```

### Industry Employment Rate MoM % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the month-over-month percentage change in [Industry Employment Rate], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Employment Rate (%)] -
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, Month ) ),
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH) ) )
```

### Industry Employment Rate YoY % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the year-over-year percentage change in [Industry Employment Rate], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Employment Rate (%)] -
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ),
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ) )
```

### Industry Share by Province

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates a specific industry's share of total employment for Canada, representing regional contribution to national totals.

**Calculation:**

```DAX
DIVIDE ( SUM([VALUE]), [Total Employed Industry (Canada)] )
```

### Industry Share by Province MoM % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the month-over-month percentage change in [Industry Share by Province], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Industry Share by Province] -
CALCULATE ( [Industry Share by Province], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Industry Share by Province], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Industry Share by Province YoY % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the year-over-year percentage change in [Industry Share by Province], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Industry Share by Province] -
CALCULATE ( [Industry Share by Province], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Industry Share by Province], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Industry Share of Total Employment

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates a specific industry's share as a proportion of total employment across all industries.

**Calculation:**

```DAX
DIVIDE ( SUM([VALUE]), [Total Employed (All Industries)] )
```

### Industry Share of Total Employment MoM % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the month-over-month percentage change in [Industry Share of Total Employment], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Industry Share of Total Employment] -
CALCULATE ( [Industry Share of Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Industry Share of Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Industry Share of Total Employment YoY % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the year-over-year percentage change in [Industry Share of Total Employment], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Industry Share of Total Employment] -
CALCULATE ( [Industry Share of Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ),
CALCULATE ( [Industry Share of Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Percentage MoM % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the month-over-month percentage change in [Percentage], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
[Industry Employment Percentage] - CALCULATE ( [Industry Employment Percentage], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) )
```

### Total Employed (All Industries)

**Source table:** `Fact Employment by industry`

**Explanation:** Filters the industry fact table to the 'Total employed, all industries' industry category and returns the sum.

**Calculation:**

```DAX
CALCULATE ( sum('Fact Employment by industry'[VALUE]), 'Dim Industry'[Industry] = "Total employed, all industries" )
```

### Total Employed Industry (Canada)

**Source table:** `Fact Employment by industry`

**Explanation:** Filters the industry fact table to the Canada geography and returns total employment, used as the denominator for national share calculations.

**Calculation:**

```DAX
CALCULATE ( sum('Fact Employment by industry'[VALUE]), 'Dim Geo'[Geogrphy] = "Canada" )
```

### Total Employment

**Source table:** `Fact Employment by industry`

**Explanation:** Averages the VALUE column of the Fact Employment by Industry table to give overall employment across all industries and geographies in context.

**Calculation:**

```DAX
AVERAGE('Fact Employment by industry'[VALUE])
```

### Total Employment MoM % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the month-over-month percentage change in [Total Employment], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Total Employment] -
CALCULATE ( [Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Total Employment], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Total Employment YoY % Change

**Source table:** `Fact Employment by industry`

**Explanation:** Calculates the year-over-year percentage change in [Total Employment], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Employed] -
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

## Fact LabourForce characteristics by age group gender

**Measures in this table**
- [Employment Rate (%)](#employment-rate-)
- [Employment Rate MoM % Change](#employment-rate-mom-change)
- [Employment Rate YoY % Change](#employment-rate-yoy-change)
- [Full Time Employed](#full-time-employed)
- [Full Time Employed MoM % Change](#full-time-employed-mom-change)
- [Full Time Employed YoY % Change](#full-time-employed-yoy-change)
- [Part Time / Full Time Employed](#part-time-full-time-employed)
- [Part Time / Full Time Employed MoM % Change](#part-time-full-time-employed-mom-change)
- [Part Time / Full Time Employed YoY % Change](#part-time-full-time-employed-yoy-change)
- [Part Time Employed](#part-time-employed)
- [Part Time Employed MoM % Change](#part-time-employed-mom-change)
- [Part Time Employed YoY % Change](#part-time-employed-yoy-change)
- [Total Employed](#total-employed)
- [Total Employed MoM % Change](#total-employed-mom-change)
- [Total Employed YoY % Change](#total-employed-yoy-change)
- [Total Population](#total-population)
- [Total Population MoM % Change](#total-population-mom-change)
- [Total Population YoY % Change](#total-population-yoy-change)
- [Total Unemployed](#total-unemployed)
- [Total Unemployed MoM % Change](#total-unemployed-mom-change)
- [Total Unemployed YoY % Change](#total-unemployed-yoy-change)
- [Total Value of LabourForce Characteristics](#total-value-of-labourforce-characteristics)
- [Total Value of LabourForce Characteristics MoM % Change](#total-value-of-labourforce-characteristics-mom-change)
- [Total Value of LabourForce Characteristics MoM Change](#total-value-of-labourforce-characteristics-mom-change)
- [Total Value of LabourForce Characteristics YoY % Change](#total-value-of-labourforce-characteristics-yoy-change)
- [Total Value of LabourForce Characteristics YoY Change](#total-value-of-labourforce-characteristics-yoy-change)
- [Unemployment Rate (%)](#unemployment-rate-)
- [Unemployment Rate MoM % Change](#unemployment-rate-mom-change)
- [Unemployment Rate YoY % Change](#unemployment-rate-yoy-change)

### Employment Rate (%)

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the employment rate as the ratio of total employed persons to total population in the labour force characteristics fact table.

**Calculation:**

```DAX
DIVIDE ( [Total Employed], [Total Population], 0 )
```

### Employment Rate MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Employment Rate], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Employment Rate (%)] -
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Employment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Employment Rate YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Employment Rate], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Employment Rate (%)] -
CALCULATE ( [Employment Rate (%)], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Employment Rate (%)], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

### Full Time Employed

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Filters the labour force characteristics fact table to 'Full-time employment' and returns the total value.

**Calculation:**

```DAX
CALCULATE (AVERAGE ( 'Fact LabourForce characteristics by age group gender'[VALUE] ),'Dim Characteristics'[Labour force characteristics] = "Full-time employment")
```

### Full Time Employed MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Full Time Employed], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Full Time Employed] -
CALCULATE ( [Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH) ) )
```

### Full Time Employed YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Full Time Employed], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Full Time Employed] -
CALCULATE ( [Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ),
CALCULATE ( [Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR) ) )
```

### Part Time / Full Time Employed

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the ratio of part-time to full-time employment, indicating the relative balance between part-time and full-time workers.

**Calculation:**

```DAX
DIVIDE([Part Time Employed],[Full Time Employed])
```

### Part Time / Full Time Employed MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Part Time / Full Time Employed], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Part Time / Full Time Employed] -
CALCULATE ( [Part Time / Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Part Time / Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH) ),0 )
```

### Part Time / Full Time Employed YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Part Time / Full Time Employed], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Part Time / Full Time Employed] -
CALCULATE ( [Part Time / Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ),
CALCULATE ( [Part Time / Full Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR) ),0 )
```

### Part Time Employed

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Filters the labour force characteristics fact table to 'Part-time employment' and returns the total value.

**Calculation:**

```DAX
Full Time Employed = CALCULATE (AVERAGE ( 'Fact LabourForce characteristics by age group gender'[VALUE] ),'Dim Characteristics'[Labour force characteristics] = "Full-time employment")

```

### Part Time Employed MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Part Time Employed], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Part Time Employed] -
CALCULATE ( [Part Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Part Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Part Time Employed YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Part Time Employed], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Part Time Employed] -
CALCULATE ( [Part Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) ),
CALCULATE ( [Part Time Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR) ) )
```

### Total Employed

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Filters the labour force characteristics fact table to rows categorized as 'Employment' and returns the total value.

**Calculation:**

```DAX
CALCULATE ( AVERAGE ( 'Fact LabourForce characteristics by age group gender'[VALUE] ), 'Dim Characteristics'[Labour force characteristics] = "Employment" )
```

### Total Employed MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Total Employed], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Total Employed] -
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Total Employed YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Total Employed], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Employed] -
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Total Employed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Total Population

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Filters the labour force characteristics fact table to rows categorized as 'Population' and returns the total value.

**Calculation:**

```DAX
CALCULATE ( [Total Value of LabourForce Characteristics], 'Dim Characteristics'[Labour force characteristics] = "Population" )
```

### Total Population MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Total Population], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Total Population] -
CALCULATE ( [Total Population], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Total Population], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Total Population YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Total Population], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Population] -
CALCULATE ( [Total Population], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Total Population], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Total Unemployed

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Filters the labour force characteristics fact table to rows categorized as 'Unemployment' and returns the total value.

**Calculation:**

```DAX
CALCULATE ( [Total Value of LabourForce Characteristics], 'Dim Characteristics'[Labour force characteristics] = "Unemployment" CALCULATE ( AVERAGE ( 'Fact LabourForce characteristics by age group gender'[VALUE] ), 'Dim Characteristics'[Labour force characteristics] = "Unemployment")

```

### Total Unemployed MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Total Unemployed], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Total Unemployed] -
CALCULATE ( [Total Unemployed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Total Unemployed], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Total Unemployed YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Total Unemployed], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Unemployed] -
CALCULATE ( [Total Unemployed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Total Unemployed], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Total Value of LabourForce Characteristics

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Sums the VALUE column of the Fact LabourForce characteristics table across all characteristic types currently in filter context.

**Calculation:**

```DAX
SUM ( 'Fact LabourForce characteristics by age group gender'[VALUE] )
```

### Total Value of LabourForce Characteristics MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Total Value of LabourForce Characteristics], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Total Value of LabourForce Characteristics] -
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Total Value of LabourForce Characteristics MoM Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the absolute month-over-month change in [Total Value of LabourForce Characteristics], subtracting the prior month value from the current month value.

**Calculation:**

```DAX
[Total Value of LabourForce Characteristics] -
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) )
```

### Total Value of LabourForce Characteristics YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Total Value of LabourForce Characteristics], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Total Value of LabourForce Characteristics] -
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ),
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, Year ) ) )
```

### Total Value of LabourForce Characteristics YoY Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the absolute year-over-year change in [Total Value of LabourForce Characteristics], subtracting the prior year value from the current year value.

**Calculation:**

```DAX
[Total Value of LabourForce Characteristics] -
CALCULATE ( [Total Value of LabourForce Characteristics], DATEADD ( 'Dim Date'[REF_DATE], -1, YEAR ) )
```

### Unemployment Rate (%)

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the unemployment rate as the ratio of total unemployed to total population.

**Calculation:**

```DAX
DIVIDE ( [Total Unemployed], [Total Population] )
```

### Unemployment Rate MoM % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the month-over-month percentage change in [Unemployment Rate], comparing the current period value to the equivalent period one month prior using DATEADD(-1, MONTH).

**Calculation:**

```DAX
DIVIDE ( [Unemployment Rate (%)] -
CALCULATE ( [Unemployment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ),
CALCULATE ( [Unemployment Rate (%)], DATEADD ( 'Dim Date'[REF_DATE], -1, MONTH ) ) )
```

### Unemployment Rate YoY % Change

**Source table:** `Fact LabourForce characteristics by age group gender`

**Explanation:** Calculates the year-over-year percentage change in [Unemployment Rate], comparing the current period value to the same period in the prior year using SAMEPERIODLASTYEAR or DATEADD(-1, YEAR).

**Calculation:**

```DAX
DIVIDE ( [Unemployment Rate (%)] -
CALCULATE ( [Unemployment Rate (%)], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ),
CALCULATE ( [Unemployment Rate (%)], SAMEPERIODLASTYEAR ( 'Dim Date'[REF_DATE] ) ) )
```

## Fact NS minimum Wage

**Measures in this table**
- [% Change from Previous Increase](#-change-from-previous-increase)
- [Change from Previous Increase](#change-from-previous-increase)
- [Minimum Wage](#minimum-wage)

### % Change from Previous Increase

**Source table:** `Fact NS minimum Wage`

**Explanation:** Calculates the percentage change in minimum wage from one increase to the next.

**Calculation:**

```DAX
VAR CurrentIndex = MAX ( 'Fact NS minimum Wage'[Index] )
VAR CurrentValue = SUM ( 'Fact NS minimum Wage'[Minimum Wage Rate])
VAR PreviousValue = CALCULATE (SUM ( 'Fact NS minimum Wage'[Minimum Wage Rate] ),FILTER (
ALL ( 'Fact NS minimum Wage' ),'Fact NS minimum Wage'[Index] = CurrentIndex - 1'Fact NS minimum Wage'[ExperienceLevelKey] <> 2))RETURN DIVIDE (
CurrentValue - PreviousValue,PreviousValue)
```

### Change from Previous Increase

**Source table:** `Fact NS minimum Wage`

**Explanation:** Uses VAR logic to identify the current and previous minimum wage index values and returns the dollar change between consecutive minimum wage increases. Returns BLANK if no previous value exists.

**Calculation:**

```DAX
VAR CurrentIndex = MAX ( 'Fact NS minimum Wage'[Index] )
VAR CurrentValue = SUM ( 'Fact NS minimum Wage'[Minimum Wage Rate] )
VAR PreviousValue =
CALCULATE ( SUM ( 'Fact NS minimum Wage'[Minimum Wage Rate] ),
FILTER ( ALL ( 'Fact NS minimum Wage' ), 'Fact NS minimum Wage'[Index] = CurrentIndex - 1 && 'Fact NS minimum Wage'[ExperienceLevelKey] <> 2 ) )
RETURN
IF ( ISBLANK ( PreviousValue ), BLANK (), CurrentValue - PreviousValue )
```

### Minimum Wage

**Source table:** `Fact NS minimum Wage`

**Explanation:** Returns the average minimum wage rate from the Fact NS minimum Wage table.

**Calculation:**

```DAX
AVERAGE('Fact NS minimum Wage'[Minimum Wage Rate])
```

## Common calculation patterns

These patterns recur throughout the measures in this model:

### Year-over-year (YoY) % change
```DAX
DIVIDE(
    [Measure] - CALCULATE([Measure], SAMEPERIODLASTYEAR('Dim Date'[REF_DATE])),
    CALCULATE([Measure], SAMEPERIODLASTYEAR('Dim Date'[REF_DATE]))
)
```

### Month-over-month (MoM) % change
```DAX
DIVIDE(
    [Measure] - CALCULATE([Measure], DATEADD('Dim Date'[REF_DATE], -1, MONTH)),
    CALCULATE([Measure], DATEADD('Dim Date'[REF_DATE], -1, MONTH))
)
```

### Ratios
```DAX
DIVIDE([Numerator], [Denominator], 0)
```

### Dense ranking across a dimension
```DAX
RANKX(
    ALL('Dimension'[Column]),
    [Measure],
    ,
    DESC,
    DENSE
)
```
