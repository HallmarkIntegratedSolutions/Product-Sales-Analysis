# Sales Performance Analysis for a Retail Store

## Project Aim

The aim of this analysis is to  analyse the sales performance of a retail store and to uncover key insights such as top-selling products, regional performance, monthly sales trends and other important findings. 

-----------

## Tools Used
1. Microsoft EXCEL for Data Cleaning and Data Summarization
2. SQL for Data Analysis
3. Power BI for Data Cleaning, Data Transformation and Data Visualization
4. GitHub for Report Documentation
----------

## Data Analysis

### *Summarization of total sales per region
This was done with the use of Microsoft EXCEL and the result is displayed 

The highest total sales (24,298) was recorded at South Region while the lowest total sales was recorded at West Region. West Region had the lowest sales (11,400) with reasons probably low advertisement, staff attitude etc.

We recommend that the company look keenly into the West region and make some adjustments so as to boost sales in that region.

-----------

### *Summarization of total sales per product
This was done with the use of Microsoft EXCEL and the result is displayed bel


The product with the highest total sales is hat while the product with the lowest total sales is jacket. 23% of the total sales came from hat.

We recommend that more hats be supplied to the firm to boost the business.
Jacket had the lowest quantity sold with 8% sales due to reasons probably choice and preference of customers or the likes.

The management of the company might take a survey to get interested jackets brand from society and introduce such jackets to the company.

--------------

### *Summarization of total sales and total revenue per product at a glance
This was done with the use of Microsoft EXCEL and the result is displayed below.



Though hat has the highest sales (15,929), it is not the product with the highest revenue. 
The product with the highest revenue (613,380) is shoe which has the second largest sales. 

--------

### *Summarization of total sales per region per product at a glance
This was done with the use of Microsoft EXCEL and the result is displayed below.




- At South region, hat and jacket were not available for sale.
- At East region, gloves and socks were not available for sale.
- At North Region, shoes, gloves and socks were not available for sale.
- At West Region, shirt and jacket were not available for sale.

- At South region, shoes had the highest sale of 9,930 while socks had the lowest sale of 4,464.
- At East region, hat had the highest sale of 8,871 while shoes had the lowest sale of 2,480.
- At North Region, shirt had the highest sale of 6,448 while jacket  had the lowest sale of 2,482.
- At West Region, hat had the highest sale of 3,486 while shoes had the lowest sale of 1,992.

It is interesting to note that the product with the highest sales in one region happen to be the product with the lowest sale in another region. For exampe, shoes had the highest sales at South region but it had the lowest sale at East region.

-------

### Using EXCEL Functions to calculate Average sales per product

We used EXCEL Function (AVERAGEIF) to calculate the average sales per product.
The function codes are displayed below:

```MICROSOFT EXCEL
=AVERAGEIF($C$2:$C$9922,"Gloves",$F$2:$F$9922)

=AVERAGEIF($C$2:$C$9922,"Hat",$F$2:$F$9922)

=AVERAGEIF($C$2:$C$9922,"Jacket",$F$2:$F$9922)

=AVERAGEIF($C$2:$C$9922,"Shirt",$F$2:$F$9922)

=AVERAGEIF($C$2:$C$9922,"Shoes",$F$2:$F$9922)

=AVERAGEIF($C$2:$C$9922,"Socks",$F$2:$F$9922)
```

The results are displayed in the table below


Gloves, hat and shirt had the highest average sales (8) while jacket had the lowest average sales (4). 

-------

### Using EXCEL Functions to calculate total revenue per region
We used EXCEL Functions to calculate total revenue per region and the function lines of code are displayed below:

```MICROSOFT EXCEL
= SUMIF($D$2:$D$9922,"East",$H$2:$H$9922)

= SUMIF($D$2:$D$9922,"North",$H$2:$H$9922)

=SUMIF($D$2:$D$9922,"South",$H$2:$H$9922)

=SUMIF($D$2:$D$9922,"West",$H$2:$H$9922)
```

The results are displayed in the table below

The highest revenue recorded from this sale analysis is from South Region with #927,820 while the lowest revenue was seen at West region with 300,345.
This implies that the business is functioning well at South region than any other region and it is recommended that  the management of the sales firm focus on what to do as to increase sales in other regions too.

------------

### Using Microsoft SQL for data analysis

- To calculate the total sales for each product category
```SQL
select product, sum(Quantity) as 'Total_Sales' from [dbo].[SalesData]
		group by product
		order by 2 desc
```
The result is displayed as below



As further confirmed using SQL Package, the product with the highest sales is hat. 

-------

- To compute the number of sales transactions in each region

```SQL
select region, count(Quantity) as 'Sales_Transaction_Number' from [dbo].[SalesData]
		group by region
		order by 2 desc
```

The result is displayed as below:



All the regions have almost equal frequency of sales transaction though the highest count of sales transaction (2483) came from the East.

------

To find the highest selling product by total sales value
select top 1 product, sum(Quantity) as 'QuantityTotal' from [dbo].[SalesData]
		group by product
		


Add scree 1.8
The highest selling product by total sales value is hat with 15929 total sales. 
