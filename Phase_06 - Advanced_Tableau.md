# Phase 6: Advanced Tableau

Welcome to **Phase 6** – the final frontier of your Tableau journey! You have come a long way: from connecting to data and preparing it, to building stunning visualisations, to creating interactive dashboards. Now, we dive into the **advanced** techniques that separate Tableau users from Tableau experts.

This phase covers sophisticated calculations, powerful interactivity with Set Actions and Parameter Actions, performance optimization, and an introduction to Tableau Prep. These skills are essential for handling complex business problems, building enterprise‑grade dashboards, and impressing in interviews.

Let's take your Tableau skills to the next level!

---

## Lesson 6.1 – Advanced Calculated Fields

### Concept Explanation

You already know how to create basic calculated fields. Now, we will explore advanced patterns that solve complex business problems.

**Advanced calculation patterns**:

1. **Conditional Aggregations** – using `IF` or `CASE` inside aggregations.

   - Example: `SUM(IF [Category] = "Furniture" THEN [Sales] END)` – sums only furniture sales.

2. **Running Calculations** – using `WINDOW_SUM`, `WINDOW_AVG`, etc. (though these are table calculations, we cover them here as calculated fields that reference other fields).

3. **Ranking** – using `RANK` or `RANK_UNIQUE` within a calculated field (though they are often used as table calculations).

4. **Date Truncation** – `DATETRUNC('month', [Date])` to group by month, quarter, etc.

5. **Parsing Strings** – using `FIND`, `LEFT`, `RIGHT`, `MID`, `SPLIT` to extract information from text.

6. **Parameterised Calculations** – using parameters in calculated fields (covered in Phase 5).

**Advanced `IF` patterns**:

- `IF [Sales] > 1000 AND [Profit] > 0 THEN "Profitable High" ELSE "Other" END`

- `COUNT(IF [Order Date] >= TODAY() - 30 THEN [Order ID] END)` – counts orders in the last 30 days.

**`CASE` with multiple conditions** (using `TRUE`):
```
CASE TRUE
WHEN [Sales] > 5000 THEN "High"
WHEN [Sales] > 1000 THEN "Medium"
ELSE "Low"
END
```

---

### Importance and Real‑World Use Cases

- **Why it matters**: Advanced calculated fields allow you to implement complex business logic directly in Tableau, reducing the need for preprocessing in ETL tools.

- **Use cases**:

  - A **financial analyst** calculates `IF [Profit] > 0 THEN [Profit] ELSE 0 END` to show only positive profits.

  - A **marketing analyst** calculates `COUNT(IF [Campaign] = "Email" THEN [Leads] END)` to count leads from email campaigns.

  - A **sales analyst** calculates `SUM(IF [Region] = "West" THEN [Sales] END)` to get West region sales.


---

### Step‑by‑Step Demonstration

**Conditional Aggregation**:

1. Connect to Sample - Superstore.

2. Create a calculated field: `Furniture Sales = SUM(IF [Category] = "Furniture" THEN [Sales] END)`.

3. Drag it to a view – it shows only furniture sales.


**Multiple Conditions**:

1. Create `Sales Tier = IF [Sales] > 5000 THEN "High" ELSEIF [Sales] > 1000 THEN "Medium" ELSE "Low" END`.

**Date-Based Calculation**:

1. `Orders Last 30 Days = COUNT(IF [Order Date] >= TODAY() - 30 THEN [Order ID] END)`.

**Using `CASE` with `TRUE`**:
```
CASE TRUE
WHEN [Sales] > 5000 THEN "High"
WHEN [Sales] > 1000 THEN "Medium"
ELSE "Low"
END
```

---

### Practical Examples

- **Example 1**: `SUM(IF [Category] = "Furniture" AND [Region] = "West" THEN [Sales] END)` – furniture sales in the West region.

- **Example 2**: `AVG(IF [Order Date] >= DATE('2025-01-01') THEN [Sales] END)` – average sales since 2025.

- **Example 3**: `COUNTD(IF [Profit] > 0 THEN [Customer ID] END)` – number of profitable customers.


---

### Hands‑on Exercises

1. Create a calculated field `Furniture Sales` using `SUM(IF ...)`.

2. Create `Sales Tier` using `IF ELSEIF`.

3. Create `Orders in 2025` using `COUNT(IF YEAR([Order Date]) = 2025 THEN [Order ID] END)`.

4. Create `Profit Tier` using `CASE TRUE`.

5. Place these fields in a worksheet to verify they work.


---

### Mini Quiz

1. How do you sum only sales for a specific category?

2. What is the difference between `IF` and `CASE`?

3. How do you use `CASE` with `TRUE` for multiple conditions?

4. Write a calculated field that counts orders from the last 30 days.

5. How do you count distinct customers with profit > 0?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Forgetting the `END` in `IF` statements | Always close `IF` with `END` |
| Using aggregations inside non‑aggregated fields – syntax errors | Ensure all fields in a calculation are either aggregated or non‑aggregated |
| Over‑complicating calculations – hard to maintain | Break complex logic into multiple calculated fields |
| Not testing calculations with sample data | Test with a few rows to verify logic |

---

### Interview Questions

1. **How would you calculate the percentage of sales from a specific category?**  

   *Answer*: `SUM(IF [Category] = "Furniture" THEN [Sales] END) / SUM([Sales])`. Format as a percentage.

