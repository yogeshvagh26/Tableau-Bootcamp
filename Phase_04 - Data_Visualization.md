# Phase 4: Data Visualization

Welcome to **Phase 4** – the heart of Tableau! After mastering data preparation (Phase 2) and calculations (Phase 3), you are now ready to bring your data to life through stunning, insightful visualisations.

Tableau is renowned for its visualisation capabilities. With its intuitive drag‑and‑drop interface and the powerful **Show Me** panel, you can create almost any chart type in seconds. But knowing *how* to create a chart is only half the battle. The real skill is knowing **which chart to use** for which type of analysis, and how to format it for maximum clarity and impact.

In this phase, we will explore every major chart type in Tableau, from simple tables to sophisticated dual-axis charts. Each lesson covers:
- What the chart is and when to use it.
- How to build it step‑by‑step.
- Real‑world business examples.
- Common mistakes and best practices.

Let's turn your data into a story!

---

## Lesson 4.1 – Tables and Crosstabs

### Concept Explanation

**Tables** are the foundation of data analysis. In Tableau, you can create two types:

1. **Text Table** – a simple grid of data, showing values (text). This is the most basic way to present data and is often used as a reference or for exporting.

2. **Crosstab** (Cross‑Tabulation) – a table that summarises data across two or more dimensions, showing aggregated values (e.g., sum of sales by product and region). It is similar to a pivot table in Excel.

**Why use tables?**

- Users often need to see the underlying numbers.

- Tables are essential for detailed reporting and auditing.

- They can be exported for further analysis.


**Key features**:
- **Subtotals and Grand Totals**: Automatically calculated.

- **Formatting**: Highlighting, conditional formatting, font styles.

- **Pagination**: If you have many rows, you can paginate.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Charts are great for patterns, but tables are essential for exact numbers, detailed reviews, and exporting data.

- **Use cases**:

  - A **financial report** shows revenue, expenses, and profit for each department in a table.

  - A **sales report** shows sales by product and region in a crosstab.

  - A **customer list** shows all customers with their contact details and purchase history.


---

### Step‑by‑Step Demonstration

**Creating a Text Table**:

1. Connect to Sample - Superstore.

2. Drag `Category` to **Rows**.

3. Drag `Sales` to **Text** on the Marks Card.

4. Drag `Profit` to **Text** as well.

5. You now have a simple table showing Sales and Profit by Category.


**Creating a Crosstab**:

1. Drag `Category` to **Rows**.

2. Drag `Region` to **Columns**.

3. Drag `Sales` to **Text**.

4. You now have a crosstab showing Sales by Category (rows) and Region (columns).


**Adding Subtotals and Grand Totals**:

1. From the menu: **Analysis** → **Totals** → **Subtotals** and **Grand Totals**.

2. You can enable them for rows, columns, or both.


**Formatting a Table**:

1. Click on the **Format** menu → **Font** (or use the Format pane).

2. Change font size, colour, and style.

3. Use **Conditional Formatting**: click on the table, then the **Color** mark.


---

### Practical Examples

- **Example 1**: A **Sales by Category and Region** crosstab helps managers quickly compare performance across segments.

- **Example 2**: A **Customer Transactions** table helps a support agent look up a customer's purchase history.

- **Example 3**: A **Financial Summary** table lists all accounts with their balances, used for auditing.


---

### Hands‑on Exercises

1. Create a text table showing `Sales`, `Profit`, and `Quantity` by `Category`.

2. Create a crosstab showing `Sales` by `Category` (rows) and `Segment` (columns).

3. Enable **Grand Totals** for both rows and columns.

4. Format the table: change font to bold, add a border.

5. Export the crosstab as a CSV.


---

### Mini Quiz

1. What is the difference between a text table and a crosstab?

2. How do you add grand totals to a table?

3. How do you format a table in Tableau?

4. When would you use a table instead of a chart?

5. Can you export a table from Tableau?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Displaying too many rows – the table becomes unreadable | Limit rows using filters or pagination |
| Not enabling totals – users miss the big picture | Always enable totals and subtotals for crosstabs |
| Using default font sizes – hard to read | Increase font size and use bold for headers |
| Not sorting the data – random order is confusing | Sort columns/rows by the most important measure |
| Using a table for everything – charts are often better for patterns | Use tables for details, charts for trends and comparisons |

---

### Interview Questions

1. **What is the difference between a text table and a crosstab in Tableau?**  

   *Answer*: A text table displays data in rows and columns with text values. A crosstab is a table that summarises data across two or more dimensions, showing aggregated values (like a pivot table).

2. **How would you add subtotals to a crosstab?**  

   *Answer*: From the menu, select **Analysis → Totals → Subtotals**. You can choose to add them for rows, columns, or both.

3. **Can you conditionally format a table in Tableau?**  

   *Answer*: Yes, using the Color mark on the Marks Card, you can apply conditional formatting to highlight certain values.

---

### Assignment and Dashboard Projects

**Assignment 4.1** – Create a detailed crosstab report:

- Show Sales and Profit by Category and Region.

- Enable subtotals and grand totals.

- Apply conditional formatting: highlight Profit > 1000 in green, Profit < 0 in red.

- Format the table with a professional look.

- Save the report.


---

### Summary and Revision Notes

- Tables are essential for detailed data viewing.

- **Text Table** = simple grid; **Crosstab** = pivot‑table style.

- Enable subtotals and grand totals for context.

- Use conditional formatting to highlight key values.

---

