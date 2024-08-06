# _NHL Analysis SQL Project_ <BR/>
<img src="https://github.com/user-attachments/assets/71855b45-e510-43a5-a75c-858c8ffb959b" alt="NHL Image" width="300" height="200" /><br/>


### This project analyzes NHL player data to answer various questions such as player demographics, performance, physical fitness, team affiliations.

## Data Sources

The analysis uses three Excel sheets containing [Canadian Birth Numbers](DATA/canada_births_1991_2022.xlsm), [NHL Roster Details](DATA/nhl_rosters.xlsm), [NHL Team](DATA/nhl_teams.xlsm). They are also available under the 'Data' folder in the repository.

## Tools & Help

[SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)<br/>
[Configuration ](https://learn.microsoft.com/en-us/sql/ssms/tutorials/ssms-configuration?view=sql-server-ver16)<br/>
[SQL Wizard](https://learn.microsoft.com/en-us/sql/integration-services/import-export-data/start-the-sql-server-import-and-export-wizard?view=sql-server-ver16)<br/>

## Data
 Overall table view that gives an estimate of the tables and the total number of attributes it contains
```
SELECT 'canada_births_1991_2022$' AS Table_Name
       , 3 AS Total_Columns
       , count(*) AS Total_rows
  FROM hockey..canada_births_1991_2022$

 UNION	
      
SELECT 'nhl_rosters$' AS Table_Name
       , 19 AS Total_Columns
       , count(*) AS Total_rows	
  FROM hockey..nhl_rosters$

 UNION 

SELECT 'nhl_teams$' AS Table_Name
       , 2 AS Total_Columns
       ,count(*) AS Total_rows	   
  FROM Hockey..nhl_teams$
```
[TABLE VIEW](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md)<BR/>

### To better understand the relationship, look at the model available [Data Model](Data_Model/Model.png)

Q1. Write a query to calculate the total number of NHL player births for each year from 1991 to 2000.
```
SELECT YEAR(birth_date) AS birth_year
       , COUNT(birth_date) AS player_count
  FROM dbo.nhl_rosters$
 WHERE YEAR(birth_date) BETWEEN 1991 AND 2000
 GROUP BY YEAR(birth_date)
HAVING YEAR(birth_date) IS NOT NULL
 ORDER BY birth_year
```
[ANSWER 1](https://github.com/srishupadhyay/NHL-Analysis-SQL/tree/main/Query%20Output#q1-write-a-query-to-calculate-the-total-number-of-nhl-player-births-for-each-year-from-1991-to-2000)



Q2. Write a SQL query to calculate the top 3 teams with highest number of players who play forward. 
```
SELECT TOP 3
       COUNT(DISTINCT player_id) AS player_count
       , team_code
  FROM dbo.nhl_rosters$
 GROUP BY team_code
 ORDER BY player_count DESC
```
[ANSWER 2](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q2-write-a-sql-query-to-calculate-the-top-3-teams-with-highest-number-of-players-who-play-forward)


Q3. Write a SQL query to find players whose birth city starts with 'New '. Classify these players into 'Young' and 'Experienced' based on whether their birth year is after 1995.
```
SELECT distinct Player_Id
       , CONCAT(first_name,' ',last_name) AS Player_Name
       , birth_city AS Birth_City
       , CAST(birth_date as DATE) AS Date
       , CASE
             WHEN year(birth_date) < 1995 THEN 'Experienced'
             ELSE 'Young'
	     END AS Player_Classification
  FROM dbo.nhl_rosters$
 WHERE birth_city LIKE 'New %'
```

[ANSWER 3](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q2-write-a-sql-query-to-calculate-the-top-3-teams-with-highest-number-of-players-who-play-forward)







Q4. Classify and count players into 'Tall' and 'Short' category based on their height where a player is tall if they are 72 inches or more.
Give the total count with the classification.
```
WITH 
Players AS (
SELECT player_id AS Player_ID
       , CONCAT(first_name, ' ', last_name) AS Player_Name
       , CASE 
              WHEN height_in_inches > 72 THEN 'Tall'
              WHEN height_in_inches < 72 THEN 'Short'
              WHEN height_in_inches = 72 THEN 'Short'
              WHEN height_in_inches IS NULL THEN 'No Data'
         END AS 'Classification'
  FROM dbo.nhl_rosters$
)

SELECT COUNT(DISTINCT Player_ID) AS Player_Count
       ,Classification
  FROM Players
 GROUP BY Classification
```
[ANSWER 4](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q4-classify-and-count-players-into-tall-and-short-category-based-on-their-height-where-a-player-is-tall-if-they-are-72-inches-or-more-give-the-total-count-with-the-classification)

Q5. Write a query to rank the maximum average weight of the position types who are either from Toronto or Manitoba in all the years.
```
WITH 
Avg_Player_Weight AS (
SELECT ROUND(AVG(weight_in_kilograms),1) AS Avg_Weight
       , position_type AS Position
  FROM dbo.nhl_rosters$
 WHERE birth_city LIKE 'Toronto' OR birth_state_province LIKE 'Manitoba'
 GROUP BY position_type
)

SELECT *
       , RANK() OVER( ORDER BY Avg_Weight DESC) AS Avg_Weight_Rank
  FROM Avg_Player_Weight
```
[ANSWER 5](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q5-write-a-query-to-rank-the-maximum-average-weight-of-the-position-types-who-are-either-from-toronto-or-manitoba-in-all-the-years)

Q6. Write queries for a running total on yearly basis and for every month since the start.
```
SELECT year
       , month
       , SUM(births) OVER ( PARTITION BY year ORDER BY month ) AS birth_count
  FROM dbo.canada_births_1991_2022$
```
#### A.This gives us the monthly running total on yearly basis and resets every year.

[PART A](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q6-write-queries-for-a-running-total-on-yearly-basis-and-for-every-month-since-the-start)


```
SELECT year
       , month
       , SUM(births) OVER (ORDER BY year, month) AS birth_count
  FROM dbo.canada_births_1991_2022$
```
[PART B](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#b-this-gives-us-the-running-total-on-yearly-and-monthly-basis-since-the-start)

#### This gives us the running total on yearly and monthly basis since the start.

Q7. Write a query to calculate the Body Mass Index for each player with their Id, name, team, height, weight, and BMI as per their last match.
```
WITH 
data AS (
SELECT player_id AS Player_Id
       , CONCAT(first_name,' ',last_name) AS Player_Name
       , full_name AS Team_Name
       , (height_in_centimeters/100) AS Height
       , weight_in_kilograms AS Weight
       , ROUND(weight_in_kilograms/POWER((height_in_centimeters/100),2),2) AS BMI
       , RIGHT(CAST(season AS int),4) AS Season_End_Year
       , DENSE_RANK() OVER ( PARTITION BY Player_id ORDER BY RIGHT(CAST(season AS INT),4) DESC) AS Row_number

  FROM dbo.nhl_rosters$ AS r
  JOIN dbo.nhl_teams$ AS t
    ON r.team_code = t.team_code
)
SELECT Player_Id
       , Player_Name
       , Team_Name
       , Height
       , Weight
       , BMI
  FROM data
 WHERE Row_number = 1 
       AND height IS NOT NULL 
       AND weight IS NOT NULL
```
[ANSWER 7](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q7-write-a-query-to-calculate-the-body-mass-index-for-each-player-with-their-id-name-team-height-weight-and-bmi-as-per-their-last-match)

Q8. What were the average height, weight, BMI for all the teams for the year 1947.
```
WITH 
DATA AS (
SELECT player_id AS Player_Id
       , CONCAT(first_name,' ',last_name) AS Player_Name
       , full_name AS Team_Name
       , (height_in_centimeters/100) AS Height
       , weight_in_kilograms AS WEIGHT
       , round(weight_in_kilograms/power((height_in_centimeters/100),2),2) AS BMI
       , right(cast(season AS INT),4) AS Season_End_Year
       , dense_rank() OVER( PARTITION BY Player_id ORDER BY RIGHT(CAST(season AS INT),4) DESC) AS Row_number

  FROM dbo.nhl_rosters$ AS r
  JOIN dbo.nhl_teams$ AS t
    ON r.team_code = t.team_code
 )

SELECT Team_Name
       , ROUND(AVG(height),2) AS Avg_Team_Height
       , ROUND(AVG(weight),2) AS Avg_Team_Weight
       , ROUND(AVG(bmi),2) AS Avg_Team_BMI
  FROM data
 WHERE Season_End_Year = 1947
 GROUP BY Team_Name
```
[ANSWER 8](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q8-what-were-the-average-height-weight-bmi-of-all-the-teams-for-the-year-1947)

Q9. Categorise and count the atheletes into underweight, healthy, overweight and obese according to their BMI.
```
WITH
player AS (
SELECT player_id AS Player_Id
       , CONCAT(first_name,' ',last_name) AS Player_Name
       , full_name AS Team_Name
       , (height_in_centimeters/100) AS Height
       , weight_in_kilograms AS Weight
       , ROUND(weight_in_kilograms/POWER((height_in_centimeters/100),2),2) AS BMI
       , LEFT(CAST(season AS INT),4) AS Season_Start_Year
       , RIGHT(CAST(season AS INT),4) AS Season_End_Year
       , dense_rank() OVER ( PARTITION BY Player_id ORDER BY RIGHT(CAST(season AS INT),4) DESC) AS Row_number

 FROM  dbo.nhl_rosters$ AS r
 JOIN  dbo.nhl_teams$ AS t
   ON  r.team_code = t.team_code
),

BMI_Category AS (
SELECT BMI, Row_number      
       , CASE
             WHEN BMI <= 18.5 THEN 'Underweight'
             WHEN BMI BETWEEN 18.5 AND 24.9 THEN 'Healthy'
             WHEN BMI BETWEEN 25 AND 29.9 THEN 'Overweight'
             WHEN BMI >=30 THEN 'Obese'
         END AS 'Category'
 FROM player
WHERE Row_number = 1
)

SELECT count(Category) as Count_Total, Category
  FROM BMI_Category
 WHERE Category IS NOT NULL
 GROUP BY Category
```
[ANSWER 9](https://github.com/srishupadhyay/NHL-Analysis-SQL/blob/main/Query%20Output/README.md#q9-categorise-and-count-the-atheletes-into-underweight-healthy-overweight-and-obese-according-to-their-bmi)

