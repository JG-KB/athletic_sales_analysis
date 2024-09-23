
# Sales Data Analysis Project

## Overview
This project involves analyzing athletic sales data from two CSV files for the years 2020 and 2021. The primary objective is to combine, clean, and analyze the data to uncover insights such as which regions, states, cities, and retailers generated the most sales, as well as identifying trends in specific product categories, like women's athletic footwear.

## Requirements and Features
The following tasks are completed in this project:

1. **Data Combination and Cleaning**:
   - The sales data from 2020 and 2021 is combined using the Pandas library.
   - The `invoice_date` column is converted to the `datetime` data type to allow for time-based analysis.
   
2. **Determine Which Region Sold the Most Products**:
   - The data is grouped by `region`, `state`, and `city`, and the total `units_sold` is calculated using both `groupby()` and `pivot_table()`.
   - The results are sorted to identify the top 5 regions that sold the most products.

3. **Determine Which Region Had the Most Sales**:
   - The `total_sales` for each region, state, and city is calculated using `groupby()` and `pivot_table()` and sorted in descending order to show the top 5 regions.

4. **Determine Which Retailer Had the Most Sales**:
   - Retailer data is aggregated by `retailer`, `region`, `state`, and `city`, and the total `sales` are calculated to find out which retailer generated the most sales.

5. **Determine Which Retailer Sold the Most Women's Athletic Footwear**:
   - The data is filtered for `Women's Athletic Footwear` and analyzed to find out which retailer sold the most units of this product.
   - The results are aggregated and sorted to identify the top-performing retailers in this category.

6. **Time-Based Analysis**:
   - **Daily Sales**: The sales data is resampled by day, showing which specific days had the highest sales for women's athletic footwear.
   - **Weekly Sales**: The data is resampled by week to show which weeks generated the most women's athletic footwear sales.

## Data Source
The data is sourced from two CSV files:
- `athletic_sales_2020.csv`
- `athletic_sales_2021.csv`

These files contain information on sales across various retailers, products, regions, and time periods, including details like `units_sold`, `total_sales`, and `operating_profit`.

## Tools and Libraries
The following Python libraries are required:
- **Pandas**: For data manipulation, cleaning, and analysis.
  
Install dependencies using the command:
```bash
pip install pandas
```

## How to Run
1. Place the two CSV files (`athletic_sales_2020.csv` and `athletic_sales_2021.csv`) in a folder named `resources`.
2. Run the Python script in the environment of your choice (Jupyter notebook, terminal, etc.).
3. The script will perform the analysis and output the required results.

## Example Code Usage
Here is a high-level example of how the data is aggregated using both `groupby()` and `pivot_table()` for analysis:

```python
# Using groupby to find total units sold by region, state, and city
region_sold_most_products_groupby_df = a_s_combined_df.groupby(['region', 'state', 'city'])['units_sold'].sum().reset_index()

# Using pivot_table for a similar operation
region_sold_most_products_pivot_df = a_s_combined_df.pivot_table(
    index=['region', 'state', 'city'],
    values='units_sold',
    aggfunc='sum'
).reset_index()
```

## Key Results
- The **Northeast region** (New York City) sold the most products overall.
- **West Gear** in California had the highest total sales in 2021.
- The day with the most sales for **Women's Athletic Footwear** was July 16, 2021, with over 1.5 million in sales.

## Conclusion
This analysis helps uncover valuable insights from athletic sales data, allowing businesses to make informed decisions on which regions, retailers, and product categories are performing well. It also highlights important time periods (days/weeks) for further investigation into sales trends.

By leveraging Pandas for data aggregation and analysis, we can answer key business questions and gain actionable insights.
