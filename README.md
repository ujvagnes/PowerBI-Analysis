# Data Preparation

The target.csv file was imported incorrectly, with Power BI creating column headers such as Column1, Column2, etc. To resolve this, I transformed the first row (containing Sales Person, Month, etc.) into headers. I then unpivoted all columns except the Sales Person. Since the date format ('Aug-21', 'Sept-21') was not recognized correctly as M-Y but as M-D with the actual year, I added a prefix '1-' to each date and changed the data type to Date.

The data from the actual.csv file required no further transformations. To optimize table connections, I created dimension tables for distinct salespeople and months by creating reference tables, removing unnecessary columns, and eliminating duplicates. Due to differences in granularity, I added a new column to the actuals table representing the start of the month. After finalizing the data model, I proceeded with the analysis.

# Questions

- Actual Performance by Product, Person & Team
- Which products have the highest profit per box?
- Forecast sales for the next 3 months
# Analysis

### Actual Performance by Product, Person & Team & Overall Variance by Sales Person
I created measures for Total Sales, Total Expenses, and Total Profit. Using a clustered column chart, I visualized the performance of each team. I also added a dropdown filter for products and a table displaying profit and salespeople names to enable filtering by relevant dimensions. Key indicators, including Variance in percentage, were highlighted as cards at the top of the page to facilitate comparison by salesperson, team, or product.

### Highest Profit per Box
To calculate Profit per Box, I created a new measure for Total Boxes. I then built a table, sorted by Profit per Box, to display the results.

### Forecast Sales for the Next 3 Months
On a new page, I used a line chart to visualize the forecast for total sales over the next 3 months. Lastly, I added navigation buttons to allow easy switching between pages.