2. **What is the difference between `IF` and `IIF`?**  

   *Answer*: `IF` supports multiple conditions and must end with `END`. `IIF` is a shorthand for simple true/false conditions.

3. **How do you handle null values in a calculated field?**  

   *Answer*: Use `ZN()` to convert null to 0, or `IFNULL()` to replace with a default value.

---

### Assignment and Dashboard Projects

**Assignment 6.1** – Create a worksheet that demonstrates advanced calculated fields:

- `Furniture Sales`.

- `Sales Tier` (High, Medium, Low).

- `Orders in 2025`.

- `Average Profit per Order` (handle nulls with `ZN`).

- Add these fields to a view and verify they work correctly.

---

### Summary and Revision Notes

- Conditional aggregations: `SUM(IF ... THEN ... END)`.

- Multiple conditions: `IF ... ELSEIF ... END`.

- `CASE TRUE` for complex conditions.

- Use `ZN` and `IFNULL` for null handling.

---

## Lesson 6.2 – Advanced LOD Expressions

### Concept Explanation

You learned the basics of LOD expressions in Phase 3 (`FIXED`, `INCLUDE`, `EXCLUDE`). Now we dive deeper into advanced patterns.

**Advanced LOD patterns**:

1. **Nested LODs** – using LOD expressions inside other LOD expressions.

   - Example: `{ FIXED [Customer ID] : AVG({ FIXED [Order ID] : SUM([Sales]) }) }` – average sales per customer.

2. **LOD with Filters** – using LOD expressions to compute values that are not affected by certain filters.

   - Example: `{ FIXED [Category] : SUM([Sales]) }` – total sales per category, ignoring other filters.

3. **LOD with Table Calculations** – combining LODs with table calculations for complex analysis.

4. **LOD for Cohort Analysis** – using `FIXED` to compute cohort‑level metrics.

**Common LOD use cases**:

- **Percent of Total**: `SUM([Sales]) / { FIXED : SUM([Sales]) }`.

- **Average Customer Spend**: `{ FIXED [Customer ID] : SUM([Sales]) }` – then average it.

- **Running Total per Category**: `{ FIXED [Category], [Order Date] : SUM([Sales]) }` – then table calculation.


---

### Importance and Real‑World Use Cases

- **Why it matters**: LOD expressions are the most powerful feature in Tableau for complex aggregations. They solve problems that cannot be solved with table calculations or basic aggregations.

- **Use cases**:

  - A **financial analyst** calculates `SUM([Sales]) / { FIXED : SUM([Sales]) }` for percent of total.
  
  - A **customer analyst** calculates `AVG({ FIXED [Customer ID] : SUM([Sales]) })` for average customer lifetime value.
  
  - A **supply chain analyst** calculates `{ FIXED [Product ID] : AVG([Inventory Days]) }` – average inventory days per product.
  

---

### Step‑by‑Step Demonstration

**Percent of Total**:

1. Create `Total Sales Overall = { FIXED : SUM([Sales]) }`.

2. Create `% of Total = SUM([Sales]) / [Total Sales Overall]`.


**Average Customer Lifetime Value**:

1. Create `Customer LTV = { FIXED [Customer ID] : SUM([Sales]) }`.

2. Create `Avg LTV = AVG([Customer LTV])`.


**LOD with Filters**:

1. `Category Sales = { FIXED [Category] : SUM([Sales]) }` – this gives the total sales per category, ignoring region filters.


**Nested LOD**:

1. `Avg Order Value per Customer = { FIXED [Customer ID] : AVG({ FIXED [Order ID] : SUM([Sales]) }) }`.


---

### Practical Examples

- **Example 1**: `{ FIXED [Region] : SUM([Sales]) } / { FIXED : SUM([Sales]) }` – regional share of total sales.

- **Example 2**: `{ FIXED [Customer ID] : AVG([Profit]) }` – average profit per customer.

- **Example 3**: `{ FIXED [Category], [Order Date] : SUM([Sales]) }` – sales per category and date, used in a running total.


---

### Hands‑on Exercises

1. Create `Total Sales Overall` using `{ FIXED : SUM([Sales]) }`.

2. Create `% of Total` using `SUM([Sales]) / [Total Sales Overall]`.

3. Create `Customer LTV` using `{ FIXED [Customer ID] : SUM([Sales]) }`.

4. Create `Avg LTV` using `AVG([Customer LTV])`.

5. Create `Category Sales` using `{ FIXED [Category] : SUM([Sales]) }`.

6. Place these in a view and verify the results.


---

### Mini Quiz

1. What is the difference between `FIXED` and `INCLUDE` in LOD expressions?

2. How do you calculate the percent of total using LOD?

3. How do you calculate average customer spend using LOD?

4. What is a nested LOD expression?

5. How does a `FIXED` LOD interact with filters?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Forgetting the aggregation inside LOD – e.g., `{ FIXED [Category] : [Sales] }` is wrong | Always use an aggregation: `{ FIXED [Category] : SUM([Sales]) }` |
| Using LODs when a table calculation would be simpler | Use LOD for fixed‑level calculations; table calculations for relative calculations |
| Not understanding filter interaction – `FIXED` ignores dimension filters | Use `INCLUDE` if you want filters to affect the calculation |
| Over‑complicating with nested LODs | Keep LODs simple; sometimes two steps are easier |

---

### Interview Questions

1. **What is an LOD expression and when would you use it?**  

   *Answer*: An LOD expression allows you to compute aggregations at a different granularity than the view's level. I use it for percent of total, average customer spend, and cohort analysis.