## Lesson 4.2 – Bar Charts

### Concept Explanation

**Bar charts** are one of the most common and versatile chart types. They use rectangular bars to represent data, with the length or height of the bar proportional to the value it represents.

**Types of bar charts**:

| **Type** | **Description** | **Use Case** |
|----------|-----------------|--------------|
| **Vertical Bar Chart** | Bars are vertical (default). | Comparing categories (e.g., sales by product). |
| **Horizontal Bar Chart** | Bars are horizontal. | When category names are long. |
| **Stacked Bar Chart** | Bars are divided into segments. | Showing composition within each category. |
| **Side‑by‑Side Bar Chart** | Bars are grouped. | Comparing multiple measures across categories. |

**When to use bar charts**:

- Comparing values across categories.

- Showing rankings (top 10 products).

- Displaying frequencies (distribution).


---

### Importance and Real‑World Use Cases

- **Why it matters**: Bar charts are intuitive and universally understood. They are the go‑to chart for categorical comparisons.

- **Use cases**:

  - A **sales manager** uses a bar chart to compare sales across regions.

  - A **marketing analyst** uses a stacked bar chart to show the composition of leads by channel.

  - A **product manager** uses a horizontal bar chart to show product rankings.


---

### Step‑by‑Step Demonstration

**Basic Bar Chart**:

1. Connect to Sample - Superstore.

2. Drag `Category` to **Columns**.

3. Drag `Sales` to **Rows**.

4. Tableau creates a vertical bar chart.

5. Drag `Region` to **Color** on the Marks Card – bars are coloured by region.


**Horizontal Bar Chart**:

1. Drag `Category` to **Rows** and `Sales` to **Columns** – bars become horizontal.


**Stacked Bar Chart**:

1. Drag `Category` to **Columns**, `Sales` to **Rows**.

2. Drag `Region` to **Color** – the bars are now stacked by region.

3. To make it 100% stacked, right‑click on the axis → **Add Table Calculation** → **Percent of Total**.


**Side‑by‑Side Bar Chart**:

1. Drag `Category` to **Columns**, `Sales` to **Rows**.

2. Drag `Region` to **Columns** (before Category) – creates side‑by‑side bars.

---

### Practical Examples

- **Example 1**: A bar chart showing Sales by Category helps identify which category generates the most revenue.

- **Example 2**: A horizontal bar chart showing Profit by Sub‑Category (long names) makes it easy to read.

- **Example 3**: A stacked bar chart showing Sales by Category and Region helps see both overall performance and regional composition.


---

### Hands‑on Exercises

1. Create a vertical bar chart showing Sales by Category.

2. Create a horizontal bar chart showing Profit by Sub‑Category.

3. Create a stacked bar chart showing Sales by Category, stacked by Region.

4. Create a side‑by‑side bar chart showing Sales by Category and Region.

5. Sort the bars from highest to lowest.

---

### Mini Quiz

1. When would you use a horizontal bar chart instead of a vertical one?

2. What is the difference between a stacked bar chart and a side‑by‑side bar chart?

3. How do you sort bars in descending order?

4. How would you create a 100% stacked bar chart?

5. What mark type is used for a bar chart?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not sorting bars – random order is hard to compare | Sort bars in descending order for quick insights |
| Using too many categories – bars become thin and unreadable | Limit to 10‑15 categories; use a "Top N" filter for the rest |
| Using stacked bars when you want to compare totals – hard to compare across stacks | Use side‑by‑side for comparing totals; stacked for showing composition |
| Not labelling bars – users can't see exact values | Add labels (right‑click → Add Data Labels) |
| Using 3D effects – they distort perception | Keep bar charts 2D |

---

### Interview Questions

1. **When would you use a bar chart vs a line chart?**  

   *Answer*: A bar chart is used for categorical comparisons (e.g., sales by product). A line chart is used for trends over continuous data (e.g., sales over time).

2. **How do you create a stacked bar chart in Tableau?**  

   *Answer*: Drag one dimension to Columns, a measure to Rows, and another dimension to Color on the Marks Card. The bars will automatically stack.

3. **What is the best way to sort a bar chart?**  

   *Answer*: Click the sort icon on the axis or right‑click the field in Rows/Columns and select **Sort**.

---

### Assignment and Dashboard Projects

**Assignment 4.2** – Create a dashboard with multiple bar charts:

- A vertical bar chart showing Sales by Category, sorted descending.

- A horizontal bar chart showing Profit by Sub‑Category, sorted.

- A stacked bar chart showing Sales by Category and Region.

- A side‑by‑side bar chart showing Sales and Profit by Category.

- Format all charts consistently and add titles.

---

### Summary and Revision Notes

- Bar charts compare categories.

- Types: vertical, horizontal, stacked, side‑by‑side.

- Sort bars for readability.

- Add labels for exact values.

---

## Lesson 4.3 – Line Charts

### Concept Explanation

**Line charts** display data points connected by a line, making them ideal for showing trends over time or continuous data. They are the default choice for time‑series analysis.

**Types of line charts**:

| **Type** | **Description** | **Use Case** |
|----------|-----------------|--------------|
| **Single Line** | One line showing one measure. | Tracking a single KPI over time. |
| **Multiple Lines** | Several lines on the same axis. | Comparing multiple measures or segments. |
| **Dual Axis Line** | Two lines with different axes. | Comparing two measures with different scales. |
| **Area Chart** | Line chart with the area below filled. | Emphasising magnitude of change. |

**When to use line charts**:

