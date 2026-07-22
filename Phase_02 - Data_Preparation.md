# Phase 2: Data Preparation

Welcome to **Phase 2** – the foundation of great visualisations! In Phase 1, you learned to navigate Tableau and connect to data. Now, we dive into the most critical step in any analytics project: **data preparation**.

In the real world, data is never perfect. You will encounter messy column names, inconsistent formats, missing values, duplicate records, and data spread across multiple files. Tableau provides a rich set of tools – both within Tableau Desktop (on the Data Source page) and in **Tableau Prep** – to clean, shape, and combine your data.

This phase covers every essential data preparation technique you need. We start with connecting to various sources, then move through cleaning, joining, unioning, blending, pivoting, and managing metadata. By the end of this phase, you will be able to take raw, chaotic data and transform it into an analysis‑ready dataset.

Let's get our hands dirty!

---

## Lesson 2.1 – Connecting to Excel, CSV, SQL Databases, and Cloud Sources

### Concept Explanation

Before you can visualise data, you must connect to it. Tableau offers **native connectors** for a wide variety of data sources. In this lesson, we focus on the most common ones you will encounter:

- **Microsoft Excel** – spreadsheets (.xlsx, .xls). Often used for ad‑hoc reports, budget data, or small datasets.

- **CSV / Text files** – comma‑separated or tab‑separated files. Common for data exports from various systems.

- **SQL Databases** – e.g., SQL Server, MySQL, PostgreSQL, Oracle. Used for enterprise data warehouses.

- **Cloud Sources** – Snowflake, Google BigQuery, Amazon Redshift, Google Analytics, Salesforce, etc.


When you connect to a source, Tableau opens the **Data Source page**, where you can:

- Select specific tables or sheets.

- Preview the data.

- Set up relationships or joins.

- Change data types.

- Create extracts.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Data lives everywhere. Being able to connect to different sources is essential for building comprehensive dashboards. For example, you might combine sales data from a SQL database with budget data from an Excel file.

- **Use cases**:

  - A **financial analyst** connects to Excel files for monthly budget data and to SQL Server for actuals.

  - A **marketing analyst** connects to Google Analytics and Salesforce to create a unified campaign dashboard.
  
  - A **data engineer** connects to Snowflake to build enterprise‑wide dashboards.

---

### Step‑by‑Step Demonstration

**Connecting to Excel or CSV**:
1. Open Tableau Desktop. On the Start Page, under **Connect**, click **Microsoft Excel** (or **Text file** for CSV).

2. Browse and select your file.

3. In the Data Source page, you'll see the sheets/tabs (for Excel) or the file content (for CSV).

4. Drag the table(s) you need onto the canvas.

5. Click **Sheet 1** to start building visualisations.

**Connecting to SQL Server**:

1. On the Start Page, click **SQL Server**.

2. Enter the **Server** name (e.g., `localhost` or `myserver.database.windows.net`).

3. Choose **Authentication** (Windows or SQL Server).

4. Optionally, enter the **Database** name.

5. Click **Sign In**.

6. In the Data Source page, select the tables you need.

7. Click **Sheet 1**.


**Connecting to a Cloud Source (e.g., Snowflake)**:

1. On the Start Page, click **Snowflake** (or your cloud connector).

2. Enter the server details, warehouse, database, and schema.

3. Sign in with your credentials.

4. Select tables and start building.


**Connecting to Sample Data**:

- On the Start Page, under **Saved Data Sources**, click **Sample - Superstore**.

---

### Practical Examples

- **Example 1**: You have a CSV file exported from your CRM. You connect to it using the Text file connector, preview the data, and start building a customer dashboard.

- **Example 2**: Your company stores sales data in Snowflake. You connect to Snowflake, select the `Sales` and `Product` tables, and join them on the Data Source page.

---

### Hands‑on Exercises

1. Download a sample Excel file and a CSV file from the internet (or use any you have).

2. Connect to the Excel file in Tableau.

3. Connect to the CSV file in Tableau.

4. If you have access to a SQL database (or use a free tier like Azure SQL), connect to it.

5. If you have a cloud account (e.g., Google BigQuery free tier), connect to it.

6. For each connection, explore the Data Source page and preview the data.


---

### Mini Quiz

1. Which connector would you use to connect to a comma‑separated file?

2. How do you connect to a SQL Server database in Tableau?

3. What is the purpose of the Data Source page?

4. Can Tableau connect to cloud sources like Snowflake? How?

5. What is the built‑in sample dataset in Tableau?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Connecting to a file that is moved or deleted – broken data source | Store files in a consistent location; use relative paths if possible |
| Not checking the preview – assuming data is correct | Always preview data to confirm it loaded correctly |
| Using the wrong delimiter for CSV files – data misreads | In the Text File connection, specify the correct delimiter (comma, tab, semicolon) |
| Connecting to too many tables without a plan | Only connect to tables you actually need; you can always add more later |

---

### Interview Questions

1. **What data sources can Tableau connect to?**  

   *Answer*: Tableau can connect to files (Excel, CSV, PDF, etc.), databases (SQL Server, Oracle, MySQL, etc.), cloud platforms (Snowflake, BigQuery, Redshift), and web applications (Salesforce, Google Analytics).

2. **How do you connect Tableau to a CSV file?**  

   *Answer*: On the Start Page, click **Text file**, browse to the CSV, and select it. Tableau will automatically detect the delimiter.

3. **What is the Data Source page used for?**  

   *Answer*: It is used to preview data, select tables, set up joins, change data types, and prepare data before building visualisations.

---

### Assignment and Dashboard Projects

**Assignment 2.1** – Connect to three different data sources:

- One Excel file.

- One CSV file.

- One database or cloud source (if available).

- Document the steps for each connection and save a screenshot of the Data Source page.

