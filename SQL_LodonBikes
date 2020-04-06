# Big Query

-- Total rodes above 60 seconds

SELECT 
  COUNT (rental_id)
FROM 
  `bigquery-public-data.london_bicycles.cycle_hire` 
WHERE 
    duration > 60;
    
-- Range date of dataset
 SELECT 
  MAX( end_date), MIN(end_date)
FROM 
  `bigquery-public-data.london_bicycles.cycle_hire`;
 
 -----------------------------
 
-- Are there any empty stations?

-- total bike stations 
SELECT  Count(id)
FROM 
  `bigquery-public-data.london_bicycles.cycle_stations`;
  
-- Empty docks ?
SELECT  ST_GeogPoint(longitude, latitude)  AS location_point, name, bikes_count, docks_count
FROM 
  `bigquery-public-data.london_bicycles.cycle_stations`
WHERE nbEmptyDocks = 0 ;

-- where are the empty stations?
SELECT
  ST_GeogPoint(longitude, latitude)  AS location_point, name, bikes_count
FROM 
  `bigquery-public-data.london_bicycles.cycle_stations`
WHERE bikes_count = 0 ; 

-- Total trips of empty stations

SELECT S.name AS station, S.bikes_count, COUNT(H.end_station_name) AS total_trips
 FROM `bigquery-public-data.london_bicycles.cycle_stations` AS S
 INNER JOIN `bigquery-public-data.london_bicycles.cycle_hire`AS H
 ON S.id = H.end_station_id
 WHERE S.bikes_count = 0
 
---------------------------------

 -- Most popular trips in the network
SELECT  start_station_name, end_station_name, count(rental_id) as Total_trips
FROM `bigquery-public-data.london_bicycles.cycle_hire` 
WHERE duration > 60
group by end_station_name, start_station_name
order by Total_trips desc;

-- starting and ending in same place check
SELECT *
FROM `bigquery-public-data.london_bicycles.cycle_hire` AS H
where h.end_station_name = "Hyde Park Corner, Hyde Park"
and h.start_station_name = "Hyde Park Corner, Hyde Park"
LIMIT 1000
 GROUP BY S.name, S.bikes_count; 
 
 ----------------------------------
 
-- most popular stations in the network
SELECT 
  station_name, count(rental_id) AS Total_Usage
FROM (
  SELECT rental_id, start_station_name as station_name
  FROM `bigquery-public-data.london_bicycles.cycle_hire`
  WHERE duration > 60
  
  UNION ALL
  
  SELECT rental_id, end_station_name as station_name
  FROM `bigquery-public-data.london_bicycles.cycle_hire`
  WHERE duration > 60
  )
GROUP BY station_name
ORDER BY Total_Usage desc
LIMIT 10;

-- Top 10 popular start station over 60 seconds
SELECT
  DISTINCT start_station_name, COUNT(start_station_name) AS total_start
FROM `bigquery-public-data.london_bicycles.cycle_hire`
WHERE duration > 60
GROUP BY start_station_name
ORDER BY total_start DESC
LIMIT 10;

-- Top 10 popular end station over 60 seconds
SELECT
  DISTINCT end_station_name, COUNT(end_station_name) AS total_end
FROM `bigquery-public-data.london_bicycles.cycle_hire`
WHERE duration > 60
GROUP BY end_station_name
ORDER BY total_end DESC
LIMIT 10;


-- Usage peak

SELECT 
  EXTRACT(HOUR FROM start_date) AS hour, 
  EXTRACT(DAYOFWEEK FROM start_date) AS week, 
  COUNT(rental_id) AS Total_rides
FROM `bigquery-public-data.london_bicycles.cycle_hire`
WHERE duration > 60
GROUP BY hour, week
ORDER BY Total_rides DESC;

SELECT EXTRACT(HOUR FROM start_date) AS hour, COUNT(rental_id) AS total_trips
FROM `bigquery-public-data.london_bicycles.cycle_hire`
WHERE duration > 60
GROUP BY hour
ORDER BY 2 DESC;

SELECT  
  EXTRACT(DAYOFWEEK FROM start_date) AS week, 
  COUNT(rental_id) AS Total_rides
FROM `bigquery-public-data.london_bicycles.cycle_hire`
WHERE duration > 60
GROUP BY week
ORDER BY Total_rides DESC;

---------------------------------
-- Are there differences in the types of rides that people take?

SELECT case when start_station_id=end_station_id then 'pleasure' else 'commute' end as Type_rider, 
       case when duration <= 60 then 'FalseRide'
            when duration < 600 then '10min-' 
            when duration < 1800 then '30min-' 
            when duration >= 1800 then "30min+" 
            end as duration_bucket, 
            count(rental_id) as Total_rides
FROM `bigquery-public-data.london_bicycles.cycle_hire`
GROUP BY Type_rider, duration_bucket
ORDER BY 3 desc;