2. **What is the difference between `FIXED` and `INCLUDE`?**  

   *Answer*: `FIXED` computes at the specified dimension(s) regardless of the view's dimensions. `INCLUDE` adds the specified dimension(s) to the view's level of detail.

3. **How would you calculate the average order value per customer using LOD?**  

   *Answer*: `AVG({ FIXED [Customer ID] : SUM([Sales]) })` – this gives the average customer spend.

---

### Assignment and Dashboard Projects

**Assignment 6.2** – Create a dashboard demonstrating advanced LOD expressions:

- Percent of total sales by category.

- Average customer lifetime value.

- Average order value per customer.

- Category sales (ignoring region filters).

- Add these to a dashboard and document each LOD.

---

### Summary and Revision Notes

- LOD expressions compute at different granularities.

- `FIXED` – fixed dimensions, ignores view filters.

- `INCLUDE` – adds dimensions to the view level.

- `EXCLUDE` – removes dimensions from the view level.

- Always use an aggregation inside LOD.

---

## Lesson 6.3 – Advanced Table Calculations

### Concept Explanation

Table calculations are computed on the aggregated result set of a view. Advanced table calculations allow you to perform complex post‑aggregation analysis.

**Advanced table calculation patterns**:

1. **Running Total with Reset** – using `WINDOW_SUM` with `PARTITION` to reset running totals.

2. **Moving Average** – using `WINDOW_AVG` with a custom window.

3. **Percent of Total with Multiple Dimensions** – using `TOTAL` and `SECONDARY` calculations.

4. **Ranking with Dense Rank** – using `RANK_DENSE` to avoid gaps.

5. **Difference from Average** – comparing each value to the overall average.

6. **Custom Sorting** – using table calculations to sort by a derived field.


**Key functions for advanced table calculations**:

- `WINDOW_SUM(sum, start, end)` – calculates a moving sum.

- `WINDOW_AVG(sum, start, end)` – calculates a moving average.

- `RANK(expression, 'asc'|'desc')` – ranks values.

- `RANK_DENSE(expression)` – ranks without gaps.

- `TOTAL(expression)` – total across the table.

- `PREVIOUS_VALUE(expression)` – previous value in the partition.

- `FIRST()` / `LAST()` – returns the index of the first/last row.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Table calculations are essential for comparing values, computing running totals, and creating rankings. Advanced table calculations allow you to handle complex scenarios like moving averages and cumulative totals with resets.

- **Use cases**:

  - A **financial analyst** calculates a 3‑month moving average of sales.
  
  - A **sales manager** ranks products by sales using `RANK_DENSE`.
  
  - A **marketing analyst** calculates the difference from the average campaign performance.

---

### Step‑by‑Step Demonstration

**Running Total with Reset**:

1. Drag `Order Date` (month) to Columns, `SUM(Sales)` to Rows.

2. Right‑click `SUM(Sales)` → **Add Table Calculation**.

3. Choose **Running Total**.

4. Under **Compute Using**, select **Table (across)**.

5. To reset by year, add `YEAR([Order Date])` to the view and set the calculation to **Table (down)** with reset.


**Moving Average**:

1. Create a calculated field `Moving Avg = WINDOW_AVG(SUM([Sales]), -2, 0)` – 3‑month moving average.

2. Place it on the view.


**Ranking with Dense Rank**:

1. `Rank = RANK_DENSE(SUM([Sales]))`.


**Percent of Total with Multiple Dimensions**:

1. Right‑click `SUM(Sales)` → **Add Table Calculation** → **Percent of Total**.

2. Configure to compute across categories and regions.

---

### Practical Examples

- **Example 1**: `WINDOW_AVG(SUM([Sales]), -2, 0)` – 3‑month moving average.

- **Example 2**: `RANK_DENSE(SUM([Sales]))` – dense ranking of products by sales.

- **Example 3**: `SUM([Sales]) / TOTAL(SUM([Sales]))` – percent of total.


---

### Hands‑on Exercises

1. Create a running total of sales by month.

2. Create a 3‑month moving average of sales.

3. Create a dense ranking of products by sales.

4. Create a percent of total by category.

5. Compare the running total with the moving average.

---

### Mini Quiz

1. What is the difference between `RANK` and `RANK_DENSE`?

2. What does `WINDOW_AVG(-2, 0)` calculate?

3. How do you reset a running total by year?

4. What does `TOTAL(expression)` do?

5. How do you calculate the difference from the average?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not understanding the compute direction – wrong results | Understand the layout and choose the correct compute direction |
| Using table calculations for row‑level logic | Use calculated fields for row‑level logic; table calculations for post‑aggregation |
| Forgetting to set the scope – calculations may not reset correctly | Set the correct scope (Table, Pane, Cell) |
| Over‑complicating with multiple nested table calculations | Keep table calculations simple; break into multiple steps if needed |

---

### Interview Questions

1. **What is a table calculation and how is it different from a calculated field?**  

   *Answer*: A table calculation is computed on the aggregated result set of a view. A calculated field is computed row‑by‑row at the data source level. Table calculations are not stored; they are computed each time the view is rendered.

2. **How would you calculate a 3‑month moving average in Tableau?**  

   *Answer*: Using `WINDOW_AVG(SUM([Sales]), -2, 0)` – this averages the current month and the two previous months.

