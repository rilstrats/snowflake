# Snowflake

## Account Creation

https://www.snowflake.com/en

## Data

https://app.snowflake.com/marketplace/listing/GZSNZ7F5UH/starschema-covid-19-epidemiological-data

## Coding Challenge

### 1. How many positive COVID-19 tests are in our data?

```sql
SELECT ... FROM ...;
```

### 2. What percentage of COVID-19 cases resulted in death?

```sql
SELECT ... FROM ...;
```

### 3. How many positive COVID-19 tests are in each state?

Order from high-to-low.

```sql
SELECT ... FROM ...
GROUP BY ... ORDER BY ...;
```

### 4. When was the earliest positive COVID-19 test in each state?

Order from earliest-to-latest.

```sql
SELECT ... FROM ...
WHERE ... GROUP BY ... ORDER BY ...;
```

### 5. Which day of the week had the most positive COVID-19 tests?

Order from high-to-low.

```sql
SELECT DAYNAME(...), ... FROM ...
GROUP BY ... ORDER BY ...;
```
