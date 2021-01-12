# Soru 1

```sql
SELECT
  name,
  c.id AS car_id,
  c.model AS car_model,
  man.year AS manufacture_year,
  ARRAY(
  SELECT
    AS STRUCT p.* REPLACE(TIMESTAMP_ADD(p.date, INTERVAL 3 HOUR) AS date)
  FROM
    UNNEST(purchase) AS p) AS purchase
FROM
  tugce_dinc.semi_structured_hw
JOIN
  UNNEST(car) AS c
JOIN
  UNNEST(manufacture) AS man
ON
  c.id = man.id ;
```
