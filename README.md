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

### Key SQL Queries

 Calulate the total profit
 
 ```
select sum(profit) as TotalProfit from [dbo].[International Breweries]

```
Calculate the total profit for Senegal

```
select sum(profit) as TotalProfit from [dbo].[International Breweries]
where countries = 'Senegal'
```
Calculate the total profit for Nigeria in 2019

```
select sum(profit) as TotalProfit from [dbo].[International Breweries]
where countries = 'Nigeria' and YEARs = '2019'

```
Calculate the total profit and brands for Nigeria in 2017 in descending order

```

select Brands, sum(profit) as TotalProfit 
from [dbo].[International Breweries]
where countries = 'Nigeria' and years = '2017'
Group by Brands
order by 2 desc

```

Calculate the total profit for Heros Brand in Nigeria 2017

```
select  sum(profit) as TotalProfitHero from [dbo].[International Breweries]
where countries = 'Nigeria' and years = '2017' and brands ='Hero'

```

calculates the total profit for each country from 2017 to 2019, and orders the results by total profit in descending order

```