- Showing trends over time.

- Comparing multiple time series.

- Visualising continuous data (temperature, stock prices).


---

### Importance and Real‑World Use Cases

- **Why it matters**: Line charts reveal patterns, seasonality, and trends that are invisible in tables or bar charts.

- **Use cases**:

  - A **financial analyst** tracks stock price movements over time.
  
  - A **sales manager** monitors monthly revenue trends.
  
  - A **marketing analyst** compares website traffic across channels.
  

---

### Step‑by‑Step Demonstration

**Basic Line Chart**:

1. Connect to Sample - Superstore.

2. Drag `Order Date` to **Columns** – Tableau automatically treats it as a continuous date.

3. Drag `Sales` to **Rows**.

4. Tableau creates a line chart of sales over time.


**Adding Multiple Lines**:

1. Drag `Category` to **Color** on the Marks Card – you get multiple lines, one for each category.


**Changing Date Granularity**:

1. Click the drop‑down arrow on `Order Date` in Columns → choose **Year**, **Quarter**, **Month**, etc.


**Area Chart**:

1. On the Marks Card, change the mark type from **Line** to **Area**.


**Dual Axis Line Chart**:

1. Drag `Sales` to Rows.

2. Drag `Profit` to the other side of the Rows shelf – you get a dual‑axis chart with two axes.

3. Right‑click on the second axis → **Synchronize Axis** if you want a single scale.

---

### Practical Examples

- **Example 1**: A line chart showing monthly sales revenue helps identify seasonal patterns.

- **Example 2**: A multiple‑line chart shows sales by category over time, revealing which categories are growing.

- **Example 3**: A dual‑axis chart shows sales (bars) and profit margin (line) on the same view.


---

### Hands‑on Exercises

1. Create a line chart showing Sales over time (by month).

2. Add Category to Color to see multiple lines.

3. Change the date granularity to Quarter.

4. Convert the line chart to an area chart.

5. Create a dual‑axis line chart showing Sales and Profit.

---

### Mini Quiz

1. What is the primary use of a line chart?

2. How do you add multiple lines to a line chart?

3. How do you change the date granularity in a line chart?

4. What is the difference between a line chart and an area chart?

5. When would you use a dual‑axis line chart?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using a line chart for categorical data – the line implies continuity | Use bar charts for categories; line charts for continuous data |
| Not handling missing dates – lines can be misleading | Ensure your date axis is continuous and complete |
| Using too many lines – cluttered and unreadable | Limit to 3‑5 lines; use a "Top N" filter |
| Forgetting to add labels or tooltips – users can't see exact values | Add labels for key points or use tooltips |
| Using an area chart with overlapping data – hides lower lines | Use line charts for clarity; area charts for emphasis on magnitude |

---

### Interview Questions

1. **When would you use a line chart vs a bar chart?**  

   *Answer*: A line chart is for trends over continuous data (e.g., time). A bar chart is for comparing discrete categories.

2. **How do you create a dual‑axis line chart in Tableau?**  

   *Answer*: Drag two measures to Rows, right‑click on one axis, and select **Dual Axis**. You can then synchronise the axes if needed.

3. **What is the advantage of a continuous date axis over a discrete date axis?**  

   *Answer*: A continuous date axis creates a smooth trend line and fills missing dates. A discrete date axis creates separate marks (bars) for each date, which is better for comparisons.

---

### Assignment and Dashboard Projects

**Assignment 4.3** – Create a line chart dashboard:

- A line chart showing Sales over time (monthly).

- Add Category to Color.

- A dual‑axis chart showing Sales and Profit Margin % over time.

- Add a filter for Region.

- Format the charts with clear titles and gridlines.

---

### Summary and Revision Notes

- Line charts show trends over continuous data.

- Use multiple lines for comparisons.

- Area charts emphasise magnitude.

- Dual‑axis charts combine two measures.

- Ensure date axes are continuous for accurate trends.

---

## Lesson 4.4 – Area Charts

### Concept Explanation

**Area charts** are essentially line charts where the area below the line is filled with colour. They are used to emphasise the magnitude of change over time, showing the cumulative effect of data.

**Types of area charts**:

| **Type** | **Description** | **Use Case** |
|----------|-----------------|--------------|
| **Simple Area Chart** | One line with filled area. | Showing a single metric over time. |
| **Stacked Area Chart** | Multiple areas stacked on top of each other. | Showing composition over time (e.g., revenue by product). |
| **100% Stacked Area Chart** | Stacked areas that sum to 100%. | Showing proportional change over time. |

**When to use area charts**:
- When you want to emphasise the magnitude of change.
- When showing cumulative totals over time.
- When comparing the composition of a total over time.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Area charts make it easy to see the "big picture" – how totals and components change over time.

- **Use cases**:

  - A **financial analyst** uses a stacked area chart to show revenue composition by product line over years.

  - A **marketing analyst** uses an area chart to show the cumulative number of leads over a campaign.

  - A **supply chain manager** uses a 100% stacked area chart to show inventory composition by category.


---

### Step‑by‑Step Demonstration

**Simple Area Chart**:

1. Connect to Sample - Superstore.

2. Drag `Order Date` to **Columns**.

3. Drag `Sales` to **Rows**.

4. On the Marks Card, change the mark type from **Automatic** to **Area**.


**Stacked Area Chart**:

1. Drag `Order Date` to **Columns**, `Sales` to **Rows**.

2. Drag `Category` to **Color** on the Marks Card.

3. Tableau creates a stacked area chart.


