I actively learnt alot in the class of SQL queries where by Mr.Femi taught us alot of parts in the SQL such as create,Insert into,Drop,Truncate,update,exetra whereby we created a database in the SQL server manageent studio that he told us to download.There fore he also gave us to analyse a CSV file called international Breweries.

# International Breweries
This involves a range of queries designed to assess key metrics such as production, sales, distribution, inventory, and revenue. Here are a few examples that could form the basis of such an analysis:

SELECT * FROM [dbo].[International Breweries]

Data columns:
- SALES_ID
- SALES_REP
- EMAILS
- BRANDS
- PLANT_COST
- UNIT_PRICE
- QUANTITY
- COST
- PROFIT
- COUNTRIE
- REGION
- MONTHS
- YEARS

## Key SQL Queries

- Calulate the total profit
 
 ```
select sum(profit) as TotalProfit from [dbo].[International Breweries]

```
![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/profit.PNG)

- Calculate the total profit for Senegal

```
select sum(profit) as TotalProfit from [dbo].[International Breweries]
where countries = 'Senegal'
```
Provided insight into how much profit was contributed in Senegal, allowing for a profit-based performance evaluation within a specific market. 

![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/profit.PNG)

- Calculate the total profit for Nigeria in 2019

```
select sum(profit) as TotalProfit from [dbo].[International Breweries]
where countries = 'Nigeria' and YEARs = '2019'

```
![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/nigera.PNG)

Provided insight into how much profit was contributed in Nigeria in 2019, allowing for a profit-based performance evaluation within a specific market. 

- Calculate the total profit and brands for Nigeria in 2017 in descending order

```

select Brands, sum(profit) as TotalProfit 
from [dbo].[International Breweries]
where countries = 'Nigeria' and years = '2017'
Group by Brands
order by 2 desc

```
![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/brand.PNG)

Provided insight into how much each brand contributed to the profit in Nigeria in 2017, allowing for a brand-based performance evaluation within a specific market.

- Calculate the total profit for Heros Brand in Nigeria 2017

```
select  sum(profit) as TotalProfitHero from [dbo].[International Breweries]
where countries = 'Nigeria' and years = '2017' and brands ='Hero'

```
![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/hero.PNG) 

Provided insight into how much Hero brand contributed to the profit in Nigeria in 2017, allowing for a brand-based performance evaluation within a specific market.

- calculates the total profit for each country from 2017 to 2019, and orders the results by total profit in descending order

```
SELECT countries,
      CASE
	     WHEN COUNTRIES IN ('Nigeria', 'Ghana') then 'Anglophone'
		 Else 'Francophone'
End as CountriesGroup,
sum(Profit) as TotalProfit from [dbo].[International Breweries]
where years in ('2017', '2018', '2019')
Group by Countries
order by 3 desc

```
Categorized countries into 'Anglophone' and 'Francophone' regions, allowing for regional performance analysis. It showed that 'Anglophone' markets like Nigeria typically yielded higher profits compared to Francophone regions.

- Calculated the Total pofits for Year-over-Year Growth Analysis
```
SELECT years, SUM(profit) AS TotalProfit
FROM [dbo].[International Breweries]
WHERE countries = 'Nigeria' AND brand = 'Hero'
GROUP BY years
ORDER BY years;
```
![](https://github.com/sharifahstella/LITA-Class-Documentation-SQL/blob/main/cout.PNG)

Tracked the growth trend for the Hero brand in Nigeria, giving visibility into performance changes over multiple years.

## Analysis Insights
- Top Markets by Profit: Nigeria emerged as the highest-grossing country, especially for brands like Hero.
- Anglophone vs. Francophone: Anglophone regions had higher profits than Francophone, indicating potential for focused marketing and resource allocation in English-speaking markets.
- Yearly Profit Growth: Key brands displayed consistent year-over-year growth, indicating brand loyalty and market potential.

## Outcome Summary
This project provided actionable insights into which brands and regions generate the most profit, segmented the data based on linguistic regions for tailored strategies, and identified potential growth markets. The findings support targeted marketing efforts, resource allocation, and strategic decision-making for International Breweries’ leadership.

## Learning Outcomes 

Here are some key learning outcomes thati gained from the training program focused on SQL (Structured Query Language):

- Understanding of Database Concepts:Define key concepts such as databases, tables, schemas, and relationships.
  Explain the purpose and structure of relational databases.
- SQL Syntax Proficiency:Write and interpret basic SQL statements and Understand SQL syntax, keywords, and data types.
- Data Retrieval:Use SELECT statements to retrieve data from one or more tables.Apply filtering using WHERE clauses, sorting with ORDER BY, and grouping with GROUP BY.
- Data Manipulation:Perform data insertion, updates, and deletions using INSERT, UPDATE, and DELETE statements.Understand transaction control with COMMIT and ROLLBACK.
- Joins and Relationships:Utilize INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL JOIN to combine data from multiple tables.Explain primary and foreign key relationships and their importance in relational databases.
- Aggregation and Functions:Use aggregate functions like COUNT, SUM, AVG, MIN, and MAX to summarize data.Apply built-in SQL functions for data manipulation (e.g., string, date functions).
- Subqueries and Nested Queries:Write and understand subqueries and their applications in complex queries.Use correlated subqueries for more advanced data retrieval.


