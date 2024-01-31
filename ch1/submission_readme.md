### Question 1

The docker command is

`docker --rm`

### Question 2

wheel verison is `0.42.0`

### Question 3

```sql
SELECT count(*)
FROM green_tripdata
where lpep_pickup_datetime::date='2019-09-18'
```

### Question 4

```sql
SELECT  *
FROM green_tripdata
order by trip_distance desc
limit 1
```

### Question 5

```sql
with temp_2 AS (SELECT *
FROM green_tripdata AS gt
JOIN taxi_zone AS tz
ON tz."LocationID" = gt."PULocationID"
where "Borough"!='Unknown' AND lpep_pickup_datetime::date='2019-09-18'),

temp3 AS (SELECT "Borough", SUM(total_amount) sum_total_amount
from temp_2
GROUP BY "Borough"
ORDER BY sum_total_amount DESC)

SELECT *
FROM temp3
```
