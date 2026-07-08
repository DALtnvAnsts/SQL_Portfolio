# SQL Portfolio

## Project Overview

This project contains SQL queries created using the MySQL World sample database.  
The aim of this project was to practise SQL queries and demonstrate basic data analysis skills.

## Skills Demonstrated

- SELECT statements
- WHERE filtering
- ORDER BY
- LIMIT
- INNER JOIN
- LEFT JOIN
- GROUP BY
- COUNT()
- Table aliases
- Multiple filtering conditions

---

## 1. Country with the Highest Life Expectancy

```sql
SELECT Name, LifeExpectancy
FROM country
ORDER BY LifeExpectancy DESC
LIMIT 1;

Result: Andorra has the highest life expectancy with 83.5 years.
---

## 2. Countries and Their Capital Cities

``sql

SELECT c.Name AS Country,
       ci.Name AS CapitalCity
FROM country c
JOIN city ci
ON c.Capital = ci.ID;

Purpose: This query uses an INNER JOIN to show countries together with their capital cities.

## 3. Number of Cities by Country

''sql

SELECT c.Name AS Country,
       COUNT(ci.ID) AS CityCount
FROM country c
LEFT JOIN city ci
ON c.Code = ci.CountryCode
GROUP BY c.Code, c.Name
ORDER BY CityCount DESC;
Purpose: This query uses LEFT JOIN, COUNT and GROUP BY to calculate how many cities are recorded for each country.

## 4. Official Languages in Europe
'''sql

SELECT c.Name AS Country,
       cl.Language AS OfficialLanguage
FROM country c
JOIN countrylanguage cl
ON c.Code = cl.CountryCode
WHERE c.Continent = 'Europe'
AND cl.IsOfficial = 'T';
Purpose: This query shows official languages in European countries using JOIN and WHERE conditions


Tools Used

* MySQL Workbench
* SQL
* MySQL World Sample Database

Conclusion

This project helped me practise SQL queries for data analysis, including filtering, sorting, joining tables and aggregating data.