**100% Stacked Area Chart**:

1. Follow the stacked area steps above.

2. Right‑click on the Sales axis → **Add Table Calculation** → **Percent of Total**.

3. Configure the calculation to compute across categories.


---

### Practical Examples

- **Example 1**: A stacked area chart showing sales by category over time reveals which categories are growing and which are shrinking.

- **Example 2**: A 100% stacked area chart shows the proportion of sales by category over time, highlighting changes in market share.

- **Example 3**: An area chart showing cumulative sales helps track progress towards an annual target.


---

### Hands‑on Exercises

1. Create a simple area chart of Sales over time (by month).

2. Create a stacked area chart of Sales by Category over time.

3. Create a 100% stacked area chart of Sales by Category over time.

4. Compare the three charts and note the differences.

---

### Mini Quiz

1. What is the difference between a line chart and an area chart?

2. When would you use a stacked area chart?

3. What is a 100% stacked area chart used for?

4. How do you change a line chart to an area chart in Tableau?

5. Why might you use an area chart instead of a line chart?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using area charts with overlapping data – lower areas are hidden | Use line charts when you need to see all lines clearly; use area charts for emphasis on totals |
| Not using transparency – overlapping areas become muddy | Apply transparency to area charts with multiple categories |
| Using stacked area charts when you want to compare individual categories – hard to compare | Use line charts for comparing individual categories; area charts for composition |
| Overcomplicating the chart with too many categories | Limit to 3‑5 categories; group the rest as "Other" |

---

### Interview Questions

1. **When would you use an area chart instead of a line chart?**  

   *Answer*: An area chart emphasises the magnitude of change and cumulative totals. It is useful when you want to show the "volume" of data, not just the trend.

2. **What is the difference between a stacked area chart and a 100% stacked area chart?**  

   *Answer*: A stacked area chart shows the absolute values of each category stacked together. A 100% stacked area chart shows the proportional contribution of each category (each category sums to 100% at each point).

3. **How do you create a 100% stacked area chart in Tableau?**  

   *Answer*: Create a stacked area chart, then right‑click on the measure axis and add a table calculation for Percent of Total.

---

### Assignment and Dashboard Projects

**Assignment 4.4** – Create a dashboard with area charts:

- A simple area chart of Sales over time.

- A stacked area chart of Sales by Category over time.

- A 100% stacked area chart of Sales by Category over time.

- Add a filter for Region.

- Add titles and format the colours.


---

### Summary and Revision Notes

- Area charts are line charts with filled areas.

- Stacked area charts show composition over time.

- 100% stacked shows proportional change.

- Use transparency for overlapping areas.

---

## Lesson 4.5 – Pie Charts

### Concept Explanation

**Pie charts** show the proportion of a whole. They are circular charts divided into slices, with each slice representing a category's contribution to the total.

**When to use pie charts**:

- When you have 2‑5 categories.

- When you want to show part‑to‑whole relationships.

- When the differences between categories are significant.


**When NOT to use pie charts**:

- More than 5 categories – slices become too small.

- When you want to compare individual categories – bar charts are better.

- When you have many similar values – difficult to distinguish.


**Donut chart**: A pie chart with a hole in the centre (created by adding a zero‑value dimension or using a dual‑axis with a smaller pie).


---

### Importance and Real‑World Use Cases

- **Why it matters**: Pie charts are intuitive and widely understood, but they are often misused. Used correctly, they are effective for showing composition.

- **Use cases**:

  - A **marketing analyst** shows the distribution of traffic by channel (organic, paid, social, direct).

  - A **financial analyst** shows the composition of expenses by category.

  - A **sales manager** shows the market share by product category.


---

### Step‑by‑Step Demonstration

**Basic Pie Chart**:

1. Connect to Sample - Superstore.

2. Drag `Category` to **Color** on the Marks Card.

3. Drag `Sales` to **Angle** on the Marks Card.

4. Tableau creates a pie chart.

5. Drag `Sales` to **Label** to show the values.


**Donut Chart**:

1. Create a pie chart.

2. On the Marks Card, change the mark type to **Pie**.

3. Create a second pie chart with no fields.

4. Double‑click on the Rows shelf and enter `0` – this creates a zero axis.

5. Drag the second pie chart to the same axis and make it smaller (using Size).

6. Format the inner pie to be white (or transparent) – creates a donut effect.


**Sorting Pie Slices**:

- Right‑click on the dimension in Color → **Sort** → sort by the measure.

---

### Practical Examples

- **Example 1**: A pie chart showing sales by category helps quickly identify the largest category.

- **Example 2**: A donut chart showing profit by region is a modern, clean alternative to a traditional pie chart.

---

### Hands‑on Exercises

1. Create a pie chart showing Sales by Category.

2. Add labels showing the percentage of total.

3. Create a donut chart showing Sales by Region.

4. Sort the slices from largest to smallest.

---

### Mini Quiz

1. When should you use a pie chart?

2. What is the maximum number of categories you should display in a pie chart?

3. How do you add percentage labels to a pie chart?

4. What is a donut chart?

5. Why are pie charts often criticised?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using too many slices – unreadable | Limit to 5 categories; group the rest as "Other" |
| Using 3D effects – distorts perception | Keep pie charts 2D |
| Not sorting slices – hard to compare | Sort slices from largest to smallest |
| Not labelling percentages – users can't see values | Always add percentage labels |
| Using pie charts for time‑series or comparisons – bar charts are better | Use pie charts only for composition |

