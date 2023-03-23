# Snowflake

## Coding Challenge Solutions

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
SELECT SUM(positive) FROM covid;
```

### 2. What percentage of COVID-19 cases resulted in death?

```sql
SELECT SUM(death)/SUM(positive) AS death_percent FROM covid;
```

### 3. How many positive COVID-19 tests are in each state?

Order from high-to-low.

```sql
SELECT state, SUM(positive) as sum_positive FROM covid
GROUP BY state ORDER BY sum_positive DESC;
```

### 4. When was the earliest positive COVID-19 test in each state?

Order from earliest-to-latest.

```sql
SELECT STATE, MIN(date) as earliest_date FROM covid
WHERE positive > 0 GROUP BY state ORDER BY earliest_date;
```

### 5. Which day of the week had the most positive COVID-19 tests?

Order from high-to-low.

```sql
SELECT DAYNAME(date) as day_of_week, SUM(positive) as sum_positive FROM covid
GROUP BY day_of_week ORDER BY sum_positive DESC;
```