3. **What is the difference between `RANK` and `RANK_DENSE`?**  

   *Answer*: `RANK` skips numbers when there are ties (e.g., 1, 2, 2, 4). `RANK_DENSE` does not skip numbers (1, 2, 2, 3).

---

### Assignment and Dashboard Projects

**Assignment 6.3** – Create a dashboard demonstrating advanced table calculations:

- Running total of sales by month.

- 3‑month moving average.

- Dense ranking of products by sales.

- Percent of total by category.

- Add these to a dashboard and document each calculation.


---

### Summary and Revision Notes

- Table calculations are post‑aggregation.

- `WINDOW_AVG` for moving averages.

- `RANK_DENSE` for rankings without gaps.

- `TOTAL` for percent of total.

- Use compute direction and scope correctly.

---

## Lesson 6.4 – Set Actions

### Concept Explanation

**Sets** are custom groups of data based on conditions. **Set Actions** allow users to interact with sets by clicking on data points, dynamically adding or removing members from the set.

**What is a Set?**

- A set is a defined subset of data (e.g., "Top 10 Products", "Customers in the West").

- Sets can be used to filter, highlight, or compare.


**Types of Sets**:

- **Static Set** – fixed based on a condition or selection.

- **Dynamic Set** – updates based on data changes (e.g., top N).


**Set Actions**:

- Allow users to add/remove members from a set by clicking on a chart.

- Triggered by selecting data points.

- Can be used for interactive filtering and highlighting.


**Use Cases for Set Actions**:

- Interactive selection: Click on products to add them to a "Compare" set.

- Dynamic filtering: Click on regions to include them in a set.

- What‑if analysis: Build a set of selected items for comparison.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Set Actions enable powerful interactivity, allowing users to build custom selections on the fly and compare them with the rest of the data.

- **Use cases**:

  - A **sales manager** clicks on products in a bar chart to create a "Selected Products" set, then compares their performance with all other products.
  
  - A **marketing analyst** selects campaigns from a scatter plot to create a "High Performance" set, then analyses their characteristics.
  
  - A **customer analyst** selects customers from a table to create a "VIP" set, then tracks their behaviour.
  

---

### Step‑by‑Step Demonstration

**Creating a Set**:

1. In the Data pane, right‑click a dimension (e.g., `Product Name`) → **Create** → **Set**.

2. In the Set dialog, choose **Use all** or **By field**.

3. For a dynamic set, choose **Top** and set the number (e.g., Top 10 by Sales).

4. Click **OK**.


**Using a Set in a View**:

1. Drag the set to the view (e.g., to Color).

2. The set creates two groups: "In Set" and "Not in Set".


**Creating a Set Action**:

1. On a dashboard, go to **Dashboard** → **Actions**.

2. Click **Add Action** → **Change Set Values**.

3. Source Sheet: Select the worksheet where the user will click.

4. Target Set: Select the set to change.

5. Action: **Select** (click) or **Hover**.

6. Configuration: Choose **Add, Remove, or Toggle**.

7. Click **OK**.


**Example: Compare Selected vs Others**:

1. Create a set of products.

2. Drag the set to Color – you see "In Set" and "Not in Set".

3. Add a Set Action so that clicking a product adds it to the set.

4. Users can now click products to compare them.

---

### Practical Examples

- **Example 1**: A dashboard where users click on regions on a map to build a "Selected Regions" set, and a bar chart shows sales for selected regions vs others.

- **Example 2**: A dashboard where users click on products in a bar chart to add them to a "Compare" set, and a table shows their details.


---

### Hands‑on Exercises

1. Create a set of products (Top 10 by Sales).

2. Drag the set to Color on a bar chart.

3. Create a Set Action so clicking a product adds it to the set.

4. Add another chart that shows sales for the set vs others.

5. Test the Set Action.


---

### Mini Quiz

1. What is a set in Tableau?

2. What is a Set Action?

3. How do you create a set?

4. How do you use a set in a view?

5. What are the possible actions for a Set Action?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using sets for static selections – sets are more powerful for dynamic interaction | Use sets with Set Actions for interactive analysis |
| Not testing Set Actions – they may not work as expected | Test all interactions thoroughly |
| Over‑complicating with multiple sets | Start with one set and build up |
| Forgetting to add visual feedback – users don't know they've selected | Use colour coding or text to show selection status |

---

### Interview Questions

1. **What is a Set Action in Tableau?**  

   *Answer*: A Set Action allows users to interact with a set by clicking on data points, dynamically adding or removing members from the set. It enables interactive comparisons and selections.

2. **How would you create a dashboard where users can select products to compare?**  

   *Answer*: I would create a set of products, use Set Actions so that clicking on a product adds it to the set, and then use the set in a view to compare selected vs others.

3. **What is the difference between a set and a filter?**  

   *Answer*: A filter limits the data displayed. A set is a defined subset of data that can be used in calculations, comparisons, and actions.

---

### Assignment and Dashboard Projects

**Assignment 6.4** – Create a dashboard with Set Actions:

- A bar chart of products by sales.

- A set of products.

- A Set Action so clicking a product adds it to the set.

- Another chart showing sales for the selected set vs others.

- Add visual feedback (colour coding).

---

### Summary and Revision Notes

- Sets are custom subsets of data.

- Set Actions allow interactive adding/removing of set members.

- Use sets in views with Color, Size, or Filters.

- Great for "compare selected vs others" analysis.

---

## Lesson 6.5 – Parameter Actions

### Concept Explanation