---

### Interview Questions

1. **When would you use a pie chart vs a bar chart?**  

   *Answer*: A pie chart is used for showing part‑to‑whole relationships when you have few categories. A bar chart is better for comparing individual categories and handling many categories.

2. **What is a donut chart and why is it used?**  

   *Answer*: A donut chart is a pie chart with a hole in the centre. It is often used for aesthetic reasons and can sometimes make the proportions easier to read.

3. **How do you add percentage labels to a pie chart?**  

   *Answer*: Drag the measure to Label, then right‑click and select **Quick Table Calculation** → **Percent of Total**.

---

### Assignment and Dashboard Projects

**Assignment 4.5** – Create a dashboard with pie/donut charts:

- A pie chart showing Sales by Category with percentage labels.

- A donut chart showing Sales by Region.

- A pie chart showing Profit by Segment.

- Format all charts consistently.


---

### Summary and Revision Notes

- Pie charts show composition (part‑to‑whole).

- Limit to 5 categories.

- Always add percentage labels.

- Donut charts are a modern alternative.

- Avoid 3D effects.

---

## Lesson 4.6 – Scatter Plots

### Concept Explanation

**Scatter plots** display the relationship between two numeric variables. Each point on the chart represents a data point (e.g., a product, a customer, a store) with its position determined by its values on the X and Y axes.

**Key features**:

- **Correlation**: Positive, negative, or no correlation.

- **Outliers**: Points that are far from the general trend.

- **Clusters**: Groups of points that suggest segmentation.


**Variations**:

- **Bubble Chart**: Scatter plot where the size of the points represents a third variable.

- **Scatter Plot with Trend Line**: A regression line showing the trend.


**When to use scatter plots**:

- Exploring relationships between two variables.

- Identifying outliers.

- Finding clusters.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Scatter plots reveal relationships that are invisible in summary statistics. They are the go‑to chart for correlation analysis.

- **Use cases**:

  - A **retail analyst** plots advertising spend (X) vs revenue (Y) to see the relationship.

  - A **quality analyst** plots temperature (X) vs defect rate (Y) to find the optimal range.

  - A **marketing analyst** plots customer age (X) vs spending (Y) to segment customers.


---

### Step‑by‑Step Demonstration

**Basic Scatter Plot**:

1. Connect to Sample - Superstore.

2. Drag `Sales` to **Columns**.

3. Drag `Profit` to **Rows**.

4. Tableau creates a scatter plot of Profit vs Sales.

**Adding Detail**:

1. Drag `Category` to **Color** on the Marks Card – points are coloured by category.

2. Drag `Product Name` to **Detail** – each point represents a product.

**Bubble Chart**:

1. Drag `Sales` to **Columns**, `Profit` to **Rows**.

2. Drag `Profit` or `Sales` to **Size** on the Marks Card – points are sized by value.

**Adding a Trend Line**:

1. Right‑click on the chart → **Trend Lines** → **Show Trend Lines**.

2. Choose the trend line type (linear, logarithmic, exponential, etc.).

---

### Practical Examples

- **Example 1**: A scatter plot of Sales vs Profit helps identify products that are high‑sales but low‑profit (potential issues).

- **Example 2**: A bubble chart of Sales vs Profit with Profit on Size shows which products are the most profitable.

- **Example 3**: A scatter plot with a trend line shows the relationship between advertising spend and revenue.


---

### Hands‑on Exercises

1. Create a scatter plot of Sales vs Profit.

2. Add Category to Color.

3. Create a bubble chart by adding Profit to Size.

4. Add a trend line.

5. Identify the products with the highest profit and the lowest profit.

---

### Mini Quiz

1. What is the primary use of a scatter plot?

2. What does each point represent in a scatter plot?

3. How do you add a third variable to a scatter plot?

4. What is the purpose of a trend line?

5. What is a bubble chart?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using scatter plots with too many points – cluttered | Use transparency (Opacity) or a smaller sample |
| Not adding detail – points are meaningless without context | Add labels (hover) or use color/detail to identify points |
| Ignoring outliers – they may be errors or opportunities | Investigate outliers and decide if they should be removed or highlighted |
| Over‑interpreting correlation as causation | Remember that correlation does not imply causation |
| Not scaling axes correctly – distortion | Use the same scale for both axes if comparing distributions |

---

### Interview Questions

1. **When would you use a scatter plot?**  

   *Answer*: When you want to explore the relationship between two numeric variables, identify outliers, or find clusters.

2. **What is a bubble chart and how is it different from a scatter plot?**  

   *Answer*: A bubble chart is a scatter plot where the size of the points represents a third variable. A scatter plot uses only X and Y.

3. **How do you add a trend line to a scatter plot in Tableau?**  

   *Answer*: Right‑click on the chart, select **Trend Lines** → **Show Trend Lines**. You can then choose the type of trend line.

---

### Assignment and Dashboard Projects

**Assignment 4.6** – Create a scatter plot dashboard:

- A scatter plot of Sales vs Profit by Product.

- Color points by Category.

- Size points by Profit.

- Add a trend line.

- Identify and label the top 5 products by profit.

- Format the chart with clear axes and titles.

---

### Summary and Revision Notes

- Scatter plots show relationships between two numeric variables.

- Use Color, Detail, and Size for additional dimensions.

- Trend lines show the direction of the relationship.

- Bubble charts add a third variable via size.


---

## Lesson 4.7 – Maps

### Concept Explanation