---

### Summary and Revision Notes

- Tableau connects to files, databases, and cloud platforms.

- Use the **Start Page** to select a connector.

- The **Data Source page** is where you preview and prepare data.

- Sample - Superstore is the built‑in dataset for practice.

---

## Lesson 2.2 – Understanding Data Types

### Concept Explanation

Data types tell Tableau how to interpret and handle each field. Choosing the correct data type is critical because it determines what operations you can perform and how Tableau visualises the data.

**Key data types in Tableau**:

| **Data Type** | **Icon** | **Description** | **Example** |
|---------------|----------|-----------------|-------------|
| **String** | Abc | Text values | "Product A", "John Doe" |
| **Number (whole)** | # | Integer | 42, 100 |
| **Number (decimal)** | # (with decimals) | Float | 3.14, 99.99 |
| **Date** | Calendar | Date values | 2025-01-15 |
| **Date & Time** | Clock | Timestamp | 2025-01-15 14:30:00 |
| **Boolean** | T/F | True/False | TRUE, FALSE |
| **Geographic** | Globe | Map‑ready location | "United States", "New York" |

**Dimensions vs Measures**:

- **Dimensions** are typically categorical (strings, dates, booleans) and are used to slice data.

- **Measures** are typically numeric and are used to aggregate (sum, average, count, etc.).


**Changing data types**:

- In the Data Source page, click the data type icon next to a field name and select the correct type.

- In a worksheet, right‑click a field → **Change Data Type**.

---

### Importance and Real‑World Use Cases

- **Why it matters**: If Tableau misinterprets a numeric field as a string, you cannot sum it. If a date is imported as a string, you cannot use time intelligence. Correct data types are the foundation of accurate analysis.

- **Use cases**:

  - A **sales analyst** ensures that `Sales` is a number and `Order Date` is a date, so they can calculate monthly totals.

  - A **geospatial analyst** sets `Country` as a geographic role to create maps.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. In the Data Source page, look at the data types next to each field name (icons).