**Parameter Actions** allow users to interact with parameters by clicking on data points. This is the next level of interactivity – users can select values from a chart to change the value of a parameter.

**What is a Parameter Action?**

- An action that updates a parameter value based on a user's selection.

- The parameter can then be used in calculations, filters, or titles.


**How it works**:

- User clicks on a data point in a source worksheet.

- Tableau passes the value of a field to the parameter.

- The parameter updates, and any views that reference the parameter update.


**Use Cases for Parameter Actions**:

- Dynamic measure switching (click to change the metric).

- Dynamic filtering (click on a region to set a parameter, then use it to filter).

- Dynamic titles (click to update the title).


---

### Importance and Real‑World Use Cases

- **Why it matters**: Parameter Actions make dashboards incredibly dynamic and user‑friendly. Users can click on elements to change what they see, without using dropdowns or sliders.

- **Use cases**:

  - A **sales dashboard**: Click on a product in a bar chart to set a "Selected Product" parameter, which updates all views.

  - A **financial dashboard**: Click on a region in a map to set a "Selected Region" parameter, which updates the P&L view.

  - A **marketing dashboard**: Click on a campaign to set a "Selected Campaign" parameter, which updates the performance view.


---

### Step‑by‑Step Demonstration

**Creating a Parameter Action**:

1. Create a parameter: `Selected Product` (String).

2. Create a calculated field that uses the parameter: `Product Filter = [Product Name] = [Selected Product]`.

3. Drag `Product Filter` to the Filters shelf to filter the view.

4. On a dashboard, go to **Dashboard** → **Actions**.

5. Click **Add Action** → **Change Parameter**.

6. Source Sheet: Select the worksheet where the user will click.

7. Target Parameter: Select `Selected Product`.

8. Field: Select `Product Name` (the field to pass to the parameter).

9. Action: **Select** (click).

10. Click **OK**.


**Testing the Action**:

- Click on a product in the source chart.
- The parameter updates, and the view filters to that product.

**Dynamic Measure Switching**:

1. Create a parameter `Metric` (string, list: "Sales", "Profit", "Quantity").

2. Create a calculated field `Dynamic Measure = CASE [Metric] WHEN "Sales" THEN SUM([Sales]) ... END`.

3. Create a Parameter Action on a chart that updates the `Metric` parameter.

4. Users can click on chart elements to switch the measure.

---

### Practical Examples

- **Example 1**: A dashboard with a bar chart of products. Clicking a product sets a parameter that filters a detailed table.

- **Example 2**: A dashboard with a scatter plot. Clicking a point sets a parameter that updates a title.

- **Example 3**: A dashboard with buttons (text objects) that set a parameter to switch between views.


---

### Hands‑on Exercises

1. Create a parameter `Selected Product` (String).

2. Create a calculated field `Product Filter = [Product Name] = [Selected Product]`.

3. Add `Product Filter` to the Filters shelf.

4. Create a bar chart of products.

5. Add a Parameter Action so clicking a product updates `Selected Product`.

6. Test the action.

7. Create a `Metric` parameter and a dynamic measure, then add a Parameter Action to switch measures.


---

### Mini Quiz

1. What is a Parameter Action?

2. How do you create a Parameter Action?

3. How do you use a parameter in a filter?

4. What is the difference between a Parameter Action and a Set Action?

5. How can you use a Parameter Action for dynamic titles?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not using the parameter in a calculation or filter – it does nothing | Always use the parameter in a calculation, filter, or title |
| Creating too many Parameter Actions – confusing | Use Parameter Actions sparingly for key interactions |
| Forgetting to set a default value – parameter may be blank | Set a meaningful default value |
| Not testing the action – it may not work | Test all interactions thoroughly |

---

### Interview Questions

1. **What is a Parameter Action in Tableau?**  

   *Answer*: A Parameter Action allows users to click on a data point to update a parameter value. The parameter can then be used in calculations, filters, or titles, making the dashboard highly interactive.

2. **How would you create a dashboard where clicking on a product sets a parameter that filters a table?**  

   *Answer*: I would create a parameter `Selected Product`, a calculated field that filters based on the parameter, and a Parameter Action on the product chart that updates the parameter.

3. **What is the difference between a Parameter Action and a Filter Action?**  

   *Answer*: A Filter Action updates the data displayed in target sheets. A Parameter Action updates a parameter value, which can then be used in calculations, filters, or titles.

---

### Assignment and Dashboard Projects

**Assignment 6.5** – Create a dashboard with Parameter Actions:

- A parameter `Selected Product`.

- A filter that uses the parameter.

- A chart where clicking a product updates the parameter.

- A second chart that changes based on the parameter.

- A `Metric` parameter and a dynamic measure with a Parameter Action.


---

### Summary and Revision Notes

- Parameter Actions update parameter values via user clicks.

- Use parameters in calculations, filters, or titles.

- Great for dynamic filtering and measure switching.

- Combine with Set Actions for powerful interactivity.

---

## Lesson 6.6 – Dashboard Performance Optimization

### Concept Explanation

Performance is critical for dashboard adoption. Users will not wait for slow dashboards. This lesson covers techniques to speed up your Tableau dashboards.

**Key performance factors**:

1. **Data Volume**: The amount of data being processed.

2. **Complexity of Calculations**: Heavy calculations slow down rendering.

3. **Number of Marks**: More marks = slower rendering.

4. **Filters**: Complex filters can slow performance.

5. **Dashboard Layout**: Too many elements on one dashboard.

