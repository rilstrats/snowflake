# Snowflake

## Account Creation

https://www.snowflake.com/en

## Data

https://app.snowflake.com/marketplace/listing/GZSNZ7F5UH/starschema-covid-19-epidemiological-data

## Coding Challenge

### 0. Setup

```sql
CREATE DATABASE code_challenge;
USE DATABASE code_challenge;

CREATE OR REPLACE VIEW covid AS
SELECT
    province_state AS state,
    date,
    positive_since_previous_day AS positive,
    negative_since_previous_day AS negative,
    death_since_previous_day AS death,
    hospitalized_since_previous_day AS hospitalized
FROM COVID19_EPIDEMIOLOGICAL_DATA.PUBLIC.CT_US_COVID_TESTS
WHERE country_region = 'United States';
```

### 1. How many positive COVID-19 tests are in our data?

```sql
SELECT ... FROM covid;
```

### 2. What percentage of COVID-19 cases resulted in death?

```sql
SELECT ... FROM covid;
```

### 3. How many positive COVID-19 tests are in each state?

Order from high-to-low.

```sql
SELECT ... FROM covid
GROUP BY ... ORDER BY ...;
```

### 4. When was the earliest positive COVID-19 test in each state?

Order from earliest-to-latest.

```sql
SELECT ... FROM covid
WHERE ... GROUP BY ... ORDER BY ...;
```

### 5. Which day of the week had the most positive COVID-19 tests?

Order from high-to-low.

```sql
SELECT DAYNAME(...), ... FROM covid
GROUP BY ... ORDER BY ...;
```
