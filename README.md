# Problem Statement
Analyze the World Population Dataset to uncover trends in population growth, regional distributions, and demographic changes across different countries, enabling insights into global population dynamics for informed decision-making and policy development.  

## 1. ASK  
Stakeholder: XYZ

### Questions:  
- Top 3 Countries with the Highest Population  
  Identify the top three countries with the largest population in the years 1980, 2000, 2010, and 2022. How have the rankings changed over time?
  
- Population Estimates of the 3 Most Populous Countries  
  Provide the estimated population numbers for the three countries with the highest populations, specifically China, India, and the United States, over the years.
  
- World Population Growth Rate in Each Census Year  
  Analyze the growth rate of the world population across different census years (1980, 2000, 2010, and 2022). How fast is the global population growing?
  
- Percentage Increase in Population Across Census Years  
  Calculate the percentage increase in the global population between each census year. What is the difference in growth from one census to the next?
  
- World Population Figures Across All Census Years  
  Present the total world population for all available census years (1980, 2000, 2010, and 2022). What trends do these numbers reveal?

- Predicted Population Growth Rate for 2030 and 2050    
  Based on current trends, predict the global population growth rate for the years 2030 and 2050. How might the growth trend change in the future
  
- Countries with Rapid Population Growth (1980–2022)  
  Identify countries that have experienced the most rapid population growth from 1980 to 2022. Which nations are growing the fastest and why?
  
- Countries with Population Decline (1980–2022)  
  Analyze which countries have seen a decline in population between 1980 and 2022. What factors might contribute to these decreases?

- Top 10 Countries Expected to Grow Rapidly by 2050    
  Predict which 10 countries are expected to see the most rapid population growth by 2050. Which nations will lead this future expansion?

- Top 10 Countries Expected to Decline Rapidly by 2050    
  Identify the 10 countries that are predicted to experience the fastest population decline by 2050. What might be causing this projected decrease?

- Top 5 Most Populous Countries by 2050    
  Forecast the five countries that will have the largest populations by 2050. How do current growth trends suggest these rankings will change?

- Predicted World Population in 2030 and 2050    
  Provide predictions for the total world population in 2030 and 2050. How large will the global population be in these future years?

- Top 10 Most Populous Countries in 2022    
  List the 10 countries with the highest populations in 2022. What are the key characteristics of these highly populated nations?

- Population Density of All Countries Across Census Years    
  Analyze the population density of every country over all available census years. How densely populated are different regions of the world?

  
## 2. PREPARE
## 3. PROCESS
## 4. ANALYZE  
Data Analyzing
MySQL was used to analyze data.

-- KPI’s REQUIREMENT --  
#Q1  
WITH cte22 AS(SELECT '2022' AS year,  
country_territory AS country, population_2022 AS population  
FROM world_population  
ORDER BY population_2022 DESC LIMIT 3),  
cte10 AS(  
SELECT '2010' AS year, country_territory AS country, population_2010 AS population  
FROM world_population  
ORDER BY population_2010 DESC LIMIT 3),  
cte00 AS(  
SELECT '2000' AS year, country_territory AS country, population_2000 AS population  
FROM world_population  
ORDER BY population_2000 DESC LIMIT 3),  
cte80 AS(  
SELECT '1980' AS year, country_territory AS country, population_1980 AS population  
FROM world_population  
ORDER BY population_1980 DESC LIMIT 3)  

SELECT * FROM cte80 UNION  
SELECT * FROM cte00 UNION  
SELECT * FROM cte10 UNION  
SELECT * FROM cte22  
## 5. SHARE
## 6. ACT