**Performance optimization techniques**:

1. **Use Extracts** – Extract data from the source for faster performance (instead of live connections).

2. **Aggregate Data** – Reduce the level of detail by aggregating data at the source.

3. **Limit Data** – Use filters to limit the data to what's needed (e.g., last 2 years).

4. **Simplify Calculations** – Avoid complex LODs and table calculations where possible.

5. **Reduce Marks** – Use aggregation to reduce the number of marks (e.g., group by category instead of product).

6. **Optimise Dashboard** – Limit the number of worksheets on one dashboard.

7. **Use Context Filters** – Apply context filters to reduce data before other calculations.


---

### Importance and Real‑World Use Cases

- **Why it matters**: A slow dashboard is a useless dashboard. Performance optimisation ensures users can interact with your dashboard without frustration.

- **Use cases**:

  - A **global sales dashboard** with millions of rows – using extracts and aggregations makes it usable.

  - A **real‑time operational dashboard** – optimising queries reduces refresh time.


---

### Step‑by‑Step Demonstration

**Creating an Extract**:

1. In the Data Source page, click **Extract**.

2. Choose **Edit** to set filters (e.g., only last 2 years).

3. Click **Extract**.


**Using Context Filters**:

1. Drag a filter to the Filters shelf.

2. Right‑click the filter → **Add to Context**.

3. This applies the filter before other calculations, reducing the data set early.


**Reducing Marks**:

1. Instead of displaying all products, group by category.

2. Use **Top N** filters to limit the number of marks.


**Optimising Dashboard**:

1. Use **Dashboard** → **Performance Recorder** to identify slow elements.

2. Remove or simplify slow elements.


---

### Practical Examples

- **Example 1**: A dashboard with 5 years of daily data (millions of rows). Using an extract with a filter for the last 2 years reduces data by 60%.

- **Example 2**: A dashboard with 20 worksheets – merging some into a single worksheet reduces rendering time.

---

### Hands‑on Exercises

1. Create an extract of Sample - Superstore with a filter for the last 2 years.

2. Add a context filter to reduce data before calculations.

3. Use the Performance Recorder to identify slow elements.

4. Simplify a complex calculation.

5. Compare the performance before and after optimisation.


---

### Mini Quiz

1. What is an extract in Tableau?

2. How do you create a context filter?

3. What is the Performance Recorder used for?

4. How can you reduce the number of marks in a view?

5. Why is data aggregation important for performance?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using live connections for large datasets – slow performance | Use extracts for large datasets |
| Not using context filters – calculations are applied to all data | Use context filters to reduce data early |
| Displaying too many marks – slow rendering | Aggregate data; use Top N filters |
| Ignoring performance issues – users complain | Use Performance Recorder to identify and fix issues |

---

### Interview Questions

1. **How do you optimise the performance of a Tableau dashboard?**  

   *Answer*: I use extracts for large datasets, apply context filters, aggregate data, limit the number of marks, simplify calculations, and use the Performance Recorder to identify bottlenecks.

2. **What is a context filter and why is it useful?**  

   *Answer*: A context filter is a filter that is applied before other calculations. It reduces the data set early, improving performance.

3. **What is the Performance Recorder and how do you use it?**  

   *Answer*: The Performance Recorder is a tool in Tableau that tracks the performance of a dashboard. It shows how long each element takes to render, helping identify slow components.

---

### Assignment and Dashboard Projects

**Assignment 6.6** – Optimise a dashboard:

- Create an extract of your dashboard's data source.

- Add context filters.

- Reduce the number of marks.

- Use the Performance Recorder to measure improvements.

- Document the changes and their impact.


---

### Summary and Revision Notes

- Performance is critical for user adoption.

- Use extracts, context filters, and data aggregation.

- Reduce marks and simplify calculations.

- Use Performance Recorder to identify bottlenecks.


---

## Lesson 6.7 – Data Source Optimization

### Concept Explanation

Data source optimisation focuses on improving the performance of the connection between Tableau and your data sources. This is different from dashboard performance (which is about rendering).

**Key techniques**:

1. **Use Data Extracts** – As covered, extracts are faster than live connections.

2. **Reduce Data at the Source** – Use SQL queries or data source filters to limit data.

3. **Use Data Source Filters** – Apply filters in the Data Source page to limit the data loaded.

4. **Optimise Joins** – Use joins carefully; unnecessary joins slow performance.

5. **Use Data Blending Sparingly** – Blends can be slow; use joins where possible.

6. **Use a Data Warehouse** – Pre‑aggregate data in a data warehouse for faster queries.


**Data Source Filters**:

- In the Data Source page, you can add filters to limit the data loaded into Tableau.

- These filters are applied at the data extraction stage, reducing the data set.


---

### Importance and Real‑World Use Cases

- **Why it matters**: The data source is the foundation of your dashboard. If the data source is slow, nothing else will be fast.

- **Use cases**:

  - A **global sales dashboard** – using a data warehouse with pre‑aggregated sales data speeds up queries.

  - A **financial dashboard** – using extracts reduces the load on the source database.


---

### Step‑by‑Step Demonstration

**Adding a Data Source Filter**:

1. In the Data Source page, click **Add** next to **Filters**.

2. Choose a field to filter (e.g., `Order Date`).

3. Set the filter (e.g., `Order Date >= 2020-01-01`).

4. Click **OK**.


**Using a Custom SQL Query**:

1. When connecting to a database, choose **Custom SQL**.