**Maps** are visualisations that display data geographically. Tableau has powerful mapping capabilities, automatically recognising geographic fields (Country, State, City, Postal Code) and plotting them.

**Types of maps**:

| **Type** | **Description** | **Use Case** |
|----------|-----------------|--------------|
| **Symbol Map** | Points plotted on a map. | Showing store locations or sales by city. |
| **Filled Map** | Regions are shaded based on a measure. | Showing sales by country/state. |
| **Density Map** | Heatmap of data density. | Showing concentration of customers. |
| **Map with Paths** | Lines connecting points. | Showing routes or connections. |

**Requirements**:

- The field must have a **Geographic Role** (City, State, Country, etc.).

- Tableau uses a built‑in geocoding database.

**Customising Maps**:

- You can change the map style (light, dark, normal).

- You can add layers (terrain, roads, etc.).

---

### Importance and Real‑World Use Cases

- **Why it matters**: Geographic patterns are often invisible in tables or charts. Maps reveal regional trends, clusters, and outliers.

- **Use cases**:

  - A **retail chain** uses a map to show store sales by location, identifying underperforming regions.
  
  - A **logistics company** uses a map to plot delivery routes and identify delays.
  
  - A **marketing team** uses a map to show customer distribution and target specific areas.
  

---

### Step‑by‑Step Demonstration

**Symbol Map**:

1. Connect to Sample - Superstore.

2. Double‑click `Country` – Tableau creates a map.

3. Drag `Sales` to **Size** on the Marks Card – the size of the circles represents sales.

4. Drag `Profit` to **Color** – the colour of the circles represents profit.


**Filled Map**:

1. Double‑click `Country`.

2. On the Marks Card, change the mark type from **Automatic** to **Filled Map**.

3. Drag `Sales` to **Color** – the regions are shaded by sales.


**Adding More Geographic Detail**:

1. Drag `State` to **Detail** on the Marks Card – the map zooms in to the state level.

2. You can also use **City**, **Postal Code**, etc.


**Customising the Map**:

1. In the menu: **Map** → **Map Layers**.

2. Change the map style: **Map** → **Map Styles** → **Light**, **Dark**, **Normal**.


---

### Practical Examples

- **Example 1**: A symbol map showing sales by state helps identify high‑performing and low‑performing regions.

- **Example 2**: A filled map showing profit by country reveals which countries are most profitable.

- **Example 3**: A density map showing customer concentration helps target marketing campaigns.


---

### Hands‑on Exercises

1. Create a symbol map showing Sales by Country.

2. Create a filled map showing Sales by Country.

3. Add State to Detail and zoom in to the US map.

4. Drag Profit to Color to add another dimension.

5. Change the map style to Dark.

---

### Mini Quiz

1. What is required for a field to be used on a map?

2. What is the difference between a symbol map and a filled map?

3. How do you add more geographic detail (e.g., states) to a map?

4. How do you change the map style in Tableau?

5. What is a density map used for?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using a map when the geographic pattern is not relevant | Only use maps when location is meaningful to the analysis |
| Not assigning the correct geographic role – map doesn't work | Ensure geographic fields have the correct role assigned |
| Using too many points – cluttered | Use clustering or aggregation |
| Not using colour effectively – hard to distinguish | Use intuitive colour schemes (e.g., green for high, red for low) |
| Forgetting to add tooltips – users can't see details | Add fields to Tooltip on the Marks Card |

---

### Interview Questions

1. **How does Tableau recognise geographic data?**  

   *Answer*: Tableau uses built‑in geocoding and the Geographic Role assigned to a field (e.g., City, State, Country). It maps the text to coordinates.

2. **What is the difference between a symbol map and a filled map?**  

   *Answer*: A symbol map uses points (circles) to represent data. A filled map shades geographic regions based on a measure.

3. **How can you customise a map in Tableau?**  

   *Answer*: You can change the map style (light, dark, normal), add map layers (terrain, roads), and use custom background images.

---

### Assignment and Dashboard Projects

**Assignment 4.7** – Create a map‑based dashboard:

- A symbol map showing Sales by Country, with Profit on Color.

- A filled map showing Sales by Country.

- A density map of Customer distribution (if you have Customer data).

- Add filters for Category and Region.

- Format the maps with clear legends.

---

### Summary and Revision Notes

- Maps display geographic data.

- Symbol maps use points; filled maps shade regions.

- Geographic roles must be assigned.

- Customise maps with styles and layers.


---

## Lesson 4.8 – Heat Maps, Tree Maps, Highlight Tables, and Bubble Charts

### Concept Explanation

These chart types are variations that excel at showing specific types of data:

1. **Heat Map** – A table where cells are coloured based on a measure. It's useful for quickly spotting patterns in large datasets.

2. **Tree Map** – A hierarchical chart where rectangles are sized and coloured by measures. It's excellent for showing part‑to‑whole relationships with many categories.

3. **Highlight Table** – A text table with conditional formatting (colour coding) applied to the values. It combines the detail of a table with the visual impact of a heat map.

4. **Bubble Chart** – A scatter plot where the size of the circles represents a measure. It's useful for showing three variables at once.

---

### Importance and Real‑World Use Cases

- **Why it matters**: These chart types add variety and depth to your visualisations, allowing you to present complex data in intuitive ways.

- **Use cases**:

  - A **financial analyst** uses a heat map to show profit by product and region.

  - A **product manager** uses a tree map to show market share by product sub‑category.

  - A **sales manager** uses a highlight table to show sales performance by sales rep and region.


