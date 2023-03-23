# Snowflake

## Coding Challenge Solutions

### 1. How many positive COVID-19 tests are in our data?

```sql
SELECT SUM(positive_since_previous_day)
FROM covid19_epidemiological_data.public.ct_us_covid_tests;
```

### 2. What percentage of COVID-19 cases resulted in death?

```sql
SELECT SUM(death_since_previous_day)/SUM(positive_since_previous_day) AS death_percent
FROM covid19_epidemiological_data.public.ct_us_covid_tests;
```

### 3. How many positive COVID-19 tests are in each state?

Order from high-to-low.

```sql
SELECT state, SUM(positive_since_previous_day) as sum_positive
FROM covid19_epidemiological_data.public.ct_us_covid_tests
GROUP BY state ORDER BY sum_positive DESC;
```

### 4. When was the earliest positive COVID-19 test in each state?

Order from earliest-to-latest.

```sql
SELECT STATE, MIN(date) as earliest_date
FROM covid19_epidemiological_data.public.ct_us_covid_tests
WHERE positive > 0 GROUP BY state ORDER BY earliest_date;
```

### 5. Which day of the week had the most positive COVID-19 tests?

Order from high-to-low.

```sql
SELECT DAYNAME(date) as day_of_week, SUM(positive_since_previous_day) as sum_positive
FROM covid19_epidemiological_data.public.ct_us_covid_tests
GROUP BY day_of_week ORDER BY sum_positive DESC;
```