2. Write a SQL query that filters and aggregates data at the source.

   - Example: `SELECT Category, Region, SUM(Sales) FROM SalesTable GROUP BY Category, Region`
3. This reduces the data before it reaches Tableau.


---

### Practical Examples

- **Example 1**: A SQL query that only selects the last 2 years of data, reducing the data set by 80%.

- **Example 2**: A data source filter that limits the data to a specific region, reducing the data loaded.

---

### Hands‑on Exercises

1. Add a data source filter to Sample - Superstore to limit data to the last 2 years.

2. Write a custom SQL query (if you have a database) that aggregates sales by category and region.

3. Compare the performance with and without these optimisations.


---

### Mini Quiz

1. What is a data source filter?

2. How do you add a data source filter?

3. What is the advantage of using a custom SQL query?

4. Why is data blending slower than joins?

5. What is the purpose of a data warehouse in Tableau?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Loading all data into Tableau – slow performance | Use data source filters to limit data |
| Using data blending for large datasets – slow | Use joins or extracts instead |
| Not using custom SQL – missing opportunities for aggregation | Use custom SQL to aggregate and filter at the source |
| Ignoring the data source connection – high latency | Use a data warehouse or optimised database connection |

---

### Interview Questions

1. **How do you optimise the data source in Tableau?**  

   *Answer*: I use data source filters to limit the data, use extracts for faster queries, write custom SQL to aggregate data at the source, and use a data warehouse for pre‑aggregated data.

2. **What is the difference between a data source filter and a worksheet filter?**  

   *Answer*: A data source filter is applied when the data is loaded into Tableau, reducing the data set at the source. A worksheet filter is applied after the data is loaded, for the specific worksheet.

3. **Why would you use a custom SQL query in Tableau?**  

   *Answer*: To filter, aggregate, and join data at the source database, reducing the data loaded into Tableau and improving performance.

---

### Assignment and Dashboard Projects

**Assignment 6.7** – Optimise the data source for a dashboard:

- Add data source filters.

- Use custom SQL (if possible) to aggregate data.

- Compare the performance before and after optimisation.

- Document the changes.


---

### Summary and Revision Notes

- Data source optimisation improves query performance.

- Use data source filters to limit data.

- Use custom SQL to aggregate at the source.

- Use extracts and avoid unnecessary blending.

---

## Lesson 6.8 – Tableau Prep Basics

### Concept Explanation

**Tableau Prep** is a dedicated data preparation tool that makes it easy to clean, shape, and combine data. It is the Tableau equivalent of Power Query in Power BI.

**Why use Tableau Prep?**

- Visual, step‑by‑step interface.

- Handles complex data preparation tasks.

- Integrates with Tableau Desktop.


**Key Tableau Prep features**:

- **Connections**: Connect to files, databases, and cloud sources.

- **Flow**: A visual representation of your data preparation steps.

- **Steps**: Each action (clean, pivot, join, union) is a step in the flow.

- **Cleaning**: Remove duplicates, handle nulls, split fields.

- **Joins and Unions**: Combine data from multiple sources.

- **Pivoting**: Reshape data from wide to long format.

- **Output**: Export to a file, Tableau Server, or Tableau Desktop.


**Tableau Prep Workflow**:

1. Connect to data source(s).

2. Add steps to clean and shape data.

3. Output the prepared data.

4. Use the output in Tableau Desktop.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Data preparation is the most time‑consuming part of analytics (often 60‑80% of the time). Tableau Prep automates and speeds up this process.

- **Use cases**:

  - A **data analyst** uses Tableau Prep to clean messy Excel files before analysis.

  - A **marketing analyst** uses Tableau Prep to join campaign data from multiple sources.

  - A **financial analyst** uses Tableau Prep to pivot budget data from wide to long format.


---

### Step‑by‑Step Demonstration

**Getting Started**:

1. Open Tableau Prep.

2. On the Start Page, click **Connect to Data**.

3. Select a data source (e.g., Sample - Superstore).

4. Drag the table onto the canvas.


**Adding a Clean Step**:

1. Click the **+** icon on the table → **Add Step**.

2. In the step, you can:

   - **Rename** fields.

   - **Change data types**.

   - **Remove duplicates**.

   - **Filter rows**.

   - **Split** fields.

   - **Handle nulls** (Replace or Remove).

**Adding a Pivot Step**:

1. Click the **+** icon → **Add Step**.

2. Select **Pivot**.

3. Choose the columns to pivot.

4. Select **Pivot to Rows**.


**Adding a Join**:

1. Connect to a second data source.

2. Drag it onto the canvas.

3. Click **Join** between the two tables.

4. Choose the join type and the join fields.


**Adding a Union**:

1. Drag a second table onto the canvas.

2. Click **Union** between the tables.


**Output**:

1. Click the **Output** icon.

2. Choose the output format (Tableau Data Source, CSV, etc.).

3. Click **Run Flow**.

---

### Practical Examples

- **Example 1**: An Excel file with messy headers and footers – use Tableau Prep to clean and export.

- **Example 2**: Three monthly sales CSV files – union them in Tableau Prep.

- **Example 3**: A wide budget file – pivot it to long format.


---

### Hands‑on Exercises

1. Open Tableau Prep and connect to Sample - Superstore.

2. Add a Clean step: rename `Sub-Category` to `Sub Category`.

3. Add a Pivot step: pivot the `Sales` and `Profit` columns (if you have them in a wide format).