---

### Step‑by‑Step Demonstration

**Heat Map**:

1. Drag `Category` to **Rows**.

2. Drag `Region` to **Columns**.

3. Drag `Sales` to **Color** on the Marks Card.

4. Change the mark type to **Square**.

5. Drag `Sales` to **Label** to show the values.


**Tree Map**:

1. Select **Show Me** → **Tree Map**.

2. Drag `Category` to **Color**.

3. Drag `Sales` to **Size**.

4. Drag `Product Name` to **Detail** for deeper hierarchy.


**Highlight Table**:

1. Create a text table (Category in Rows, Region in Columns, Sales in Text).

2. Drag `Sales` to **Color** on the Marks Card.

3. The table cells are now colour‑coded by sales value.


**Bubble Chart**:

1. Drag `Sales` to **Columns**, `Profit` to **Rows**.

2. Drag `Profit` to **Size**.

3. Drag `Category` to **Color**.

4. Drag `Product Name` to **Detail**.

---

### Practical Examples

- **Example 1**: A heat map showing sales by product category and region quickly reveals which combinations are performing well.

- **Example 2**: A tree map showing sales by product category helps visualise the relative contribution of each category.

- **Example 3**: A highlight table showing sales by sales rep and region helps identify top and bottom performers.


---

### Hands‑on Exercises

1. Create a heat map of Sales by Category and Region.

2. Create a tree map of Sales by Category and Sub‑Category.

3. Create a highlight table of Sales by Category and Region.

4. Create a bubble chart of Sales vs Profit, sized by Profit.


---

### Mini Quiz

1. What is the difference between a heat map and a highlight table?

2. When would you use a tree map?

3. What does a bubble chart show?

4. How do you create a tree map in Tableau?

5. What mark type is used for a heat map?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using a heat map with too many categories – hard to read | Limit to 10‑15 categories |
| Using a tree map with too many items – rectangles become tiny | Limit to 50‑100 items; drill down for details |
| Not adding labels to tree maps – users can't see values | Always add labels or tooltips |
| Using bubble charts with too many bubbles – cluttered | Limit to 50‑100 bubbles; use transparency |
| Using colour that is not intuitive | Use consistent colour schemes (e.g., blue‑green for positive, red for negative) |

---

### Interview Questions

1. **What is the difference between a heat map and a highlight table?**  

   *Answer*: A heat map uses coloured squares (or rectangles) where the colour intensity represents the value. A highlight table is a text table with conditional formatting (colour coding) applied to the text cells.

2. **When would you use a tree map instead of a pie chart?**  

   *Answer*: A tree map is better when you have many categories (more than 5) and want to show hierarchical data. It uses space more efficiently than a pie chart.

3. **What is a bubble chart and what does it show?**  

   *Answer*: A bubble chart is a scatter plot where the size of the points represents a third variable. It shows the relationship between two variables and the magnitude of a third.

---

### Assignment and Dashboard Projects

**Assignment 4.8** – Create a dashboard with:

- A heat map of Sales by Category and Region.

- A tree map of Sales by Category and Sub‑Category.

- A highlight table of Sales by Segment and Region.

- A bubble chart of Sales vs Profit, sized by Profit, coloured by Category.

- Format all charts consistently and add titles.


---

### Summary and Revision Notes

- **Heat Map**: colour‑coded table (squares).

- **Tree Map**: hierarchical, sized rectangles.

- **Highlight Table**: colour‑coded text table.

- **Bubble Chart**: scatter plot with size representing a third variable.


---

## Lesson 4.9 – Dual Axis Charts and Combined Charts

### Concept Explanation

**Dual Axis Charts** allow you to combine two different chart types or measures on a single view, using two separate axes. This is extremely useful for comparing two measures that have different scales or types.

**Combined Charts** are a broader category that includes:

- **Dual Axis**: two measures with different axes.

- **Combo Chart**: a combination of bar and line chart (e.g., bars for sales, line for profit margin).

- **Synchronised Dual Axis**: where both axes share the same scale.


**When to use dual axis**:

- Comparing a volume measure (e.g., sales) with a percentage measure (e.g., profit margin).

- Comparing two measures with different units (e.g., revenue and count).

- Combining a bar chart with a line chart for visual variety.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Many business questions require comparing two different types of data. Dual axis charts allow you to see both in a single view.

- **Use cases**:

  - A **sales dashboard** shows sales (bars) and profit margin (line) over time.

  - A **marketing dashboard** shows clicks (bars) and conversion rate (line).

  - A **financial dashboard** shows revenue (bars) and growth rate (line).


---

### Step‑by‑Step Demonstration

**Basic Dual Axis**:

1. Connect to Sample - Superstore.

2. Drag `Order Date` to **Columns**.

3. Drag `Sales` to **Rows**.

4. Drag `Profit Ratio` (a calculated field: `SUM([Profit]) / SUM([Sales])`) to the **right side** of the Rows shelf.

5. Right‑click on the Profit Ratio axis → **Dual Axis**.

6. You now have a dual‑axis chart.


**Combined Chart (Bar + Line)**:

1. Follow the steps above.

2. On the Marks Card, you'll see two marks layers: one for SUM(Sales) and one for Profit Ratio.

3. Change the mark type for Profit Ratio to **Line**.

4. Change the mark type for SUM(Sales) to **Bar**.

5. Format each axis and synchronise if needed.


**Synchronising Axes**:

1. Right‑click on the secondary axis → **Synchronize Axis**.

