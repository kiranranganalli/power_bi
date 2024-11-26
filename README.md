Pizza Sales Dashboard

Problem Statement
This dashboard helps the pizza business analyze sales data to improve operations and customer satisfaction. It identifies key performance indicators (KPIs) such as revenue trends, ingredient popularity, and order patterns. Using this dashboard, the business can uncover insights like peak sales hours, high-revenue pizzas, and popular pizza sizes.

Steps followed
Steps Followed

Step 1: Load Data into Power BI

The dataset used is a .csv file containing information about pizza orders, including pizza names, categories, ingredients, sizes, and order details like revenue, quantity, and time.The data was loaded into Power BI Desktop.

Step 2: Data Profiling

Opened the Power Query Editor and enabled the following options under the View tab: Column Distribution Column Quality Column Profile Enabled Column Profiling for the Entire Dataset (default setting profiles only 1000 rows).

Observed the dataset's quality: Identified no errors or empty values except in pizza_ingredients, where some fields contained missing or null values.

Step 3: Data Transformation

Duplicated the pizza_ingredients column for transformation. Split the pizza_ingredients column into rows to analyze individual ingredient popularity and revenue contribution.

Extracted the hour from the order_time column to analyze sales trends by time of day. Handled null values in critical columns like total_price and quantity to ensure accurate KPI calculations. Created calculated columns for: Revenue by Hour Ingredient Frequency Ensured that null or zero values were excluded when calculating averages or sums.

Step 4: Calculated Columns and Measures

Created a calculated column to extract the hour from order_time:

Hour = HOUR(pizza_sales[order_time])

Created measures for:

Total Revenue: Total_Revenue = SUM(pizza_sales[total_price])

Average Order Value (AOV): AOV = DIVIDE(SUM(pizza_sales[total_price]), COUNTDISTINCT(pizza_sales[order_id]))

Ingredient Popularity: A count of individual ingredient occurrences after splitting the pizza_ingredients column.

Revenue by Ingredient: Revenue_By_Ingredient = SUM(pizza_sales[total_price])

Step 5: Visualizations

Ingredient Popularity:

Type: Horizontal bar chart.

X-Axis: Ingredients.

Y-Axis: Count of occurrences.

Purpose: Identifies the most used ingredients. Revenue by Hour:

Type: Line chart.

X-Axis: Hour of the day.

Y-Axis: Total revenue.

Purpose: Highlights peak sales hours to optimize operations.

Top Ingredients by Revenue:

Type: Horizontal bar chart.

X-Axis: Ingredients.

Y-Axis: Revenue contribution.

Purpose: Identifies ingredients contributing the most to revenue.

Order Trends by Pizza Size and Category:

Type: Stacked bar chart.

Purpose: Visualizes preferences across sizes and categories.

Revenue Contribution by Pizza Size:

Type: Pie chart.

Purpose: Highlights revenue share of each pizza size.

Step 6: Slicers and Filters

Added slicers for:

Pizza size

Pizza category

Order date

Order time

Filters allow users to drill down into specific segments for deeper insights.

Step 7: Publishing

The dashboard was published to Power BI Service. A descriptive title, company logo, and slicers were added for an enhanced user experience.

Insights

Total Revenue and Sales:

Total revenue generated: $[X]. Total pizzas sold: [X]. Popular Ingredients:

Most frequently used ingredient: [Ingredient Name]. Ingredients with the highest revenue contribution: [Top Ingredient Names]. Sales Trends:

Peak sales hours: [Time Ranges]. Days with the highest number of orders: [Day Names]. Order Preferences:

Most popular pizza size: [Size]. Most popular pizza category: [Category]. High-Revenue Items:

Pizzas generating the highest revenue: [Top Pizzas]. Revenue by Time:
