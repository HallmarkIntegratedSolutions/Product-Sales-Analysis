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

## Data Summarization with MICROSOFT EXCEL

- Summarization of total sales per region
This was done with the use of Microsoft EXCEL and the result is displayed below

![Sales 1 1~2](https://github.com/user-attachments/assets/07b1077e-a95e-483e-b26f-78ca02af060e)

The highest total sales (24,298) was recorded at South Region while the lowest total sales was recorded at West Region. West Region had the lowest sales (11,400) with reasons probably low advertisement, staff attitude etc.

We recommend that the company look keenly into the West region and make some adjustments so as to boost sales in that region.

-----------

- Summarization of total sales per product
This was done with the use of Microsoft EXCEL and the result is displayed below

![Screenshot (84)~2](https://github.com/user-attachments/assets/22d31aa0-13aa-4b46-97dd-93940da058c9)

The product with the highest total sales is hat while the product with the lowest total sales is jacket. 23% of the total sales came from hat.

We recommend that more hats be supplied to the firm to boost the business.
Jacket had the lowest quantity sold with 8% sales due to reasons probably choice and preference of customers or the likes.

The management of the company might take a survey to get interested jackets brand from society and introduce such jackets to the company.

--------------

- Summarization of total sales and total revenue per product at a glance
This was done with the use of Microsoft EXCEL and the result is displayed below.

![Sales 1 3~2](https://github.com/user-attachments/assets/b4d6cd1d-ea44-4e7a-8d29-0409e974f7c4)


Though hat has the highest sales (15,929), it is not the product with the highest revenue. 
The product with the highest revenue (613,380) is shoe which has the second largest sales. 

--------

- Summarization of total sales per region per product at a glance
This was done with the use of Microsoft EXCEL and the result is displayed below.


![Screenshot (83)~2](https://github.com/user-attachments/assets/d25e019b-9453-4769-9928-0e73e42ea6db)


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

### Data Analysis with MS EXCEL
- Using EXCEL Functions to calculate Average sales per product

EXCEL Function (AVERAGEIF) was used to calculate the average sales per product.
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

![Sales 1 4~2](https://github.com/user-attachments/assets/8cfd1db4-c5b8-4670-afa0-719ea4e88074)

Gloves, hat and shirt had the highest average sales (8) while jacket had the lowest average sales (4). 

-------

- Using EXCEL Functions to calculate total revenue per region
EXCEL Function was used to calculate total revenue per region and the function lines of code are displayed below:

```MICROSOFT EXCEL
=SUMIF($D$2:$D$9922,"East",$H$2:$H$9922)

=
SUMIF($D$2:$D$9922,"North",$H$2:$H$9922)

=SUMIF($D$2:$D$9922,"South",$H$2:$H$9922)

=SUMIF($D$2:$D$9922,"West",$H$2:$H$9922)
```

The results are displayed in the table below

![Sales 1 5~2](https://github.com/user-attachments/assets/76eea254-15ec-4ad1-86ba-08410fecd3dd)


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

![Sales 1 6~3](https://github.com/user-attachments/assets/bab80ce9-cfc0-43de-bac2-18379cf7c094)


As further confirmed using SQL Package, the product with the highest sales is hat. 

-------

- To compute the number of sales transactions in each region

```SQL
select region, count(Quantity) as 'Sales_Transaction_Number' from [dbo].[SalesData]
		group by region
		order by 2 desc
```

The result is displayed as below

![Sales 1 7~2](https://github.com/user-attachments/assets/ae9aaa27-b0bb-41f1-b205-ecb99cd4b521)



All the regions have almost equal frequency of sales transaction though the highest count of sales transaction (2483) came from the East.

------

- To find the highest selling product by total sales value

```SQL
select top 1 product, sum(Quantity) as 'QuantityTotal' from [dbo].[SalesData]
		group by product
```

![Sales 1 8~2](https://github.com/user-attachments/assets/6cdebffd-8a68-4a00-8d22-5298564c7ab7)


The highest selling product by total sales value is hat with 15929 total sales. 

-----

- To calculate total revenue per product

``` SQL
select product, sum(Revenue) as 'Total_Revenue' from [dbo].[SalesData]
		group by product
		order by 2 desc
```

![Sales 1 9~2](https://github.com/user-attachments/assets/9ff93864-c5f1-4e5a-9495-c271d06d5c06)

The product with the highest revenue (613,380) is shoe while the product with the lowest revenue is socks with #180,785. (See fig 9, the visual dashboard) 

--------


- To calculate monthly sales for the current year
Firstly, extract month and year from the order date separately to give us a new dataset 

```SQL
select OrderMonth, sum(Quantity) as MonthlySales from [dbo].[Monthly_Sales_Data ]
	where Orderyear = 2024
	group by OrderMonth
```

![Sales 1 10~2](https://github.com/user-attachments/assets/932769a0-8e32-432e-bd23-772f233eb3d5)


- At year 2024, there was an increase in sales from the month of January to March but a sharp decrease in sales occured between April and May. 
- Total sales experienced a rapid increase during the month of June but it decreased at July. Thereafter, total sales increased at the month of August. 
- The highest total sales (5,928) was recorded at the month of June while the lowest sales (1488) was observed at the month of May. 

-------

- To find the top 5 customers by total purchase amount

```SQL
select top 5 Customer_Id, sum(Revenue) as 'Total_Purchase_Amount' from [dbo].[SalesData]
		group by Customer_Id
		order by 2 desc
```

![Sales 1 11~2](https://github.com/user-attachments/assets/359d453f-0904-43cb-b50c-0c423388fe28)


The customers with the highest total purchase amount are Cus1372, Cus1385, Cus1395, Cus1207 and Cus1075 all with equal amount of total purchase of 4,235.

-------------


- To calculate the percentage of total sales contributed by each region
select region

```SQL
	sum(Quantity) as Total_Sales,
	ROUND(
	sum(Quantity) * 100.0 / (select sum(Quantity) from [dbo].[SalesData]),
	2
	) as Percentage_Sales
	from [dbo].[SalesData]
	group by region
	WITH ROLLUP;
```

![Sales 1 12~2](https://github.com/user-attachments/assets/f01bab18-33bd-4a5c-bad9-57e79427b608)


The highest percentage (35.49%) of the total sales came from South region while the lowest percentage (16.65%) of total sales was observed from the West region. ( See fig 9, the visual dashboard). 

-------------

- To identify products with no sales in the last quarter
- 
```SQL
select product from [dbo].[Monthly_Sales_Data ]
	where OrderMonth in ('July','August','September') and Quantity = '0'
	group by product
```

![Sales 1 13~2](https://github.com/user-attachments/assets/77465c0d-c52b-4bd8-9019-17e3424d7e0f)

There was no product identified with no sales in the last quarter.

## Data Visualization with the use of MS POWER BI