4. Add a Join step: connect to another table and join on a key.

5. Output the cleaned data as a `.hyper` file.

6. Load the output into Tableau Desktop.


---

### Mini Quiz

1. What is Tableau Prep used for?

2. What are the key steps in a Tableau Prep flow?

3. How do you clean data in Tableau Prep?

4. How do you pivot data in Tableau Prep?

5. What are the output options in Tableau Prep?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Doing all preparation in Tableau Desktop – slower and less efficient | Use Tableau Prep for heavy data preparation |
| Not documenting the flow – hard to reproduce | Add comments to steps in Tableau Prep |
| Over‑complicating the flow – too many steps | Keep the flow simple; use Tableau Desktop for final calculations |
| Not validating the output – data may be wrong | Preview the data at each step |

---

### Interview Questions

1. **What is Tableau Prep and how is it different from Tableau Desktop?**  

   *Answer*: Tableau Prep is a data preparation tool used to clean, shape, and combine data. Tableau Desktop is used for visualisation and dashboard creation. Tableau Prep is often used before Tableau Desktop.

2. **What are the main features of Tableau Prep?**  

   *Answer*: Connections, Clean steps, Pivots, Joins, Unions, and Output.

3. **How do you handle null values in Tableau Prep?**  

   *Answer*: In a Clean step, you can choose to replace null values with a default value or remove rows with nulls.

---

### Assignment and Dashboard Projects

**Assignment 6.8** – Create a Tableau Prep flow:

- Connect to a messy Excel file (or use Sample - Superstore).

- Add at least three Clean steps (rename, data type, handle nulls).

- Add a Pivot step.

- Add a Join step (if you have multiple sources).

- Output the cleaned data.

- Load the output into Tableau Desktop.

- Document the flow.


---

### Summary and Revision Notes

- Tableau Prep is a visual data preparation tool.

- Key steps: Connect, Clean, Pivot, Join, Union, Output.

- Use Tableau Prep to reduce the time spent on data preparation.

- Output can be used directly in Tableau Desktop.

---

## Final Phase 6 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can create advanced calculated fields (conditional aggregations, `CASE TRUE`).

-  I can write advanced LOD expressions (nested LODs, LODs with filters).

-  I can create advanced table calculations (running totals, moving averages, rankings).

-  I can create and use Set Actions.

-  I can create and use Parameter Actions.

-  I can optimise dashboard performance.

-  I can optimise data sources.

-  I can use Tableau Prep for data preparation.

---

### Answers to Mini Quizzes

**Lesson 6.1**: 1. `SUM(IF [Category] = "Furniture" THEN [Sales] END)`. 2. `IF` supports multiple conditions; `CASE` matches discrete values. 3. `CASE TRUE WHEN ... THEN ... END`. 4. `COUNT(IF [Order Date] >= TODAY() - 30 THEN [Order ID] END)`. 5. `COUNTD(IF [Profit] > 0 THEN [Customer ID] END)`.

**Lesson 6.2**: 1. `FIXED` ignores view filters; `INCLUDE` adds to view level. 2. `SUM([Sales]) / { FIXED : SUM([Sales]) }`. 3. `AVG({ FIXED [Customer ID] : SUM([Sales]) })`. 4. An LOD inside another LOD. 5. `FIXED` ignores dimension filters but respects data source filters.

**Lesson 6.3**: 1. `RANK` skips numbers on ties; `RANK_DENSE` does not. 2. 3‑month moving average. 3. Add `YEAR([Date])` to the view and set the calculation to reset. 4. Total across the table. 5. `SUM([Sales]) - WINDOW_AVG(SUM([Sales]), -2, 2)`.

**Lesson 6.4**: 1. A subset of data. 2. An action that updates a set based on user clicks. 3. Right‑click dimension → Create → Set. 4. Drag to Color, Size, or Filters. 5. Add, Remove, Toggle.

**Lesson 6.5**: 1. An action that updates a parameter based on user clicks. 2. Dashboard → Actions → Change Parameter. 3. Use the parameter in a calculated field on the Filters shelf. 4. Parameter Action updates a parameter; Set Action updates a set. 5. Use the parameter in a title text.

**Lesson 6.6**: 1. A snapshot of data stored in Tableau. 2. Right‑click a filter → Add to Context. 3. To identify slow elements. 4. Aggregate data or use Top N filters. 5. Reduces the amount of data processed.

**Lesson 6.7**: 1. A filter applied when data is loaded. 2. Data Source page → Add → Filters. 3. Aggregates data at the source. 4. Blends query separately; joins combine at the source. 5. To provide pre‑aggregated data.

**Lesson 6.8**: 1. Data preparation. 2. Connect, Clean, Pivot, Join, Union, Output. 3. Using Clean steps. 4. Using Pivot steps. 5. File, Tableau Server, Tableau Desktop.

---

**Congratulations!** You have completed all six phases of this comprehensive Tableau curriculum. You are now a full‑stack Tableau professional, capable of:

- Connecting to and preparing any data source.

- Building sophisticated data models.

- Writing advanced calculations and LOD expressions.

- Creating stunning, interactive dashboards.

- Optimising performance for enterprise use.

- Using Tableau Prep for data preparation.

Remember that Tableau is constantly evolving, so keep learning through the Tableau community, blogs, and official documentation. The best way to maintain your skills is to keep building dashboards and solving real‑world problems.

Good luck on your Tableau journey!

---










<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>