3. Notice that `Sales` is a number (#), `Order Date` is a date (calendar), and `Category` is a string (Abc).

4. Click the data type icon for `Sales` – you can change it to a different number format or to a string (though you wouldn't normally).

5. In a worksheet, right‑click `Order Date` → **Change Data Type** → **Date & Time** – it changes to a timestamp.

**Setting Geographic Roles**:

1. Right‑click `Country` in the Data pane → **Geographic Role** → **Country/Region**.

2. Now Tableau knows this field contains country names and can be used on maps.

---

### Practical Examples

- **Example 1**: You import a CSV where a numeric column has a dollar sign (`$1,000`). Tableau might import it as a string. You use **Data Interpreter** (Lesson 2.3) or manually clean it to convert to a number.

- **Example 2**: You have a `Date` column but Tableau imports it as a string because of formatting. You change the data type to Date to enable time‑based analysis.

---

### Hands‑on Exercises

1. Connect to Sample - Superstore.

2. In the Data Source page, identify the data types of all fields.

3. Change `Profit` to a number (if it isn't already) – it should already be one.

4. Change `Order Date` to **Date & Time** and observe the change.

5. Set `Country` to **Geographic Role → Country/Region**.

6. Create a worksheet and drag `Country` to the canvas – Tableau will create a map!


---

### Mini Quiz

1. What data type icon represents a string in Tableau?

2. What is the difference between a dimension and a measure?

3. How do you change a field's data type in the Data Source page?

4. What geographic role would you assign to a field containing city names?

5. Why is it important to set correct data types?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Leaving numbers as strings – cannot perform calculations | Change numeric fields to Number data types |
| Leaving dates as strings – cannot use time intelligence | Always set date fields to Date or Date & Time |
| Not assigning geographic roles – maps won't work | Assign geographic roles to location fields |
| Changing data types in the wrong place – inconsistent | Use the Data Source page for one‑time fixes; use the Data pane for on‑the‑fly changes |

---

### Interview Questions

1. **What are the main data types in Tableau and when would you use each?**  

   *Answer*: String (text), Number (whole and decimal), Date, Date & Time, Boolean (true/false), Geographic (locations). Use strings for labels, numbers for calculations, dates for time analysis, and geographic for maps.

2. **What is the difference between a dimension and a measure?**  

   *Answer*: Dimensions are categorical fields used to slice and group data (e.g., Product, Region). Measures are numeric fields that can be aggregated (e.g., Sales, Profit).

3. **How do you assign a geographic role to a field?**  

   *Answer*: Right‑click the field in the Data pane → **Geographic Role** → select the appropriate role (e.g., City, State, Country/Region).

---

### Assignment and Dashboard Projects

**Assignment 2.2** – Load a new dataset (e.g., a CSV with sales data). 

- Identify all fields and their data types.

- Correct any incorrect data types.

- Assign geographic roles to any location fields.

- Save the workbook and document your changes.


---

### Summary and Revision Notes

- Data types: String, Number, Date, Date & Time, Boolean, Geographic.

- Dimensions are categorical; Measures are numeric.

- Correct data types are essential for calculations and visualisations.

- Change data types in the Data Source page or the Data pane.

---

## Lesson 2.3 – Data Interpreter

### Concept Explanation

**Data Interpreter** is a powerful Tableau feature that automatically detects and cleans messy Excel files. It removes extra headers, footers, blank rows, and other "noise" to extract the clean data table.

**When to use Data Interpreter**:

- The Excel file has multiple sheets with inconsistent formatting.


- There are extra rows (titles, footnotes, empty rows) above the actual data.

- The data doesn't start in cell A1.

**How it works**: Data Interpreter analyses the structure of the Excel file and identifies the clean data table(s) within it, ignoring anything that doesn't look like structured data.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Many business users create Excel files with formatting that isn't "table‑friendly". Data Interpreter saves hours of manual cleaning.

- **Use cases**:

  - You receive a monthly sales report from a colleague. The file has a title row, a blank row, a subtitle, and then the data. Data Interpreter extracts just the data.

  - You connect to an Excel file exported from an old system that includes headers and footers. Data Interpreter removes them.

---

### Step‑by‑Step Demonstration

1. Open an Excel file that has messy formatting (e.g., a title row above the data).

2. In Tableau, connect to the Excel file.

3. In the Data Source page, look for the **Use Data Interpreter** checkbox in the top‑left corner.

4. Check the box **Use Data Interpreter**.

5. Tableau processes the file and shows the cleaned data.

6. You can now drag the interpreted table onto the canvas.

7. To see what was removed, click **View Data Interpreter Results** – it shows a summary of what was discarded.

---

### Practical Examples

- **Example 1**: You receive an Excel file with "Sales Report 2025" in cell A1, a blank row, "Prepared by: John" in cell A2, and then the headers in row 3. Data Interpreter removes the first two rows and starts at row 3.

- **Example 2**: An Excel file has a footer with "Confidential" at the bottom. Data Interpreter removes it.

---

### Hands‑on Exercises

1. Create a messy Excel file: add a title row, a blank row, a subtitle, and then a clean data table.

2. Connect to this file in Tableau.

3. Observe that Tableau shows the messy data with extra rows.

4. Check **Use Data Interpreter** and observe the cleaned data.

5. Click **View Data Interpreter Results** to see what was removed.


---

### Mini Quiz

1. What is the Data Interpreter in Tableau used for?

2. How do you enable Data Interpreter?

3. What types of "noise" does Data Interpreter remove?

4. Can Data Interpreter be used on CSV files?

5. How can you see what Data Interpreter removed?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Assuming Data Interpreter works on all files – it works best on Excel files | Use Data Interpreter primarily for Excel files; for CSVs, use manual cleaning |
| Not checking the results – assuming everything is correct | Always verify the cleaned data and check the Interpreter results |
| Relying on Data Interpreter for complex cleaning – it's a helper, not a full ETL tool | Use Data Interpreter for quick fixes, but use Tableau Prep for complex transformations |

---

### Interview Questions

1. **What is the Data Interpreter in Tableau?**  

   *Answer*: It is a feature that automatically cleans messy Excel files by removing extra headers, footers, blank rows, and other non‑data content to extract the clean table.

2. **When would you use Data Interpreter?**  

   *Answer*: When connecting to Excel files that have inconsistent formatting or extra rows/columns that are not part of the actual data.

3. **Can Data Interpreter be used on PDFs?**  

   *Answer*: Data Interpreter is primarily designed for Excel files; for PDFs, Tableau has a separate PDF connector but it is less robust.

---

### Assignment and Dashboard Projects

**Assignment 2.3** – Find a messy Excel file (or create one). Connect to it in Tableau, enable Data Interpreter, and document:

- What Data Interpreter removed.

- Whether any additional cleaning is needed.

- Save the cleaned data as a new data source.


---

### Summary and Revision Notes

- Data Interpreter cleans messy Excel files automatically.

- Enables you to skip extra headers, footers, and blank rows.

- Enable it via the checkbox on the Data Source page.

- Always verify the results.

---

## Lesson 2.4 – Cleaning Data

### Concept Explanation

Data cleaning (or data scrubbing) is the process of fixing or removing incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data. Tableau provides several tools for cleaning data:

**Common cleaning tasks**:

1. **Removing duplicates** – identify and remove duplicate rows.

2. **Handling null values** – replace nulls with a default value (e.g., 0, "Unknown") or filter them out.

3. **Removing extra spaces** – trim leading/trailing spaces (using Tableau Prep).

4. **Filtering out unwanted rows** – remove rows that don't meet criteria.

5. **Splitting fields** – split a field (e.g., "John Doe" into "John" and "Doe").

6. **Replacing values** – correct typos (e.g., "USA" vs "U.S.A").

**Cleaning in Tableau**:

- **Data Source page**: You can filter data, rename fields, and change data types. For more advanced cleaning, you need Tableau Prep.

- **Tableau Prep**: A dedicated tool for visual data preparation with a rich set of cleaning operations.

In this lesson, we focus on cleaning within Tableau Desktop (Data Source page) and introduce Tableau Prep concepts.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Dirty data leads to wrong calculations and broken relationships. A 2023 survey found that data quality issues cost organisations an average of $12.9 million per year. Cleaning ensures data integrity.


- **Use cases**:

  - A **sales analyst** removes duplicate orders to avoid double‑counting revenue.

  - A **marketing analyst** replaces null values in the `Campaign` column with "Unknown" so they can still group campaigns.

  - A **data engineer** uses Tableau Prep to split a `Full Name` field into `First Name` and `Last Name`.


---

### Step‑by‑Step Demonstration

**Cleaning in the Data Source page**:

1. **Filtering rows**:

   - In the Data Source page, click the drop‑down arrow on a field → **Filter**.

   - Select values to keep or exclude.


2. **Renaming fields**:

   - Double‑click a field name and type a new name.


3. **Changing data types**:

   - Click the data type icon and select a new type.


4. **Splitting fields** (only available in Tableau Prep or via custom calculations):

   - In a worksheet, you can use a calculated field: `SPLIT([Full Name], " ", 1)` for first name.


**Cleaning with Tableau Prep**:

1. Open Tableau Prep.

2. Connect to your data source.

3. Add a **Clean Step**.

4. Use the **Drop** option to remove duplicates.

5. Use the **Replace** option to replace nulls.

6. Use the **Split** option to split a field.

7. Run the flow and output the cleaned data to a file or Tableau Server.

---

### Practical Examples

- **Example 1**: You have a `Country` field with values "USA", "U.S.A.", "United States". You use **Replace** in Tableau Prep to standardise them to "USA".


- **Example 2**: You have a `Sales` field with null values. You replace nulls with 0 so that totals are not affected.

---

### Hands‑on Exercises

1. Load a dataset with some messiness (e.g., duplicates, nulls, typos).

2. In the Data Source page, filter out rows where `Sales` is null.

3. Rename `Customer ID` to `Customer ID (Unique)`.

4. Change `Order Date` to Date data type.

5. If you have Tableau Prep, create a flow to:

   - Remove duplicate rows.

   - Replace nulls in the `Region` field with "Unknown".

   - Split a `Full Name` field into two fields.

6. Save the cleaned data.


---

### Mini Quiz

1. What is the purpose of data cleaning?

2. How do you filter rows in the Data Source page?

3. How do you rename a field in the Data Source page?

4. What is Tableau Prep used for?

5. How would you replace null values in a field?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Cleaning data in a worksheet instead of the data source – changes are not reusable | Clean data at the data source level so all worksheets benefit |
| Not documenting cleaning steps – hard to reproduce | Use Tableau Prep to visually document each step |
| Over‑cleaning – removing rows that are actually valid | Always validate with business users before removing data |
| Not handling nulls – calculations break | Decide on a strategy for nulls (remove, replace, or keep) |

---

### Interview Questions

1. **What is your process for cleaning data in Tableau?**  

   *Answer*: I start by profiling the data to understand its quality. I use Tableau Prep for most cleaning tasks – removing duplicates, handling nulls, standardising values, and splitting fields. I document each step and validate with business users.

2. **How do you handle null values in Tableau?**  

   *Answer*: I can replace nulls with a default value (e.g., 0, "Unknown") using Tableau Prep, or I can filter them out if they are not needed. In Tableau Desktop, I can use `ZN()` or `IFNULL()` in calculated fields.

3. **What is the difference between cleaning in Tableau Desktop and Tableau Prep?**  

   *Answer*: Tableau Desktop's Data Source page offers basic cleaning (filtering, renaming, data types). Tableau Prep provides a visual, step‑by‑step interface for complex cleaning tasks like splitting, pivoting, aggregating, and joining.

---

### Assignment and Dashboard Projects

**Assignment 2.4** – Take a messy dataset and perform a complete cleaning process:

- Identify duplicates and remove them.

- Handle nulls (replace or remove).

- Standardise inconsistent values.

- Split any combined fields.

- Save the cleaned data as a new data source.

- Document each step.


---

### Summary and Revision Notes

- Data cleaning is essential for accurate analysis.

- Use the Data Source page for basic cleaning (filtering, renaming, data types).

- Use **Tableau Prep** for advanced cleaning (duplicates, nulls, splits, replacements).

- Always document and validate your cleaning steps.

---

## Lesson 2.5 – Data Joins

### Concept Explanation

**Joins** combine two tables by matching values in one or more columns. This is how you bring related data together – for example, combining a Sales table with a Product table.

**Join types in Tableau**:

| **Join Type** | **Description** | **Result** |
|---------------|-----------------|------------|
| **Inner Join** | Keeps only rows with matching values in both tables | All matching rows from both tables |
| **Left Join** | Keeps all rows from the left table, matching rows from the right | All left rows + matched right rows |
| **Right Join** | Keeps all rows from the right table, matching rows from the left | All right rows + matched left rows |
| **Full Outer Join** | Keeps all rows from both tables | All rows from both, matching where possible |

**Setting up a Join in Tableau**:

1. In the Data Source page, drag two tables onto the canvas.

2. A join icon appears between them.

3. Click the join icon to open the join dialog.

4. Select the **Join Type** (Inner, Left, Right, Full Outer).

5. Select the **Join Clause**: which fields to match on (e.g., `Sales[ProductID] = Products[ProductID]`).

6. You can add multiple join clauses.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Data is rarely in a single table. Joins enable you to combine data from different sources into a unified view, enriching your analysis.

- **Use cases**:

  - A **sales dashboard** joins Sales (fact) with Products (dimension) to show product names instead of IDs.

  - A **customer analysis** joins Orders with Customers to bring customer demographics into the transaction data.

  - A **financial report** joins Actuals with Budget on account and period.


---

### Step‑by‑Step Demonstration

1. Connect to Sample - Superstore.

2. In the Data Source page, you'll see a single table.

3. Connect to another data source (e.g., a separate Excel file with product categories).

4. Drag the new table onto the canvas.

5. Click the join icon (the overlapping circles).

6. In the join dialog:

   - Select **Left Join**.

   - Match `Product ID` from the main table to `Product ID` from the second table.

7. Click **OK**.

8. The tables are now joined. You can bring in fields from both tables.


---

### Practical Examples

- **Example 1**: You have a `Sales` table with `ProductID`. You join it with a `Products` table on `ProductID` to add `ProductName` and `Category` to each sale.

- **Example 2**: You have a `Customers` table and a `Orders` table. A **Left Join** keeps all customers, even those with no orders, showing nulls in the Orders fields for those customers.

---

### Hands‑on Exercises

1. Use Sample - Superstore as your main table.

2. Create a small Excel file with `Product ID` and `Category` (or use the Superstore's built‑in dimensions if you can).

3. Connect to this Excel file in the same Data Source page.

4. Perform a **Left Join** between the main table and the Excel file on `Product ID`.

5. Perform an **Inner Join** and note the row count difference.

6. Perform a **Full Outer Join** and observe the results.


---

### Mini Quiz

1. What is the purpose of a join in Tableau?

2. What are the four types of joins?

3. Which join keeps all rows from the left table?

4. How do you set up a join in Tableau?

5. What is a join clause?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using an Inner Join when you need a Left Join – losing data | Think about which table is the "main" table and use Left Join to preserve it |
| Joining on fields with different data types – no matches | Ensure the fields in the join clause have the same data type |
| Not checking join results – data may be missing or duplicated | After joining, check the row count and sample data |
| Joining on non‑unique keys – causing duplicates | Ensure the key on the "one" side is unique |

---

### Interview Questions

1. **What is the difference between an Inner Join and a Left Join?**  

   *Answer*: An Inner Join returns only rows that have matching values in both tables. A Left Join returns all rows from the left table and matching rows from the right; non‑matching rows from the right show null values.

2. **How do you set up a join in Tableau?**  

   *Answer*: In the Data Source page, drag two tables onto the canvas, click the join icon, select the join type, and define the join clause(s).

3. **What happens if you join on fields that are not unique?**  

   *Answer*: The join will produce duplicate rows (Cartesian product) for each matching combination, which can inflate your data incorrectly.

---

### Assignment and Dashboard Projects

**Assignment 2.5** – Create a joined data source:

- Take two related datasets (e.g., Sales and Products, or Orders and Customers).

- Perform a Left Join and build a dashboard using fields from both tables.

- Document the join type and why you chose it.


---

### Summary and Revision Notes

- Joins combine tables by matching columns.

- Types: Inner, Left, Right, Full Outer.

- Left Join is the most common – preserves all rows from the "main" table.

- Join clauses define which columns to match on.

- Always verify join results.

---

## Lesson 2.6 – Data Unions

### Concept Explanation

**Unions** stack rows from two or more tables on top of each other, combining them into a single table. This is useful when you have the same data spread across multiple files or sheets (e.g., monthly sales files).

**Union requirements**:

- Tables must have the same number of columns.

- Columns must have similar data types and names (Tableau matches by name).

**Setting up a Union**:

1. In the Data Source page, drag your first table onto the canvas.

2. Drag a second table onto the canvas and hover until the **Union** option appears.

3. Or, double‑click **New Union** below the table.

4. Add tables to the union.

5. Tableau will automatically match columns by name. You can manually adjust if needed.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Data often arrives in chunks – monthly files, regional files, or historical exports. Unions combine them into a unified dataset for analysis.

- **Use cases**:

  - A **retail analyst** has monthly sales CSVs (Jan, Feb, Mar). They union them to create a yearly dataset.

  - A **marketing analyst** has separate Excel sheets for each campaign. They union them to analyse all campaigns together.

  - A **finance analyst** has quarterly budget files. They union them to create a yearly budget.


---

### Step‑by‑Step Demonstration

1. Create three Excel files with the same structure (e.g., `Sales_Jan.xlsx`, `Sales_Feb.xlsx`, `Sales_Mar.xlsx`) – each with columns: `Date`, `Product`, `Sales`.

2. In Tableau, connect to the folder containing these files (or add them individually).

3. In the Data Source page, drag `Sales_Jan` onto the canvas.

4. Drag `Sales_Feb` below it – the union option appears. Drop it.


5. Drag `Sales_Mar` similarly.

6. Tableau creates a unioned table with all rows from all files.

7. You can now analyse the combined data.

**Automatic Union of Files in a Folder**:

- Instead of adding each file, you can connect to the **folder** and Tableau will automatically union all files with the same structure.

---

### Practical Examples

- **Example 1**: You have 12 monthly sales CSV files. You connect to the folder, and Tableau unions them automatically, adding a `File Name` field to identify the source.

- **Example 2**: You have separate Excel sheets for each region (North, South, East, West). You union them to create a single `AllRegions` table.

---

### Hands‑on Exercises

1. Create three small Excel files with identical columns (e.g., `Date`, `Product`, `Sales`) – each with different data.

2. In Tableau, connect to the folder containing these files.

3. Drag the folder onto the canvas – Tableau automatically unions them.

4. Alternatively, drag each file individually and union them.

5. Observe the combined data.


---

### Mini Quiz

1. What is a union in Tableau?

2. What are the requirements for tables to be unioned?

3. How do you union tables in Tableau?

4. What is the advantage of connecting to a folder of files?

5. Does Tableau automatically add a field to identify the source file in a union?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Unioning tables with different column names – creates separate columns | Ensure column names are identical across files |
| Unioning tables with different data types – causes errors | Standardise data types across files before unioning |
| Manually adding each file instead of using a folder | Use the **folder** connection for automatic union of all files |
| Not checking the union result – missing data or misaligned columns | Preview the unioned table and verify the column structure |

---

### Interview Questions

1. **What is the difference between a join and a union?**  

   *Answer*: A join combines columns from two tables horizontally (by matching rows). A union combines rows from two tables vertically (stacking them).

2. **How do you union files in a folder in Tableau?**  

   *Answer*: Connect to the folder, and Tableau will automatically detect and union all files with the same structure. You can also manually add files.

3. **What happens if the files in a union have different column names?**  

   *Answer*: Tableau will treat them as separate columns. You should rename columns to match before unioning, or use the "Custom" union to map columns.

---

### Assignment and Dashboard Projects

**Assignment 2.6** – Create a unioned data source:

- Create at least 3 monthly sales files with the same structure.

- Union them in Tableau (either by folder or manually).

- Add a calculated field to extract the month from the `Date` column.

- Build a line chart showing sales trends across the months.

---

### Summary and Revision Notes

- Unions stack rows vertically.

- Tables must have the same column structure.

- Use the **folder** connector for automatic union of multiple files.

- Tableau adds a `File Name` or `Table Name` field to identify the source.


---

## Lesson 2.7 – Data Blending

### Concept Explanation

**Data Blending** is a Tableau feature that allows you to combine data from **different data sources** in a single view. Unlike joins (which merge data at the row level in the Data Source page), blending merges data at the **visualisation level** – Tableau queries each source separately and combines the results in the worksheet.


**Key concepts**:

- **Primary data source** – the main data source (identified by a blue checkmark in the Data pane).

- **Secondary data source** – additional data sources (identified by an orange checkmark).

- **Blend fields** – the fields used to link the sources (must have the same name and data type).

- **Aggregation** – blends require aggregation (measures are summed before blending).

**When to use Blending vs Joins**:

| **Blending** | **Joins** |
|--------------|-----------|
| Different data sources (e.g., SQL Server + Excel) | Same data source (e.g., two tables in the same database) |
| Different levels of granularity | Same grain |
| Data sources are updated independently | Data is combined at the source |
| Performance can be slower | Performance is usually faster |

---

### Importance and Real‑World Use Cases

- **Why it matters**: In real organisations, data lives in silos – sales in SQL Server, budgets in Excel, marketing data in Google Analytics. Blending allows you to bring them together without complex ETL.

- **Use cases**:

  - A **financial analyst** blends actual sales (SQL Server) with budget (Excel) to compare performance.

  - A **marketing analyst** blends Google Analytics data (web) with Salesforce data (cloud) to track leads from ad clicks.

  - A **retail analyst** blends store sales (database) with demographic data (CSV) to analyse regional performance.


---

### Step‑by‑Step Demonstration

1. Connect to your **primary data source** (e.g., Sample - Superstore).

2. Build a worksheet using a field from this source (e.g., drag `Sales` to Columns, `Region` to Rows).

3. Click **Data** → **Edit Data Sources** → **Add** a secondary data source (e.g., an Excel file with budget data).

4. In the secondary data source, create the necessary fields.

5. In your worksheet, drag a field from the secondary data source to the view (e.g., `Budget`).

6. Tableau prompts you to define a blend relationship – select the common field (e.g., `Region`).

7. Tableau blends the data and shows the combined result.


**Important**: The blend field in the primary source must be a dimension (blue). The secondary source must also have a field with the same name and data type.

---

### Practical Examples

- **Example 1**: You have a `Sales` table in SQL Server (primary) and a `Budget` table in Excel (secondary). You blend on `Region` to compare actual sales vs budget per region.

- **Example 2**: You have `Customer` data in Salesforce (primary) and `Website Visits` in Google Analytics (secondary). You blend on `Email` to see which customers visited the website.

---

### Hands‑on Exercises

1. Connect to Sample - Superstore as your primary data source.

2. Create a simple Excel file with `Region` and `Budget` values (e.g., East: 1000, West: 1200, South: 900, Central: 1100).

3. Add this Excel file as a secondary data source.

4. In a worksheet, create a bar chart showing `Sales` by `Region` (from Superstore).

5. Drag `Budget` (from the Excel file) onto the Rows shelf.

6. Define the blend on `Region`.

7. Observe the blended chart showing both Sales and Budget by Region.


---

### Mini Quiz

1. What is data blending in Tableau?

2. What is the difference between data blending and joins?

3. How do you identify the primary data source in a blend?

4. What is a blend field?

5. Why do blends require aggregation?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Blending on fields that have different names – no match | Ensure blend fields have identical names |
| Using a secondary data source at a different level of granularity | Align the grain of both sources as much as possible |
| Expecting blends to work like joins – they don't, and performance may be slower | Use joins when data is in the same source; use blends only when necessary |
| Forgetting to set the field as a dimension (blue) in the primary source | The blend field must be a dimension (blue) in the primary source |

---

### Interview Questions

1. **What is the difference between data blending and a join?**  

   *Answer*: A join combines data at the row level in the Data Source page, creating a single table. Blending combines data at the visualisation level, querying each source separately and then aggregating the results. Blending is used for different data sources; joins are for the same data source.

2. **When would you use data blending over a join?**  

   *Answer*: When the data comes from different sources (e.g., SQL Server and Excel), or when the data is at different levels of granularity and you want to avoid duplication.

3. **How do you set up a data blend in Tableau?**  

   *Answer*: Add a secondary data source, then drag a field from it into the view. Tableau will prompt you to define the blend relationship on common fields.

---

### Assignment and Dashboard Projects

**Assignment 2.7** – Create a blended data source:

- Primary: Sample - Superstore.

- Secondary: An Excel file with `Region` and `Target` (target sales).

- Blend on `Region`.

- Build a dashboard showing actual sales vs target by region.

- Document the blending process.

---

### Summary and Revision Notes

- Data blending combines data from different sources at the visualisation level.

- Primary source (blue) and secondary source (orange).

- Blend fields must have the same name and be dimensions in the primary source.

- Blends aggregate data; they are not row‑level joins.

---

## Lesson 2.8 – Pivoting Data

### Concept Explanation

**Pivoting** in Tableau is the process of reshaping your data by turning **columns into rows** (unpivot) or **rows into columns** (pivot). This is essential because Tableau works best with **tidy data** – where each row is an observation and each column is a variable.

**Two operations**:

1. **Unpivot** (Pivot in Tableau) – Takes multiple columns and transforms them into two columns: a `Pivot Field Names` column (the original column names) and a `Pivot Field Values` column (the values). This converts wide data to narrow/long data.

   *Example*: `Year`, `Q1`, `Q2`, `Q3`, `Q4` → `Year`, `Quarter`, `Sales`

2. **Pivot** (the reverse) – Takes a long table and spreads values from a column into multiple columns (wide data). This is less common but useful for certain presentations.

**Why pivot (unpivot)**:

- Tableau is optimised for long, narrow tables.

- Long tables are easier to filter, group, and aggregate.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Many business reports are formatted for human reading (wide format). For analysis, you need long format. Unpivoting is one of the most common data preparation tasks.

- **Use cases**:

  - You receive a budget file with columns: `Department`, `Jan`, `Feb`, `Mar`, ... You unpivot to get `Department`, `Month`, `Budget`.

  - You have survey data with columns for each question. You unpivot to get `Respondent`, `Question`, `Score`.

  - You have sales data with columns for each product. You unpivot to get `Date`, `Product`, `Sales`.

---

### Step‑by‑Step Demonstration

**Unpivot (Pivot) in Tableau Prep**:

1. Open Tableau Prep.

2. Connect to your data source.

3. Add a **Pivot** step.

4. Select the columns you want to pivot (e.g., `Jan`, `Feb`, `Mar`).

5. Choose **Pivot to Rows**.

6. Specify the new column names (e.g., `Month`, `Sales`).

7. The data is now in long format.


**Unpivot in Tableau Desktop (Data Source page)**:
1. In the Data Source page, select multiple columns (e.g., `Q1`, `Q2`, `Q3`, `Q4`).

2. Right‑click and select **Pivot**.

3. Tableau creates two new columns: `Pivot Field Names` and `Pivot Field Values`.

4. Rename them to something meaningful (e.g., `Quarter`, `Sales`).

**Pivot (rows to columns) in Tableau Desktop**:

- This is less common. You can use a pivot table or crosstab in a worksheet.

---

### Practical Examples

- **Example 1**: A budget file has `Department` and 12 monthly columns. You unpivot to create `Month` and `Budget Amount` columns, enabling trend analysis.

- **Example 2**: A survey file has columns `Q1`, `Q2`, `Q3`, `Q4`. You unpivot to create `Question` and `Score` columns, enabling you to calculate average scores per question.

---

### Hands‑on Exercises

1. Create a wide dataset in Excel: `Product`, `Jan_Sales`, `Feb_Sales`, `Mar_Sales`.

2. Load it into Tableau Prep.

3. Add a Pivot step, select the three month columns, and pivot to rows.

4. Rename the new columns to `Month` and `Sales`.

5. Load the pivoted data into Tableau Desktop.

6. Create a line chart showing sales by month.


---

### Mini Quiz

1. What is pivoting in Tableau?

2. What is the difference between pivot and unpivot?

3. Why is unpivoting important for Tableau analysis?

4. How do you pivot columns to rows in Tableau Prep?

5. Can you pivot rows to columns in Tableau Desktop?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Pivoting columns that are not of the same type – mixing numbers and text | Ensure all selected columns have the same data type |
| Not renaming the pivot columns – leaving generic names | Rename to business‑friendly names (e.g., `Month`, `Sales`) |
| Pivoting too many columns – creating a very long table | Only pivot the columns you actually need |
| Forgetting to pivot dates – leaving them as strings | Ensure date columns are correctly typed before or after pivoting |

---

### Interview Questions

1. **What is the purpose of pivoting data in Tableau?**  

   *Answer*: Pivoting transforms wide data (many columns) into long data (fewer columns with more rows). Tableau is optimised for long data, making it easier to filter, group, and aggregate.

2. **How do you unpivot data in Tableau?**  

   *Answer*: In the Data Source page, select the columns you want to pivot, right‑click, and select **Pivot**. In Tableau Prep, add a Pivot step and choose **Pivot to Rows**.

3. **When would you use pivoting?**  

   *Answer*: When you have data structured for reporting (e.g., months as columns) and need to analyse it over time, or when you have survey data with columns for each question.

---

### Assignment and Dashboard Projects

**Assignment 2.8** – Take a wide dataset (e.g., monthly sales or quarterly budgets) and pivot it to long format. Build a line chart showing the trend over time. Document the before‑and‑after structure.

---

### Summary and Revision Notes

- Pivoting turns columns into rows (unpivot) – the most common operation.

- Use **Tableau Prep** or the **Data Source page** to pivot.

- Long format is preferred for Tableau analysis.

- Rename pivot columns for clarity.

---

## Lesson 2.9 – Managing Metadata

### Concept Explanation

**Metadata** is "data about data" – it describes the structure, meaning, and characteristics of your data. In Tableau, metadata management involves:

1. **Renaming fields** – giving fields business‑friendly names.

2. **Assigning aliases** – changing how values appear (e.g., "M" to "Male").

3. **Setting default properties** – defining default aggregation (e.g., "Sum" vs "Average"), colour palette, and number format.

4. **Organising fields** – grouping fields into folders.

5. **Adding descriptions** – explaining what each field means.

6. **Hiding fields** – removing unused fields from the Data pane.

**Where to manage metadata**:

- **Data Source page**: Rename fields, change data types.

- **Data pane** (in a worksheet): Right‑click a field to set aliases, default properties, or hide it.

- **Tableau Prep**: Rename fields and add descriptions.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Metadata makes your data understandable to others. A field named `COGS` might mean nothing to a business user, but "Cost of Goods Sold" is clear. Good metadata reduces confusion and speeds up dashboard development.

- **Use cases**:

  - A **data analyst** renames `Cust_ID` to `Customer ID` for clarity.

  - A **dashboard designer** assigns aliases to `Region` values: "E" → "East", "W" → "West".

  - A **finance team** sets default number formatting to Currency for all monetary fields.


---

### Step‑by‑Step Demonstration

**Renaming a Field**:

- In the Data Source page, double‑click the field name and type a new name.
- Or, in the Data pane, right‑click the field → **Rename**.

**Assigning Aliases to Values**:

1. In the Data pane, right‑click a dimension (e.g., `Region`).

2. Select **Aliases**.

3. In the dialog, enter aliases for each value (e.g., "E" → "East").

4. Click **OK**.

**Setting Default Aggregation**:

1. Right‑click a measure (e.g., `Sales`).

2. Select **Default Properties** → **Aggregation**.

3. Choose `Sum`, `Average`, `Count`, etc.

4. Now every time you drag `Sales` into a view, it will use that aggregation by default.

**Organising Fields into Folders**:

1. In the Data pane, right‑click → **Create Folder**.

2. Drag fields into the folder.

**Hiding a Field**:

1. Right‑click the field → **Hide**.

2. The field disappears from the Data pane (but still exists; you can unhide it later).

---

### Practical Examples

- **Example 1**: You have a field `P_Code` with values "1", "2", "3". You rename it to `Product Code` and assign aliases "1" → "Electronics", "2" → "Furniture", "3" → "Office Supplies".

- **Example 2**: You have a `Sales` field. You set its default aggregation to **Sum** and default number format to **Currency**.

---

### Hands‑on Exercises

1. Connect to Sample - Superstore.

2. Rename `Sub-Category` to `Sub Category`.

3. Assign aliases to `Region`: "East" → "Eastern", "West" → "Western", "South" → "Southern", "Central" → "Central".

4. Set `Profit` to default aggregation **Average**.

5. Create a folder called "Financials" and drag `Sales`, `Profit`, and `Discount` into it.

6. Hide `Postal Code` (if you don't need it).


---

### Mini Quiz

1. What is metadata in Tableau?

2. How do you rename a field in Tableau?

3. What are aliases used for?

4. How do you set a default aggregation for a measure?

5. Why would you hide a field?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not renaming fields – users don't understand them | Always use business‑friendly names |
| Not using aliases – inconsistent value labels | Use aliases to standardise how values are displayed |
| Changing default aggregation without thinking – may mislead users | Set defaults carefully (e.g., Sales = Sum, Price = Average) |
| Not organising fields – the Data pane becomes cluttered | Use folders to group related fields |

---

### Interview Questions

1. **How do you manage metadata in Tableau?**  

   *Answer*: I use the Data Source page and Data pane to rename fields, assign aliases, set default aggregations and formatting, organise fields into folders, and hide unused fields. This makes the data source more intuitive for users.

2. **What is the difference between renaming a field and using an alias?**  

   *Answer*: Renaming changes the field name itself. An alias changes how the values within that field are displayed in the view, without changing the underlying data.

3. **Why is metadata management important?**  

   *Answer*: It makes data understandable to business users, reduces confusion, speeds up dashboard development, and ensures consistent reporting.

---

### Assignment and Dashboard Projects

**Assignment 2.9** – Take a dataset and perform a full metadata cleanup:

- Rename all fields to business‑friendly names.

- Assign aliases to at least two dimensions.

- Set default aggregations for all measures.

- Group related fields into folders.

- Hide any unnecessary fields.

- Save the workbook and document your changes.


---

### Summary and Revision Notes

- Metadata = data about data.

- Key tasks: renaming, aliases, default properties, folders, hiding.

- Rename fields for clarity.

- Use aliases to standardise value display.

- Set default aggregations and formatting.

- Organise fields into folders.

---

## Final Phase 2 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist
-  I can connect to Excel, CSV, SQL databases, and cloud sources.

-  I understand and can change data types in Tableau.

-  I can use Data Interpreter to clean messy Excel files.

-  I can perform data cleaning (duplicates, nulls, filtering, splitting).

-  I can set up and perform Inner, Left, Right, and Full Outer joins.

-  I can union multiple tables.

-  I understand data blending and can set it up.

-  I can pivot data (unpivot) to transform wide to long format.

-  I can manage metadata (renaming, aliases, default properties).

---

### Answers to Mini Quizzes

**Lesson 2.1**: 1. Text file. 2. Start Page → SQL Server. 3. To preview and prepare data. 4. Yes, via connectors. 5. Sample - Superstore.

**Lesson 2.2**: 1. Abc. 2. Dimensions are categorical; Measures are numeric. 3. Click the data type icon. 4. City. 5. To enable correct calculations and visualisations.

**Lesson 2.3**: 1. To clean messy Excel files. 2. Check the Use Data Interpreter box. 3. Headers, footers, blank rows. 4. No, it's for Excel. 5. Click View Data Interpreter Results.

**Lesson 2.4**: 1. To fix or remove incorrect, duplicate, or incomplete data. 2. Click the drop‑down arrow on a field → Filter. 3. Double‑click the field name. 4. Data preparation. 5. Use Replace in Tableau Prep.

**Lesson 2.5**: 1. To combine tables by matching columns. 2. Inner, Left, Right, Full Outer. 3. Left Join. 4. Drag tables to canvas, click join icon, select type and clause. 5. The condition that matches columns.

**Lesson 2.6**: 1. Stacking rows vertically. 2. Same number of columns and similar data types. 3. Drag tables together or use New Union. 4. It automatically unions all files. 5. Yes, it adds a File Name field.

**Lesson 2.7**: 1. Combining data from different sources at the visualisation level. 2. Blend combines at visualisation level; join combines at row level. 3. It has a blue checkmark. 4. The field used to link sources. 5. Because blending aggregates data.

**Lesson 2.8**: 1. Reshaping data (columns to rows or rows to columns). 2. Unpivot = columns to rows; Pivot = rows to columns. 3. Tableau works best with long, narrow data. 4. Add a Pivot step and select Pivot to Rows. 5. Yes, but it's less common.

**Lesson 2.9**: 1. Data about data. 2. Double‑click the field name. 3. To change how values are displayed. 4. Right‑click → Default Properties → Aggregation. 5. To remove clutter from the Data pane.

---

**Congratulations!** You have completed Phase 2 of Tableau. You now have a strong foundation in data preparation – a skill that separates successful BI professionals from the rest. Keep practising with different datasets!

---








<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>
