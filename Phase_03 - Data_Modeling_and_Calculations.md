# Phase 3: Data Modeling and Calculations

Welcome to **Phase 3** – the intellectual core of Tableau! In Phase 2, you learned to clean and shape your data. Now, you will learn how to **think in Tableau** – understanding how data is categorised, how calculations work, and how to create powerful derived fields that unlock deeper insights.

This phase covers everything from the fundamental building blocks (Dimensions vs Measures, Discrete vs Continuous) to advanced calculations (Table Calculations and Level of Detail Expressions). These concepts are the bridge between raw data and meaningful analysis. Mastery of this phase will set you apart as a Tableau expert.

We'll proceed step‑by‑step, from absolute basics to sophisticated techniques, with real‑world business scenarios at every turn.

---

## Lesson 3.1 – Dimensions and Measures / Discrete vs Continuous Fields

### Concept Explanation

These four concepts form the foundation of every Tableau visualisation. Understanding them is like knowing the parts of speech in a language – you can't form a proper sentence without them.

**Dimensions vs Measures** (what the data represents):

| | **Dimensions** | **Measures** |
|---|---|---|
| **What they are** | Categorical fields that describe attributes | Quantitative fields that can be measured |
| **Examples** | Product, Region, Customer Name, Date | Sales, Profit, Quantity, Temperature |
| **Used for** | Grouping, filtering, labelling | Aggregating (sum, average, count) |
| **Colour in Data pane** | Blue (or Abc icon) | Green (or # icon) |
| **How Tableau treats them** | Creates headers (labels) | Creates axes (numeric scales) |

**Discrete vs Continuous** (how the data is treated):

| | **Discrete** | **Continuous** |
|---|---|---|
| **What it means** | Values are distinct, separate categories | Values form a continuous range |
| **Colour** | Blue | Green |
| **Examples** | Product names, specific dates (Jan 1, Jan 2) | A continuous timeline, numeric scale |
| **What Tableau creates** | Headers (labels) | Axes (with a continuous scale) |
| **Behaviour in charts** | Creates individual marks (bars) | Creates a continuous line or smooth gradient |

**The key insight**: A field is **both** a dimension/measure AND discrete/continuous. For example, `Order Date` is a dimension (it's categorical) but can be treated as discrete (e.g., each date as a separate label) or continuous (e.g., a continuous time axis).

---

### Importance and Real‑World Use Cases

- **Why it matters**: These concepts determine **how** your data is displayed. Dragging a field as discrete creates a bar chart with distinct bars; dragging it as continuous creates a line chart with a continuous axis. Choosing correctly ensures your visualisation accurately represents your data.

- **Use cases**:

  - A **sales analyst** wants to show sales by month. If they treat `Month` as **discrete**, they get a bar chart with each month as a separate bar. If they treat it as **continuous**, they get a line chart showing the trend.

  - A **financial analyst** wants to show profit margin. They drag `Profit` to the view – as a measure, it sums automatically.

  - A **geospatial analyst** uses `Country` as a dimension to group data on a map.


---

### Step‑by‑Step Demonstration

1. Open Tableau and connect to **Sample - Superstore**.

2. Look at the **Data pane** on the left:

   - Fields with a blue icon (or Abc for strings) are **dimensions**.

   - Fields with a green icon (or # for numbers) are **measures**.

3. Drag `Sales` (green measure) to **Columns** – it appears as `SUM(Sales)` because measures are aggregated by default.

4. Drag `Category` (blue dimension) to **Rows** – a bar chart appears.

5. Now look at the **Marks Card** – you'll see `SUM(Sales)` is a green pill.

6. Click the drop‑down arrow on `Category` (in Rows). You'll see **Discrete** is checked (blue pill).

7. Now change `Category` to continuous: right‑click `Category` in Rows → **Continuous**. The chart changes – a continuous axis appears (though for text categories, it might look strange).

8. Now drag `Order Date` (dimension) to Columns. By default, it's discrete (blue). Click the drop‑down and change to **Continuous** (green) – the chart changes from individual date headers to a continuous axis.

9. Experiment with different fields to see how discrete vs continuous changes the view.

---

### Practical Examples

- **Example 1**: You want to show sales by product category. Drag `Category` (discrete dimension) to Rows and `Sales` to Columns – you get a bar chart with distinct bars for each category. This is the most common use of dimensions.

- **Example 2**: You want to show sales over a continuous timeline. Drag `Order Date` to Columns as **Continuous** (green) and `Sales` to Rows – you get a line chart showing the trend.

- **Example 3**: You want to colour marks by profit. Drag `Profit` (measure) to Color on the Marks Card. Tableau automatically creates a continuous colour gradient (green/red) because `Profit` is a measure.

---

### Hands‑on Exercises

1. Connect to Sample - Superstore.

2. Drag `Sales` to Columns and `Category` to Rows – observe the discrete bar chart.

3. Click on `Category` in Rows and change it to **Continuous** – observe the change.

4. Drag `Order Date` to Columns. Change it between Discrete and Continuous and observe the difference (bar chart vs line chart).

5. Drag `Profit` to Color on the Marks Card – observe the continuous colour gradient.

6. Identify all dimensions and measures in the Data pane.

---

### Mini Quiz

1. What is the difference between a dimension and a measure?

2. What colour represents a discrete field in Tableau? Continuous?

3. What does a measure do when you drag it to a view?

4. What is the difference between a continuous date and a discrete date?

5. Can a dimension be continuous? Can a measure be discrete?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Confusing discrete and continuous – using discrete for time series (creates separate bars instead of a trend line) | Use **continuous** for dates and numeric axes when showing trends |
| Treating numeric IDs as measures – summing them creates meaningless numbers | Change numeric IDs to dimensions (right‑click → Convert to Dimension) |
| Not understanding that measures are aggregated by default – expecting row‑level values | Use measures for aggregations; for row‑level, use a calculation or table calculation |
| Ignoring the pill colour – blue vs green tells you how the field is being used | Pay attention to pill colours; they indicate how Tableau is interpreting the field |

---

### Interview Questions

1. **What is the difference between a dimension and a measure in Tableau?**  

   *Answer*: Dimensions are categorical fields used to group, filter, and label data (e.g., Region, Product). Measures are numeric fields that can be aggregated (e.g., Sales, Profit). Dimensions create headers; measures create axes.

2. **What is the difference between discrete and continuous fields?**  

   *Answer*: Discrete fields are distinct, separate values that create headers (blue pills). Continuous fields form a continuous range that creates axes (green pills). Discrete is for categories; continuous is for numeric and date ranges.

3. **How can you change a measure to a dimension in Tableau?**  

   *Answer*: Right‑click the field in the Data pane and select **Convert to Dimension**, or drag it to the Dimensions section.

---

### Assignment and Dashboard Projects

**Assignment 3.1** – Create a worksheet that demonstrates your understanding:

- A bar chart using a discrete dimension.

- A line chart using a continuous date.

- A scatter plot using two measures.

- Add a screenshot of the Data pane showing the dimensions and measures.

- Write a brief explanation of why you used each field type.


---

### Summary and Revision Notes

- **Dimensions**: categorical, blue, create headers.

- **Measures**: numeric, green, create axes, are aggregated.

- **Discrete**: blue, distinct values, creates headers.

- **Continuous**: green, continuous range, creates axes.

- A field is both a dimension/measure AND discrete/continuous.

- Use continuous for trends; discrete for distinct categories.

---

## Lesson 3.2 – Calculated Fields and Basic Calculations

### Concept Explanation

**Calculated fields** are custom fields you create using formulas. They allow you to derive new data from existing fields – for example, calculating profit margin, concatenating first and last names, or creating categories based on conditions.

**Where to create them**:

- In the Data pane, click the drop‑down arrow next to **Dimensions** or **Measures** and select **Create Calculated Field**.

- Or, right‑click in the Data pane → **Create Calculated Field**.

**Basic calculation types**:

1. **Arithmetic**: `[Sales] - [Profit]` (for cost), `[Sales] / [Quantity]` (for average price).

2. **String**: `[First Name] + " " + [Last Name]` (for full name).

3. **Date**: `DATEDIFF('day', [Order Date], [Ship Date])` (for shipping days).

4. **Logical**: `IF [Sales] > 1000 THEN "High" ELSE "Low" END`.

5. **Aggregate**: `SUM([Sales]) / SUM([Quantity])` – but note that this is an aggregate calculation.


**Syntax basics**:

- Field names are enclosed in square brackets: `[Sales]`.

- Strings are in single quotes: `'High'`.

- Logical operators: `AND`, `OR`, `NOT`.

- Comparison: `=`, `<>`, `>`, `<`, `>=`, `<=`.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Calculated fields are where business logic lives. They transform raw data into actionable metrics – profit margins, customer tiers, age groups, etc. Without them, your analysis remains superficial.

- **Use cases**:

  - A **financial analyst** creates `Gross Profit = [Sales] - [Cost]` to analyse profitability.

  - A **marketing analyst** creates `Conversion Rate = [Orders] / [Visits]` to measure campaign effectiveness.

  - A **HR analyst** creates `Age Group = IF [Age] < 30 THEN "Young" ELSEIF < 50 THEN "Middle" ELSE "Senior" END` to segment employees.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. In the Data pane, click the drop‑down arrow next to **Measures** → **Create Calculated Field**.

3. Name it `Profit Margin %`.

4. Enter the formula: `SUM([Profit]) / SUM([Sales])`

5. Click **OK**. The new field appears in the Data pane with a `=` icon.

6. Drag `Profit Margin %` to the view – it displays the margin.

7. Create another field: `Shipping Delay` (if you have a Ship Date):

   - `DATEDIFF('day', [Order Date], [Ship Date])`

8. Create a field: `Category Group`:

   - `IF [Category] = "Technology" OR [Category] = "Office Supplies" THEN "Core" ELSE "Other" END`

---

### Practical Examples

- **Example 1**: `Profit Ratio = SUM([Profit]) / SUM([Sales])` – gives the overall profit margin.


- **Example 2**: `Days to Ship = DATEDIFF('day', [Order Date], [Ship Date])` – allows you to analyse shipping performance.


- **Example 3**: `Customer Tier = IF [Total Sales] > 10000 THEN "Gold" ELSEIF [Total Sales] > 5000 THEN "Silver" ELSE "Bronze" END` – segments customers.



---

### Hands‑on Exercises

1. Create a calculated field `Revenue per Unit` = `SUM([Sales]) / SUM([Quantity])`.

2. Create a calculated field `Full Name` = `[Customer Name]` (if you have first and last separately, use concatenation).

3. Create a calculated field `Discount Level` using `IF [Discount] = 0 THEN "None" ELSE "Discounted" END`.

4. Create a calculated field `Shipment Efficiency` = `1 - ([Shipping Cost] / [Sales])` (if you have shipping cost).

5. Drag these fields into a worksheet to see the results.


---

### Mini Quiz

1. How do you create a calculated field in Tableau?

2. What is the syntax to reference a field in a formula?

3. How do you write a string literal in a calculated field?

4. Write a formula to calculate the average price per unit (Sales / Quantity) as a measure.

5. What does the `DATEDIFF` function do?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using aggregation (`SUM`) inside a calculation that is then used as a dimension – causing errors | Understand when to use row‑level vs aggregate calculations |
| Not testing calculations with sample data – errors go unnoticed | Test your calculated fields with a few rows before using them broadly |
| Overcomplicating formulas – hard to maintain | Break complex logic into multiple calculated fields |
| Using field names with spaces without brackets | Always enclose field names in square brackets: `[Order Date]` |

---

### Interview Questions

1. **How do you create a calculated field in Tableau?**  

   *Answer*: In the Data pane, click the drop‑down arrow next to Dimensions or Measures and select Create Calculated Field. Alternatively, right‑click in the Data pane and select Create Calculated Field.

2. **What is the difference between a calculated field and a table calculation?**  

   *Answer*: A calculated field is computed at the data source level (for each row) and is stored in the data model. A table calculation is computed on the result set of the view (after aggregation) and is not stored.

3. **How would you calculate profit margin in Tableau?**  

   *Answer*: `SUM([Profit]) / SUM([Sales])`. Format the field as a percentage.

---

### Assignment and Dashboard Projects

**Assignment 3.2** – Create at least five calculated fields on the Superstore dataset:

- Two arithmetic fields.

- One string field.

- One date field.

- One logical field.

- Build a simple dashboard using these fields and document each calculation.


---

### Summary and Revision Notes

- Calculated fields create new data from existing fields.

- Syntax: `[FieldName]` for fields, `'text'` for strings.

- Types: arithmetic, string, date, logical, aggregate.

- Test your calculations.


---

## Lesson 3.3 – String, Number, and Date Functions

### Concept Explanation

Now that you know how to create calculated fields, let's explore the most useful functions for manipulating text, numbers, and dates.

**String Functions** (text manipulation):
| **Function** | **Description** | **Example** |
|--------------|-----------------|-------------|
| `LEFT(string, num)` | Returns leftmost characters | `LEFT([Product Name], 5)` |
| `RIGHT(string, num)` | Returns rightmost characters | `RIGHT([Product Name], 3)` |
| `MID(string, start, num)` | Extracts from the middle | `MID([Product ID], 3, 2)` |
| `LEN(string)` | Returns string length | `LEN([Customer Name])` |
| `FIND(string, substring)` | Finds position of substring | `FIND([Email], "@")` |
| `REPLACE(string, old, new)` | Replaces text | `REPLACE([Country], "USA", "United States")` |
| `UPPER(string)`, `LOWER(string)` | Change case | `UPPER([City])` |
| `CONTAINS(string, substring)` | Checks if substring exists | `CONTAINS([Product Name], "Chair")` |
| `TRIM(string)` | Removes leading/trailing spaces | `TRIM([Customer Name])` |
| `SPLIT(string, delimiter, part)` | Splits text (Tableau 2020.4+) | `SPLIT([Full Name], " ", 1)` |

**Number Functions**:
| **Function** | **Description** | **Example** |
|--------------|-----------------|-------------|
| `ROUND(number, decimals)` | Rounds a number | `ROUND([Sales], 2)` |
| `CEILING(number)` | Rounds up | `CEILING([Sales])` |
| `FLOOR(number)` | Rounds down | `FLOOR([Sales])` |
| `ABS(number)` | Absolute value | `ABS([Profit])` |
| `MIN(number1, number2)` | Returns smaller value | `MIN([Sales], [Budget])` |
| `MAX(number1, number2)` | Returns larger value | `MAX([Sales], [Budget])` |
| `ZN(expression)` | Returns 0 if null | `ZN([Profit])` |

**Date Functions**:
| **Function** | **Description** | **Example** |
|--------------|-----------------|-------------|
| `DATEADD(part, interval, date)` | Adds interval to date | `DATEADD('month', 1, [Order Date])` |
| `DATEDIFF(part, date1, date2)` | Difference between dates | `DATEDIFF('day', [Order Date], [Ship Date])` |
| `DATEPART(part, date)` | Returns part of a date | `DATEPART('year', [Order Date])` |
| `DATETRUNC(part, date)` | Truncates date to part | `DATETRUNC('month', [Order Date])` |
| `MAKEDATE(year, month, day)` | Creates a date | `MAKEDATE(2025, 1, 15)` |
| `TODAY()` | Returns current date | `TODAY()` |
| `NOW()` | Returns current date/time | `NOW()` |

---

### Importance and Real‑World Use Cases

- **Why it matters**: Data rarely comes in the exact format you need. Functions allow you to extract, transform, and format data on the fly.

- **Use cases**:

  - A **marketing analyst** uses `SPLIT` to extract campaign names from a long string.

  - A **financial analyst** uses `ROUND` to format currency values.

  - A **supply chain analyst** uses `DATEDIFF` to calculate delivery times.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. Create a calculated field `Product Code Start` = `LEFT([Product Name], 3)`.

3. Create `Product Name Length` = `LEN([Product Name])`.

4. Create `Profit Absolute` = `ABS([Profit])` – absolute value.

5. Create `Order Year` = `DATEPART('year', [Order Date])`.

6. Create `Shipment Days` = `DATEDIFF('day', [Order Date], [Ship Date])`.

7. Create `Order Month Start` = `DATETRUNC('month', [Order Date])` – useful for grouping.

8. Drag these into a worksheet to see the results.


---

### Practical Examples

- **Example 1**: `Email Domain = RIGHT([Email], LEN([Email]) - FIND([Email], "@"))` – extracts domain from email.

- **Example 2**: `Age in Days = DATEDIFF('day', [Birthdate], TODAY())` – calculates age in days.

- **Example 3**: `Sales Rounded = ROUND([Sales], 0)` – rounds sales to the nearest dollar.


---

### Hands‑on Exercises

1. Create a calculated field that extracts the first 4 characters of `Product Name`.

2. Create a field that replaces "Furniture" with "Home Furnishings" in `Category`.

3. Create a field that calculates `Profit` as a positive value using `ABS`.

4. Create a field that calculates the number of days between `Order Date` and `Ship Date`.

5. Create a field that extracts the year from `Order Date`.

---

### Mini Quiz

1. Which function would you use to extract the first 5 characters of a string?

2. How do you calculate the difference in days between two dates?

3. What does `ZN()` do?

4. How do you round a number to 2 decimal places?

5. Which function returns the current date?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using `DATEDIFF` with the wrong date part (e.g., 'day' vs 'week') | Specify the correct part: 'day', 'month', 'year', 'week', 'hour', etc. |
| Forgetting to handle nulls – calculations break | Use `ZN()` or `IFNULL()` to handle nulls |
| Using `SPLIT` on a field that sometimes has fewer parts – returns null | Use `SPLIT` with a default or handle with `IF CONTAINS` |
| Not testing functions with edge cases | Test with a variety of data to ensure robustness |

---

### Interview Questions

1. **How would you extract the month from a date in Tableau?**  

   *Answer*: `DATEPART('month', [Date])` returns the month number. `DATENAME('month', [Date])` returns the month name.

2. **What is the difference between `DATEPART` and `DATETRUNC`?**  

   *Answer*: `DATEPART` returns a specific part of a date (e.g., month number). `DATETRUNC` returns the date truncated to a specific part (e.g., first day of the month), which is useful for grouping.

3. **How would you calculate the age of a customer in years?**  

   *Answer*: `DATEDIFF('year', [Birthdate], TODAY())` – but this gives the difference in years; for exact age, you might need to adjust for birthdays.

---

### Assignment and Dashboard Projects

**Assignment 3.3** – Create a worksheet that uses at least three string, three number, and three date functions. Document each function and its purpose.

---

### Summary and Revision Notes

- String functions: `LEFT`, `RIGHT`, `MID`, `LEN`, `FIND`, `REPLACE`, `SPLIT`, `UPPER`, `LOWER`.

- Number functions: `ROUND`, `CEILING`, `FLOOR`, `ABS`, `MIN`, `MAX`, `ZN`.

- Date functions: `DATEADD`, `DATEDIFF`, `DATEPART`, `DATETRUNC`, `TODAY`, `NOW`.


---

## Lesson 3.4 – Logical Functions

### Concept Explanation

**Logical functions** allow you to perform conditional logic – returning different values based on conditions. These are essential for categorising, flagging, and creating business rules.

**Key logical functions**:

| **Function** | **Description** | **Example** |
|--------------|-----------------|-------------|
| `IF condition THEN true ELSE false END` | Basic conditional | `IF [Sales] > 1000 THEN "High" ELSE "Low" END` |
| `IF condition THEN true ELSEIF condition THEN true ELSE false END` | Multiple conditions | `IF [Sales] > 10000 THEN "Gold" ELSEIF [Sales] > 5000 THEN "Silver" ELSE "Bronze" END` |
| `IIF(condition, true, false)` | Inline if (shorthand) | `IIF([Sales] > 1000, "High", "Low")` |
| `CASE [field] WHEN value1 THEN result1 ... ELSE default END` | Case statement | `CASE [Category] WHEN "Furniture" THEN 1 WHEN "Office Supplies" THEN 2 ELSE 3 END` |
| `AND`, `OR`, `NOT` | Logical operators | `IF [Sales] > 1000 AND [Profit] > 100 THEN "Good" ELSE "Bad" END` |
| `ISNULL(expression)` | Checks if null | `ISNULL([Customer Name])` |
| `IFNULL(expression1, expression2)` | Returns expression1 if not null, else expression2 | `IFNULL([Sales], 0)` |

---

### Importance and Real‑World Use Cases

- **Why it matters**: Business logic is almost always conditional. Customers are tiered, products are classified, and performance is rated. Logical functions bring this logic to your data.

- **Use cases**:

  - A **sales analyst** creates a `Tier` field: `IF [Total Sales] > 100000 THEN "Platinum" ELSEIF > 50000 THEN "Gold" ELSE "Silver" END`.

  - A **marketing analyst** creates a `Campaign Status` field: `IIF([Budget] = 0, "Inactive", "Active")`.

  - A **financial analyst** creates a `Flag` for high‑risk accounts.

---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. Create a calculated field `Sales Tier`:

   ```
   IF [Sales] > 5000 THEN "High"
   ELSEIF [Sales] > 1000 THEN "Medium"
   ELSE "Low"
   END
   ```
3. Create `High Profit Flag`:

   ```
   IIF([Profit] > 100, "Profitable", "Not Profitable")
   ```
4. Create `Category Code`:

   ```
   CASE [Category]
       WHEN "Furniture" THEN 1
       WHEN "Office Supplies" THEN 2
       WHEN "Technology" THEN 3
       ELSE 0
   END
   ```
5. Create `Null Check`:

   ```
   IFNULL([Postal Code], "Unknown")
   ```
6. Drag these fields into a worksheet to see the results.


---

### Practical Examples

- **Example 1**: `IF [Discount] = 0 THEN "Full Price" ELSE "Discounted" END` – simple flag.

- **Example 2**: `CASE [Region] WHEN "East" THEN 1 WHEN "West" THEN 2 WHEN "South" THEN 3 WHEN "Central" THEN 4 END` – numeric mapping for sorting.

- **Example 3**: `IIF([Order Date] >= TODAY() - 30, "Recent", "Old")` – recency flag.


---

### Hands‑on Exercises

1. Create a calculated field that categorises products as "High Margin" if Profit/Sales > 30%, "Medium" if > 15%, else "Low".

2. Create a field that flags orders where Shipping Cost > 10% of Sales.

3. Create a field that replaces null `Region` values with "Unknown".

4. Create a field that uses `CASE` to map `Segment` to a numeric code.

---

### Mini Quiz

1. What is the difference between `IF` and `IIF`?

2. How do you check if a field is null?

3. What does `IFNULL` do?

4. Write a `CASE` statement that maps `Category` to a group.

5. How do you combine conditions with `AND` and `OR`?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Forgetting `END` in `IF` statements – syntax error | Always close `IF` with `END` |
| Using `=` instead of `==` in logical comparisons – Tableau uses `=` | Use `=` for equality (not `==`) |
| Nesting too many `IF` statements – becomes unreadable | Use `CASE` for multiple discrete values, or break into multiple fields |
| Not handling nulls – calculations return null | Use `IFNULL` or `ISNULL` to handle nulls |

---

### Interview Questions

1. **How do you implement conditional logic in Tableau?**  

   *Answer*: Using logical functions like `IF`, `IIF`, `CASE`, and operators like `AND`, `OR`, `NOT`. `IF` is used for complex conditions, `IIF` for simple true/false, and `CASE` for matching discrete values.

2. **What is the difference between `IF` and `IIF`?**  

   *Answer*: `IF` is a full conditional statement that can handle multiple `ELSEIF` branches and must end with `END`. `IIF` is a shorthand for simple true/false conditions and returns a single value.

3. **How would you replace null values in a field?**  

   *Answer*: Use `IFNULL([Field], 'Default Value')` or `ZN([Field])` for numeric fields.

---

### Assignment and Dashboard Projects

**Assignment 3.4** – Create a worksheet that uses at least three logical functions:

- One `IF` with multiple `ELSEIF` branches.

- One `IIF`.

- One `CASE`.

- One `IFNULL`.

- Apply these to categorise products, flag orders, and handle nulls.


---

### Summary and Revision Notes

- Logical functions implement conditional logic.

- `IF ... THEN ... ELSEIF ... ELSE ... END` – for multiple conditions.

- `IIF(condition, true, false)` – for simple conditions.

- `CASE [field] WHEN value THEN result ... END` – for discrete matching.

- `ISNULL`, `IFNULL` – handle null values.


---

## Lesson 3.5 – Aggregate Functions

### Concept Explanation

**Aggregate functions** summarise multiple rows into a single value. They are the core of analytical calculations – totals, averages, counts, etc. In Tableau, measures are automatically aggregated when you drag them into a view.

**Common aggregate functions**:

| **Function** | **Description** | **Example** |
|--------------|-----------------|-------------|
| `SUM(expression)` | Sum of values | `SUM([Sales])` |
| `AVG(expression)` | Average of values | `AVG([Sales])` |
| `COUNT(expression)` | Count of non‑null values | `COUNT([Customer ID])` |
| `COUNTD(expression)` | Count of distinct values | `COUNTD([Customer ID])` |
| `MIN(expression)` | Minimum value | `MIN([Sales])` |
| `MAX(expression)` | Maximum value | `MAX([Sales])` |
| `STDEV(expression)` | Standard deviation | `STDEV([Sales])` |
| `VAR(expression)` | Variance | `VAR([Sales])` |
| `MEDIAN(expression)` | Median value | `MEDIAN([Sales])` |
| `PERCENTILE(expression, n)` | Percentile | `PERCENTILE([Sales], 0.5)` |

**Aggregation in calculated fields**:

- When you create a calculated field, you can use aggregate functions: `SUM([Sales]) / SUM([Quantity])` – this returns the average price.

- But you cannot mix aggregated and non‑aggregated values in the same calculation (e.g., `SUM([Sales]) + [Quantity]` – Tableau will throw an error).


**Row‑level vs Aggregate**:
- Row‑level calculations are evaluated for each row (e.g., `[Sales] - [Cost]`).

- Aggregate calculations are evaluated over groups (e.g., `SUM([Sales])`).

---

### Importance and Real‑World Use Cases

- **Why it matters**: Aggregations are how we summarise data – answering questions like "What are our total sales?" or "What is the average order value?"

- **Use cases**:

  - A **financial analyst** uses `SUM` for total revenue.

  - A **customer analyst** uses `COUNTD` for unique customers.

  - A **product manager** uses `AVG` for average selling price.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. Drag `Sales` to Columns – Tableau automatically shows `SUM(Sales)`.

3. Click the drop‑down arrow on `SUM(Sales)` → **Measure** → change to `AVG`, `MIN`, `MAX`, `COUNT`, etc.

4. Create a calculated field `Total Sales` = `SUM([Sales])` – this is an aggregate calculation.

5. Create `Average Price` = `SUM([Sales]) / SUM([Quantity])` – uses two aggregations.

6. Create `Distinct Customers` = `COUNTD([Customer ID])`.

7. Drag `Category` to Rows and see how the aggregations change per category.

---

### Practical Examples

- **Example 1**: `Total Revenue = SUM([Sales])` – used in KPIs.

- **Example 2**: `Average Order Value = SUM([Sales]) / COUNTD([Order ID])` – total sales divided by number of orders.

- **Example 3**: `Customer Acquisition Cost = SUM([Marketing Spend]) / COUNTD([New Customers])`.


---

### Hands‑on Exercises

1. Create a calculated field `Total Sales` = `SUM([Sales])`.

2. Create `Total Profit` = `SUM([Profit])`.

3. Create `Profit Ratio` = `[Total Profit] / [Total Sales]`.

4. Create `Unique Products` = `COUNTD([Product Name])`.

5. Create `Average Discount` = `AVG([Discount])`.

6. Drag `Category` to Rows and place these measures in a table.


---

### Mini Quiz

1. What is an aggregate function?

2. What is the difference between `COUNT` and `COUNTD`?

3. How do you change the aggregation of a measure in a view?

4. Write a calculation that returns the average sales per order.

5. Can you mix aggregated and non‑aggregated fields in the same calculation?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using `SUM` on a field that should be averaged – misleading numbers | Choose the correct aggregation for your business question |
| Forgetting to use `COUNTD` for distinct counts – using `COUNT` instead | Always use `COUNTD` when you need unique counts |
| Mixing aggregate and non‑aggregate expressions – syntax errors | Ensure all fields in a calculation are either all aggregated or all non‑aggregated |
| Not understanding that Tableau aggregates by default – may be surprised by values | Always check the aggregation of fields in your view |

---

### Interview Questions

1. **What are the common aggregate functions in Tableau?**  

   *Answer*: `SUM`, `AVG`, `COUNT`, `COUNTD`, `MIN`, `MAX`, `STDEV`, `VAR`, `MEDIAN`, `PERCENTILE`.

2. **What is the difference between `COUNT` and `COUNTD`?**  

   *Answer*: `COUNT` counts the number of non‑null rows. `COUNTD` counts the number of distinct (unique) values in a field.

3. **How do you calculate the average sales per order in Tableau?**  

   *Answer*: `SUM([Sales]) / COUNTD([Order ID])` – this divides total sales by the number of unique orders.

---

### Assignment and Dashboard Projects

**Assignment 3.5** – Create a dashboard showing:

- Total Sales, Total Profit, Profit Margin %.

- Average Sales per Order.

- Distinct Customers and Products.

- All measures should be aggregated correctly.

- Add a table showing these metrics by Category.

---

### Summary and Revision Notes

- Aggregates summarise data: `SUM`, `AVG`, `COUNT`, `COUNTD`, `MIN`, `MAX`.

- `COUNTD` counts unique values.

- Aggregate fields cannot be mixed with non‑aggregate fields in calculations.

- Tableau defaults to `SUM` for numeric measures.

---

## Lesson 3.6 – Table Calculations

### Concept Explanation

**Table calculations** are calculations applied to the **result set** of a view – they are computed after the data has been aggregated. This is different from calculated fields (which are computed row‑by‑row at the data source level).

**Key characteristics**:

- Computed on the **table** (the view's data).

- Used for: running totals, percent of total, moving averages, rankings, and comparisons.

- They are not stored – they are computed each time the view is rendered.


**Common table calculations**:

| **Calculation** | **Description** | **Use Case** |
|-----------------|-----------------|--------------|
| **Running Total** | Cumulative sum | Tracking sales growth over time |
| **Percent of Total** | Each value as % of total | Market share analysis |
| **Rank** | Ranking values | Top 10 products |
| **Difference** | Difference from previous | Month‑over‑month change |
| **Percent Difference** | % change from previous | Growth rates |
| **Moving Average** | Average over a window | Smoothing trends |

**How to apply a table calculation**:

1. Add a measure to the view (e.g., `SUM(Sales)`).

2. Right‑click the measure pill → **Add Table Calculation**.

3. Choose the calculation type.

4. Configure the **Compute Using** (the direction) and **Scope** (what it applies to).


**Important**: Table calculations are dependent on the structure of the view (the dimensions on Rows and Columns). Changing the view changes the calculation.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Table calculations answer questions like "What is the running total?", "What percentage of total does each product contribute?", and "What is the month‑over‑month growth?". These are fundamental business questions.

- **Use cases**:

  - A **sales analyst** uses **Running Total** to show cumulative sales over the year.

  - A **marketing analyst** uses **Percent of Total** to show each channel's share of conversions.

  - A **financial analyst** uses **Percent Difference** to show quarter‑over‑quarter growth.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. Drag `Order Date` to Columns (as Discrete by month).

3. Drag `Sales` to Rows – you get a bar chart of sales by month.

4. Right‑click `SUM(Sales)` → **Add Table Calculation**.

5. Choose **Running Total** → **Table (across)**.

6. The chart now shows cumulative sales.

7. Try **Percent of Total** – shows each month's contribution to total.

8. Try **Rank** – ranks months by sales.

9. Try **Difference** – shows the change from the previous month.

**Compute Using options**:

- **Table (across)**: across the table.

- **Table (down)**: down the table.

- **Pane**: within the current pane.

- **Cell**: single cell (not useful alone).


---

### Practical Examples

- **Example 1**: Running Total of Sales by Month – to track progress towards an annual target.

- **Example 2**: Percent of Total Sales by Category – to see which category contributes most.

- **Example 3**: Moving Average of Sales (3‑month) – to smooth out seasonal fluctuations.


---

### Hands‑on Exercises

1. Create a view with `Order Date` (month) on Columns and `SUM(Sales)` on Rows.

2. Add a Running Total table calculation.

3. Duplicate the sheet and change to Percent of Total.

4. Duplicate again and change to Difference (from previous).

5. Duplicate again and change to Moving Average (3 periods).

6. Observe how each calculation changes the view.

---

### Mini Quiz

1. What is a table calculation?

2. How do you add a table calculation in Tableau?

3. What is the difference between a calculated field and a table calculation?

4. What does "Compute Using" control?

5. Name three types of table calculations.


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Applying table calculations without understanding the view structure – wrong results | Understand the layout of your view before applying table calculations |
| Choosing the wrong "Compute Using" – e.g., Table (across) when you want Table (down) | Select the correct direction based on your dimensions |
| Using table calculations for row‑level logic – they are for aggregated results | Use calculated fields for row‑level logic; table calculations for post‑aggregation |
| Not resetting calculations across dimensions – e.g., ranking each product separately | Use **Scope** to control resetting (e.g., Pane, Table) |

---

### Interview Questions

1. **What is the difference between a calculated field and a table calculation?**  

   *Answer*: A calculated field is computed row‑by‑row at the data source level and is stored in the model. A table calculation is computed on the aggregated result set of the view and is not stored – it is calculated each time the view is rendered.

2. **How would you calculate a running total in Tableau?**  

   *Answer*: Right‑click the measure, add a table calculation, and select **Running Total**. Configure the compute direction (e.g., Table (across) for months).

3. **What is the purpose of the "Compute Using" setting?**  

   *Answer*: It determines the direction and scope of the table calculation – e.g., whether it runs across columns, down rows, or within a pane.

---

### Assignment and Dashboard Projects

**Assignment 3.6** – Create a dashboard that includes:

- A view showing Running Total of Sales by Month.

- A view showing Percent of Total Sales by Category.

- A view showing Month‑over‑Month Growth using Difference.

- A view showing Rank of Products by Sales.

- For each, document the table calculation used.


---

### Summary and Revision Notes

- Table calculations are computed on the view's aggregated data.

- Common types: Running Total, Percent of Total, Rank, Difference, Percent Difference, Moving Average.

- Added via right‑click → Add Table Calculation.

- Compute Using controls direction and scope.


---

## Lesson 3.7 – Level of Detail (LOD) Expressions

### Concept Explanation

**Level of Detail (LOD) expressions** are a powerful feature that allows you to compute aggregations at a **different granularity** than the view's level. They give you control over the "level" at which a calculation is performed.

**Why LOD?** : Sometimes you need to calculate something at a level that is not present in the view. For example, you might want to show each product's **average sales per customer**, but your view is at the product level. An LOD expression allows you to compute at the customer level, then bring that result to the product level.

**Three types of LOD expressions**:

| **Type** | **Syntax** | **Description** | **Use Case** |
|----------|------------|-----------------|--------------|
| **Fixed** | `{ FIXED [Dimension] : AGG(Measure) }` | Computes at the specified dimension(s), ignoring view filters | Total sales per customer, regardless of filter |
| **Include** | `{ INCLUDE [Dimension] : AGG(Measure) }` | Adds the specified dimension to the view's level | Adding a detail dimension to an aggregate |
| **Exclude** | `{ EXCLUDE [Dimension] : AGG(Measure) }` | Removes the specified dimension from the view's level | Removing a dimension to calculate a higher‑level aggregate |

**Aggregation in LOD**: The expression must contain an aggregation function (e.g., `SUM`, `AVG`, `COUNTD`).

**Example**:

- You have a view showing Sales by Region.

- You want to show the average sales per customer for each region.

- You can write: `{ FIXED [Region] : AVG({ FIXED [Customer ID], [Region] : SUM([Sales]) }) }` – but a simpler approach is `{ FIXED [Customer ID], [Region] : SUM([Sales]) }` then average that.


Actually, a classic example:

- `{ FIXED [Customer ID] : SUM([Sales]) }` – total sales per customer.

- Then you can average that over products or categories.


---

### Importance and Real‑World Use Cases

- **Why it matters**: LOD expressions solve the "level mismatch" problem. They allow you to answer questions like "What is each product's share of total sales?" (you need total sales at the entire dataset level) or "What is the average order value per customer?" at a product‑level view.

- **Use cases**:

  - A **retail analyst** wants to show each product's sales as a percentage of total sales. `{ FIXED : SUM([Sales]) }` gives the grand total.

  - A **customer analyst** wants to show average revenue per customer, but the view is by product. `AVG({ FIXED [Customer ID] : SUM([Sales]) })`.

  - A **regional analyst** wants to show the highest‑selling product in each region, using `FIXED` to compute within regions.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. Create a calculated field `Total Sales Overall` = `{ FIXED : SUM([Sales]) }`.

3. Create a field `% of Total Sales` = `SUM([Sales]) / [Total Sales Overall]`.

4. Drag `Category` to Rows, `% of Total Sales` to Columns – you see each category's contribution to total sales.

5. Create `Customer Sales` = `{ FIXED [Customer ID] : SUM([Sales]) }`.

6. Create `Average Customer Sales` = `AVG([Customer Sales])`.

7. Drag `Category` to Rows and `Average Customer Sales` to Columns – you see the average sales per customer for each category.

**Include Example**:

- `{ INCLUDE [Region] : SUM([Sales]) }` – this adds Region to the level of detail, so even if Region isn't in the view, the calculation includes it.

**Exclude Example**:

- `{ EXCLUDE [Category] : SUM([Sales]) }` – removes Category from the level of detail, giving the total sales across all categories, even when Category is in the view.

---

### Practical Examples

- **Example 1**: `{ FIXED [Product] : SUM([Sales]) }` – total sales per product (good for product‑level metrics).

- **Example 2**: `{ FIXED [Region] : AVG( { FIXED [Customer ID], [Region] : SUM([Sales]) } ) }` – average customer spending per region.

- **Example 3**: `{ EXCLUDE [Order Date] : SUM([Sales]) }` – total sales ignoring date filters.


---

### Hands‑on Exercises

1. Create a `Grand Total Sales` field using `{ FIXED : SUM([Sales]) }`.

2. Create `% of Total` = `SUM([Sales]) / [Grand Total Sales]`.

3. Create `Customer Lifetime Value` = `{ FIXED [Customer ID] : SUM([Sales]) }`.

4. Create `Average Customer LTV` = `AVG([Customer Lifetime Value])`.

5. Drag `Category` to Rows and place `% of Total`, `Customer Lifetime Value`, and `Average Customer LTV` in the view.

6. Experiment with `INCLUDE` and `EXCLUDE`.


---

### Mini Quiz

1. What is an LOD expression?

2. What is the difference between `FIXED`, `INCLUDE`, and `EXCLUDE`?

3. Write an LOD expression that calculates total sales per customer.

4. How would you calculate the average sales per customer at the product level?

5. Why are LOD expressions useful?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Forgetting the aggregation inside LOD (e.g., `{ FIXED [Dimension] : [Measure] }` – wrong) | Always use an aggregation function inside LOD: `{ FIXED [Dimension] : SUM([Measure]) }` |
| Using LOD expressions when a table calculation would be simpler | Use LOD for fixed‑level calculations; use table calculations for relative calculations (e.g., running total) |
| Not understanding the interaction with filters – FIXED ignores some filters | Be aware that FIXED ignores dimension filters but respects data source filters |
| Overcomplicating with nested LODs | Keep LODs simple; sometimes two steps are easier |

---

### Interview Questions

1. **What is a Level of Detail (LOD) expression in Tableau?**  

   *Answer*: An LOD expression allows you to compute aggregations at a different granularity than the view's level. It uses `FIXED`, `INCLUDE`, or `EXCLUDE` to specify the level of detail.

2. **What is the difference between `FIXED` and `INCLUDE`?**  

   *Answer*: `FIXED` computes at the specified dimension(s) regardless of the view's dimensions. `INCLUDE` adds the specified dimension(s) to the view's level of detail.

3. **How would you calculate the percentage of total sales for each product?**  

   *Answer*: `SUM([Sales]) / { FIXED : SUM([Sales]) }`. The LOD gives the grand total.

---

### Assignment and Dashboard Projects

**Assignment 3.7** – Create a dashboard that demonstrates LOD expressions:

- Show each product's % of total sales (using FIXED).

- Show each product's average sales per customer (using FIXED on customer).

- Show each region's average customer lifetime value.

- For each, document the LOD expression and explain why you used it.


---

### Summary and Revision Notes

- LOD expressions compute at a different granularity.

- `FIXED` – fixed dimensions, ignores view.

- `INCLUDE` – adds dimensions to view level.

- `EXCLUDE` – removes dimensions from view level.

- Always use an aggregation function inside LOD.

- LODs are powerful but can be complex; use them when needed.

---

## Final Phase 3 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

- I can distinguish between dimensions and measures, discrete and continuous.

- I can create calculated fields with arithmetic, string, date, and logical functions.

- I can use aggregate functions correctly.

- I can apply table calculations (running total, percent of total, rank, etc.).

- I can write LOD expressions with `FIXED`, `INCLUDE`, and `EXCLUDE`.

---

### Answers to Mini Quizzes

**Lesson 3.1**: 1. Dimensions are categorical; Measures are numeric. 2. Blue (discrete) / Green (continuous). 3. It aggregates (sums by default). 4. Continuous creates a continuous axis; discrete creates headers. 5. Yes, a dimension can be continuous (e.g., continuous date); a measure can be discrete (if treated as a count).

**Lesson 3.2**: 1. In the Data pane, drop‑down → Create Calculated Field. 2. Square brackets: `[Field]`. 3. Single quotes: `'text'`. 4. `SUM([Sales]) / SUM([Quantity])`. 5. Returns the difference between two dates.

**Lesson 3.3**: 1. `LEFT(string, 5)`. 2. `DATEDIFF('day', [Start], [End])`. 3. Returns 0 if the expression is null. 4. `ROUND(number, 2)`. 5. `TODAY()`.

**Lesson 3.4**: 1. `IF` handles multiple conditions; `IIF` is for simple true/false. 2. `ISNULL([Field])`. 3. Returns the second value if the first is null. 4. `CASE [Category] WHEN "Furniture" THEN 1 ... END`. 5. Use `AND`, `OR`.

**Lesson 3.5**: 1. Summarises multiple rows into one. 2. `COUNT` counts all rows; `COUNTD` counts distinct. 3. Click the drop‑down arrow on the measure and select the aggregation. 4. `SUM([Sales]) / COUNTD([Order ID])`. 5. No – they must all be aggregated or all non‑aggregated.

**Lesson 3.6**: 1. A calculation on the aggregated result set of a view. 2. Right‑click the measure → Add Table Calculation. 3. Calculated field is row‑level; table calculation is post‑aggregation. 4. It controls direction and scope. 5. Running Total, Percent of Total, Rank.

**Lesson 3.7**: 1. An expression that computes at a different granularity. 2. `FIXED` – fixed dimensions; `INCLUDE` – adds to view; `EXCLUDE` – removes from view. 3. `{ FIXED [Customer ID] : SUM([Sales]) }`. 4. `AVG({ FIXED [Customer ID], [Product] : SUM([Sales]) })`. 5. They allow calculations at levels not present in the view.

---

**Congratulations!** You have completed Phase 3. You now have a deep understanding of Tableau's calculation engine – from basic dimensions to advanced LOD expressions. Keep practising!

---








<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>