2. This aligns the two axes if they share the same range.

---

### Practical Examples

- **Example 1**: A dual‑axis chart showing Sales (bars) and Profit Margin % (line) over time helps see how profitability changes with sales volume.

- **Example 2**: A dual‑axis chart showing Orders (bars) and Average Order Value (line) helps understand the relationship between volume and value.

- **Example 3**: A combo chart showing Revenue (bars) and Growth Rate (line) is common in executive dashboards.


---

### Hands‑on Exercises

1. Create a dual‑axis chart with Sales on one axis and Profit on the other.

2. Change Sales to bars and Profit to a line.

3. Synchronise the axes.

4. Add Category to Color on both marks layers.

5. Format the axes, colours, and labels.


---

### Mini Quiz

1. What is a dual‑axis chart?

2. When would you use a dual‑axis chart?

3. What is the difference between a dual‑axis chart and a combined chart?

4. How do you synchronise axes in a dual‑axis chart?

5. What is a combo chart?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using dual‑axis charts unnecessarily – they can confuse | Only use dual‑axis when the measures have different scales or types |
| Not synchronising axes – misleading comparisons | Synchronise axes when the measures are on the same scale |
| Overcomplicating with too many marks layers – cluttered | Limit to two marks layers; keep it simple |
| Not labelling axes clearly – users don't know what they're looking at | Always add clear axis labels and legends |
| Using dual‑axis charts for time series with different granularities – misalignment | Ensure both measures have the same date granularity |

---

### Interview Questions

1. **What is a dual‑axis chart and when would you use it?**  

   *Answer*: A dual‑axis chart combines two measures on a single view using two separate axes. It is used when comparing two measures with different scales or units, such as sales (bars) and profit margin (line).

2. **How do you create a dual‑axis chart in Tableau?**  

   *Answer*: Drag two measures to Rows, then right‑click on one axis and select Dual Axis. You can then synchronise the axes if they share the same scale.

3. **What is the advantage of a combined chart (bar + line) over separate charts?**  

   *Answer*: A combined chart allows you to see the relationship between two measures in a single view, making it easier to spot correlations (e.g., high sales with low margin).

---

### Assignment and Dashboard Projects

**Assignment 4.9** – Create a dashboard with dual‑axis charts:

- A dual‑axis chart showing Sales (bars) and Profit Margin % (line) over time.

- A dual‑axis chart showing Quantity (bars) and Average Price (line) over time.

- Add filters for Category and Region.

- Synchronise the axes where appropriate.

- Format the charts with clear titles and legends.


---

### Summary and Revision Notes

- Dual‑axis charts combine two measures with separate axes.

- Use when measures have different scales or types.

- Synchronise axes when they share the same scale.

- Combo charts (bar + line) are a common use case.

---

## Final Phase 4 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can create tables and crosstabs.

-  I can create bar charts (vertical, horizontal, stacked, side‑by‑side).

-  I can create line charts (single, multiple, dual‑axis).

-  I can create area charts (simple, stacked, 100% stacked).

-  I can create pie charts and donut charts.

-  I can create scatter plots and bubble charts.

-  I can create maps (symbol, filled).

-  I can create heat maps, tree maps, and highlight tables.

-  I can create dual‑axis and combined charts.

-  I understand when to use each chart type.

---

### Answers to Mini Quizzes

**Lesson 4.1**: 1. Text table = simple grid; Crosstab = pivot‑table style. 2. Analysis → Totals → Grand Totals. 3. Format menu. 4. For detailed data, exact numbers. 5. Yes, via the export option.

**Lesson 4.2**: 1. When category names are long. 2. Stacked shows composition; side‑by‑side compares totals. 3. Click the sort icon on the axis. 4. Add a table calculation for Percent of Total. 5. Bar.

**Lesson 4.3**: 1. Showing trends over time. 2. Drag a dimension to Color. 3. Click the drop‑down on the date field. 4. Area chart fills the area below the line. 5. When measures have different scales.

**Lesson 4.4**: 1. Area chart fills the area below the line. 2. Showing composition over time. 3. Showing proportional change. 4. Change mark type to Area. 5. To emphasise magnitude.

**Lesson 4.5**: 1. For part‑to‑whole with few categories. 2. 5 categories. 3. Drag the measure to Label and set to Percent of Total. 4. Pie chart with a hole. 5. They are hard to compare angles.

**Lesson 4.6**: 1. Exploring relationships between two variables. 2. A data point (e.g., product, customer). 3. Add to Color, Size, or Detail. 4. To show the direction of the relationship. 5. Scatter plot with size representing a third variable.

**Lesson 4.7**: 1. A Geographic Role. 2. Symbol map uses points; filled map shades regions. 3. Drag the geographic field to Detail. 4. Map → Map Layers. 5. Showing concentration of data.

**Lesson 4.8**: 1. Heat map = coloured squares; Highlight table = coloured text. 2. For hierarchical part‑to‑whole with many categories. 3. Relationship between two variables and magnitude of a third. 4. Show Me → Tree Map. 5. Square.

**Lesson 4.9**: 1. Two measures with separate axes. 2. When measures have different scales. 3. Dual‑axis = separate axes; combined = specific combo (e.g., bar + line). 4. Right‑click on axis → Synchronize Axis. 5. Combination of bar and line chart.

---

**Congratulations!** You have completed Phase 4. You now have a deep understanding of Tableau's visualisation capabilities – from simple tables to sophisticated dual‑axis charts. Keep practising!


---








<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>
