--Primer ejercicio
SELECT count(*) FROM new_schema.flights;

--Segundo Ejercicio
Select
origin,
 AVG
 (ArrDelay) As Prom_arribades,
 AVG
 (DepDelay) As Prom_Sortidas
From new_schema.flights
Group by origin

--Tercer ejercicio
Select
Origin,
ColYear,
ColMonth,
 AVG
 (ArrTime) As Prom_arribades
From new_schema.flights
Group by Origin

--Cuarto ejercicio
Select
City,
ColYear,
Colmonth,
AVG
 (ArrDelay) As Prom_arribades
From new_schema.flights, new_schema.airports
group by city

--Quinto ejercicio 

Select
UniqueCarrier,
ColYear,
Colmonth,
Avg
(Cancelled) as total_cancelled
From new_schema.flights
where cancelled > 0.00020
group by uniquecarrier

--Sexto Ejercicio
Select
TailNum,
(DayOfWeek * distance) as TotalDistance
FROM New_Schema.Flights
Where TailNum > 0
group by TotalDistance
Order by TotalDistance desc
limit 10

--Septimo Ejercicio
Select
UniqueCarrier,
AVG
 (ArrDelay) As Avg_Delay
From new_schema.flights
group by uniquecarrier
having Avg_Delay > 10.000