# Phase 1: Tableau Fundamentals

Welcome to Tableau! You're about to embark on an exciting journey into the world of data visualisation. Just as you mastered Power BI in the previous phases, you'll now build a rock-solid foundation in Tableau – another industry-leading business intelligence tool.

Think of Tableau as your **visual storytelling canvas**. While Power BI excels at integrated enterprise analytics with deep DAX calculations, Tableau is renowned for its intuitive drag-and-drop interface, stunning visualisations, and rapid prototyping capabilities. Many organisations use both tools, and adding Tableau to your skill set makes you a versatile BI professional.

This phase mirrors the structure of your Power BI journey – we start from absolute basics and gradually build up. Every concept is explained in simple language, tied to real-world business scenarios, and reinforced with hands-on exercises.

---

## Lesson 1.1 – Introduction to Tableau

### Concept Explanation

**Tableau** is a powerful data visualisation and business intelligence platform that helps people see and understand their data. Founded in 2003, Tableau has become one of the most popular BI tools globally, known for its:

- **Intuitive drag-and-drop interface** – no coding required to create stunning visualisations.

- **Speed to insight** – you can go from raw data to a meaningful chart in seconds.

- **Visual best practices** – Tableau is built on research into how people perceive visual information.


Tableau offers several products:
- **Tableau Desktop** – the authoring tool where you create workbooks, worksheets, dashboards, and stories.

- **Tableau Public** – a free version for sharing visualisations publicly (limited data connection options).

- **Tableau Cloud** (formerly Tableau Online) – the cloud-hosted version for sharing and collaboration.

- **Tableau Server** – an on-premises version for enterprise deployment.

- **Tableau Prep** – a data preparation tool for cleaning and shaping data.

---

### Importance and Real-World Use Cases

- **Why it matters**: Data is everywhere, but raw data is difficult to interpret. Tableau transforms numbers into visual stories that decision-makers can understand at a glance. It enables **self-service analytics** – business users can explore data without relying on IT.


- **Use cases**:

  - A **retail chain** uses Tableau to monitor daily sales across hundreds of stores, identifying underperforming locations instantly.
  
  - A **healthcare provider** visualises patient wait times and treatment outcomes to improve care quality.
  
  - A **marketing agency** creates interactive dashboards for clients showing campaign performance in real-time.
  
  - A **financial services firm** analyses portfolio performance and risk exposure through dynamic visualisations.
  

---

### Step-by-Step Demonstration

Let's take Tableau for a quick spin:

1. **Open Tableau Desktop** – you'll see the **Start Page**.

2. The Start Page has three main sections:

   - **Connect** – options to connect to data files, servers, or saved data sources.
   - **Workbooks** – recently opened workbooks.
   - **Resources** – learning materials and community links.
3. Under **Connect**, click **Sample - Superstore** (a built-in dataset).

4. Tableau connects to the data and opens a new **worksheet** with the Data pane on the left.

5. Drag `Sales` from the Data pane to the **Columns** shelf.

6. Drag `Category` from the Data pane to the **Rows** shelf.

7. Tableau instantly creates a bar chart showing sales by category!

8. Drag `Region` to the **Filters** shelf and select only "West" – the chart updates.


You've just created your first Tableau visualisation in under a minute!

---

### Hands-on Exercises

1. Open Tableau Desktop and explore the Start Page – identify the Connect, Workbooks, and Resources sections.

2. Connect to **Sample - Superstore**.

3. Create a bar chart showing `Profit` by `Region`.

4. Create a line chart showing `Sales` over `Order Date` (drag `Order Date` to Columns, `Sales` to Rows).

5. Save your workbook as `MyFirstTableau.twbx`.

---

### Mini Quiz

1. What are the main products in the Tableau ecosystem?

2. What is the difference between Tableau Desktop and Tableau Public?

3. What is the built-in sample dataset called in Tableau?

4. Which shelf do you drag a field to in order to create the horizontal axis of a chart?

5. What does a "self-service analytics" tool allow users to do?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Skipping the exploration of Tableau's interface – jumping straight into chart creation | Spend time familiarising yourself with the Start Page, Data pane, and shelves |
| Using Tableau Public for sensitive or proprietary data | Use Tableau Desktop or Tableau Server for confidential business data |
| Not saving workbooks frequently | Save your `.twbx` (packaged workbook) regularly – it includes data sources |
| Overlooking the built-in sample data for learning | The Superstore dataset is excellent for practice and learning |

---

### Interview Questions

1. **What is Tableau and why is it used in business?**  

   *Answer*: Tableau is a data visualisation platform that helps organisations see and understand their data. It is used to create interactive dashboards and reports that enable data-driven decision-making without requiring programming skills.


2. **What are the key components of the Tableau product suite?**  

   *Answer*: Tableau Desktop (authoring), Tableau Server/Cloud (sharing), Tableau Public (free sharing), and Tableau Prep (data preparation).


3. **How does Tableau differ from traditional reporting tools?**  

   *Answer*: Tableau is designed for visual discovery and self-service analytics, allowing users to explore data interactively rather than viewing static reports.


---

### Assignment and Dashboard Projects

**Assignment 1.1** – Create a one-page summary of Tableau's product offerings, their key features, and when you would use each one. Include a brief comparison with Power BI.

---

### Summary and Revision Notes

- Tableau is a leading data visualisation tool for creating interactive dashboards.

- Key products: Desktop (authoring), Server/Cloud (sharing), Public (free), Prep (data preparation).

- The Start Page is your launchpad for connecting to data and accessing recent workbooks.

- Built-in **Sample - Superstore** dataset is perfect for practice.


---

## Lesson 1.2 – Business Intelligence Concepts

### Concept Explanation

Before diving deeper into Tableau, it's essential to understand the **Business Intelligence (BI)** concepts that underpin all data visualisation work. These concepts are the same whether you're using Tableau, Power BI, or any other BI tool.

**Core BI concepts**:

- **ETL (Extract, Transform, Load)** – The process of extracting data from source systems, transforming it (cleaning, aggregating, joining), and loading it into a data warehouse or BI tool.

- **Data Warehouse** – A central repository that stores integrated data from multiple sources, optimised for querying and analysis.

- **Star Schema** – A data modelling design with a central **fact table** (quantitative measures) surrounded by **dimension tables** (descriptive attributes).

- **Dimensions** – Categorical fields used to slice and dice data (e.g., Product, Region, Date).

- **Measures** – Quantitative fields that can be aggregated (e.g., Sales, Profit, Quantity).

- **KPIs (Key Performance Indicators)** – Quantifiable measures used to track performance against objectives (e.g., Revenue Growth, Customer Churn).


---

### Importance and Real-World Use Cases

- **Why it matters**: Understanding BI concepts helps you design better dashboards and communicate effectively with stakeholders. You'll know what questions to ask, how to structure your data, and what metrics matter.

- **Use cases**:

  - A **retail analyst** uses a star schema to analyse sales by product, region, and time.

  - A **finance director** monitors KPIs like Operating Margin and Cash Flow to assess company health.

  - A **marketing manager** uses ETL processes to combine campaign data from multiple sources into a single dashboard.


---

### Step-by-Step Demonstration (Conceptual)

Let's walk through a typical BI workflow:

1. **Extract**: Pull sales data from a SQL database and product data from an Excel file.

2. **Transform**: Clean product names, remove duplicates, convert date formats.

3. **Load**: Import the cleaned data into Tableau (or a data warehouse).

4. **Model**: Create relationships between Sales and Product tables.

5. **Visualise**: Build a dashboard showing sales by product category and region.

6. **Share**: Publish to Tableau Cloud or Tableau Server for the team to access.


This workflow is the same whether you're using Tableau, Power BI, or any other BI platform.

---

### Practical Examples

- **Example**: A retail chain wants to understand which products are underperforming. Using a star schema, they connect a `Sales` fact table to `Product`, `Store`, and `Date` dimension tables. They create a dashboard showing sales by product category, store location, and time period, enabling them to identify and address underperforming products.

---

### Hands-on Exercises

1. Think about a business question you would like to answer (e.g., "Which products are our best sellers?").

2. Identify the fact table and dimension tables you would need.

3. Draw a simple star schema on paper for a sales scenario (one fact table, two or three dimension tables).

4. List three KPIs a sales manager might monitor.


---

### Mini Quiz

1. What does ETL stand for?

2. What is the difference between a fact table and a dimension table?

3. What is a KPI? Give an example.

4. What is a data warehouse?

5. What is the purpose of a star schema?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Building dashboards without a clear business question – producing "chart junk" | Always start with a specific business question or hypothesis |
| Using data that hasn't been validated for accuracy | Validate data quality early; involve business users to confirm definitions |
| Over-complicating the data model with unnecessary tables | Keep the model as simple as possible; star schemas are preferred in Tableau |

---

### Interview Questions

1. **What is the difference between BI and data analytics?**  

   *Answer*: BI is the broader umbrella that includes the entire process from data collection to reporting. Analytics is more focused on statistical analysis and predictive modelling.

2. **What is a star schema and why is it used in BI?**  

   *Answer*: A star schema is a dimensional model with a central fact table and surrounding dimension tables. It optimises query performance and makes the data model easy to understand.

3. **How do you ensure your BI reports drive action?**  

   *Answer*: By aligning KPIs with business strategy, presenting data in a clear narrative, and providing drill-down capabilities to investigate root causes.

---

### Assignment and Dashboard Projects

**Assignment 1.2** – Write a one-page business case for a dashboard you would like to build. Describe:

- The business problem.

- The KPIs you will track.

- The data sources required.

- The expected users and how they will interact with the dashboard.


---

### Summary and Revision Notes

- BI transforms raw data into actionable insights.

- Key concepts: ETL, data warehouses, star schemas, dimensions, measures, KPIs.

- Tableau is a tool that implements the entire BI workflow from data to visualisation.

- Always start with a clear business question.


---

## Lesson 1.3 – Installing and Setting Up Tableau Desktop

### Concept Explanation

Tableau Desktop is the primary authoring tool for creating visualisations, dashboards, and stories. It is available for both **Windows** and **Mac** operating systems.

**System Requirements**:

- **Windows** – Windows 8/8.1, Windows 10 (x64), or Windows 11

  - Minimum: Intel Core i3 or AMD Ryzen 3 (Dual Core), 4GB RAM, 2GB disk space
  
  - Recommended: Intel Core i7 or AMD Ryzen 7 (Quad Core), 16GB RAM, 2GB SSD
  
- **Mac** – macOS Ventura, Sonoma, Sequoia, or Tahoe (for Tableau 2026.1+)

  - Minimum: Intel Core i3 or Apple Silicon, 4GB RAM
  
  - Recommended: Intel Core i7, 16GB RAM, 2GB SSD
  

**Licensing Options**:
- **Tableau Desktop** – Full-featured version, requires a license (part of Tableau Creator subscription).

- **Tableau Public** – Free version with limited data connection options and public sharing only.

- **Trial Version** – 14-day free trial of Tableau Desktop.


---

### Importance and Real-World Use Cases

- **Why it matters**: Without a proper installation, you cannot begin creating visualisations. Understanding system requirements ensures smooth performance, especially with large datasets.

- **Use cases**:

  - A **data analyst** installs Tableau Desktop on their work laptop to create weekly sales reports.

  - A **consultant** uses the 14-day trial to build a proof-of-concept dashboard for a client.

  - A **student** uses Tableau Public to build a portfolio of visualisations.


---

### Step-by-Step Demonstration

1. **Check system requirements** – ensure your computer meets the minimum specifications.

2. **Download Tableau Desktop**:

   - Go to `tableau.com/products/desktop/download`.

   - Click **Download Free Trial** (or **Download** if you have a license).

3. **Run the installer**:

   - Windows: Run the `.exe` file and follow the prompts.

   - Mac: Open the `.dmg` file and drag Tableau to the Applications folder.

4. **Activate your license** (or start the trial):

   - Enter your license key, or click **Start trial**.

5. **Launch Tableau Desktop** – the Start Page appears.


**For Tableau Public**:

- Download from `public.tableau.com`.

- Sign in with a free Tableau Public account.

- Note: You can only save to Tableau Public (not locally as `.twbx`).


---

### Practical Examples

- **Example**: You are setting up Tableau on a new laptop. You check that the laptop has Windows 11, an Intel Core i7 processor, and 16GB RAM – well above the minimum requirements. You download the installer, run it, and activate the 14-day trial to start learning.

---

### Hands-on Exercises

1. Download and install Tableau Desktop (trial version) or Tableau Public.

2. Launch Tableau and explore the Start Page.

3. Check your version: Help → About Tableau.

4. Sign in with your Tableau account (if using Tableau Public).

5. Connect to Sample - Superstore to confirm everything is working.


---

### Mini Quiz

1. What are the minimum RAM requirements for Tableau Desktop?

2. Where can you download Tableau Desktop?

3. What is the difference between Tableau Desktop and Tableau Public?

4. What operating systems does Tableau Desktop support?

5. How long is the Tableau Desktop trial period?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Installing Tableau on a machine with insufficient RAM – slow performance | Ensure at least 8GB RAM (16GB recommended) for moderate datasets |
| Using Tableau Public for confidential business data | Use Tableau Desktop for proprietary data; Tableau Public is for public-facing visualisations |
| Not checking system requirements before installation | Verify CPU, RAM, and disk space before installing |
| Forgetting to activate the license or start the trial | Complete the activation process to avoid running in limited mode |

---

### Interview Questions

1. **How do you install Tableau Desktop on a Windows machine?**  

   *Answer*: Download the installer from the Tableau website, run the `.exe` file, follow the prompts, and activate the license or start the trial.

2. **What is the difference between Tableau Desktop and Tableau Public?**  

   *Answer*: Tableau Desktop is the full-featured version for professional use with extensive data connection options. Tableau Public is free but limited to public data sources and requires saving workbooks to the Tableau Public cloud.

3. **Can you install Tableau on a Mac?**  

   *Answer*: Yes, Tableau Desktop is available for macOS (Intel and Apple Silicon).

---

### Assignment and Dashboard Projects

**Assignment 1.3** – Write a step-by-step guide (with screenshots or descriptions) for installing Tableau Desktop on a fresh machine. Include troubleshooting tips (e.g., admin rights, firewall).

---

### Summary and Revision Notes

- Tableau Desktop is available for Windows and Mac.

- Minimum requirements: 4GB RAM (16GB recommended), 2GB disk space.

- Download from `tableau.com/products/desktop/download`.

- Tableau Public is a free alternative with limitations.

---

## Lesson 1.4 – Tableau Interface Overview

### Concept Explanation

Understanding the Tableau interface is your first step towards becoming proficient. Tableau's interface is designed to be intuitive, with a clear separation of data, analysis, and presentation areas.

**Key Interface Components**:

| **Component** | **Description** |
|---------------|-----------------|
| **Menu Bar** | Top – File, Data, Worksheet, Dashboard, Story, Analysis, Map, Format, Server, Window, Help |
| **Toolbar** | Below menu bar – quick access to common actions (undo, redo, save, etc.) |
| **Data pane** | Left side – lists all fields (columns) from your data source; fields are colour-coded (blue = dimensions, green = measures) |
| **Shelves** | **Columns** (horizontal axis) and **Rows** (vertical axis) – drag fields here to build visualisations |
| **Marks Card** | Controls the appearance of marks (bars, lines, circles, etc.) – includes Color, Size, Label, Detail, Tooltip |
| **Filters Shelf** | Apply filters to the entire worksheet |
| **Pages Shelf** | Create animations by adding a field to split the view across pages |
| **Worksheet tabs** | Bottom – switch between worksheets, dashboards, and stories |

**Key Concepts**:

- **Dimensions** (blue pills) – categorical variables that slice and dice data.

- **Measures** (green pills) – quantitative variables that are aggregated.

- **Discrete** (blue) vs **Continuous** (green) fields.

---

### Importance and Real-World Use Cases

- **Why it matters**: Knowing your way around the interface dramatically speeds up report development. You'll spend most of your time in the Data pane, shelves, and Marks Card.


- **Use cases**:

  - A **data analyst** drags `Sales` (measure) to Columns and `Category` (dimension) to Rows to create a bar chart.

  - A **dashboard designer** uses the Marks Card to colour bars by profit and add labels.

  - A **business user** applies filters to focus on a specific region or time period.


---

### Step-by-Step Demonstration

1. Open Tableau and connect to **Sample - Superstore**.

2. Look at the **Data pane** on the left:

   - Blue icons = **Dimensions** (e.g., Category, Region, Customer Name).

   - Green icons = **Measures** (e.g., Sales, Profit, Quantity).

3. Drag `Sales` (green) to the **Columns** shelf.

4. Drag `Category` (blue) to the **Rows** shelf.

5. A bar chart appears.

6. Click on the **Marks Card** – you'll see options for Color, Size, Label, Detail, and Tooltip.

7. Drag `Profit` to **Color** on the Marks Card – the bars are now coloured by profit.

8. Drag `Region` to the **Filters** shelf – a filter dialog appears. Select "West" and click OK.

9. The chart updates to show only the West region.

---

### Hands-on Exercises

1. Connect to Sample - Superstore.

2. Identify all dimensions and measures in the Data pane.

3. Create a bar chart showing `Sales` by `Sub-Category`.

4. Use the Marks Card to:

   - Change the colour of the bars.

   - Add labels showing the sales values.

   - Change the mark type to "Circle".

5. Add a filter for `Region` and select "East".

6. Save your workbook.


---

### Mini Quiz

1. What is the difference between a dimension and a measure in Tableau?

2. What colour are dimension pills typically?

3. What does the Marks Card allow you to control?

4. Which shelf would you drag a field to in order to create the vertical axis?

5. What is the purpose of the Filters shelf?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Dragging measures to Rows and dimensions to Columns – confusing axis placement | Use Columns for horizontal axis, Rows for vertical axis |
| Ignoring the Marks Card – default colours and labels may not be optimal | Always customise the Marks Card for clarity and aesthetics |
| Not using the Data pane to explore fields before building visuals | Spend time understanding your data fields before dragging them onto shelves |
| Forgetting to rename fields in the Data pane | Rename fields to business-friendly names (e.g., "Profit" instead of "Sum of Profit") |

---

### Interview Questions

1. **What are the key components of the Tableau interface?**  

   *Answer*: The menu bar, toolbar, Data pane, Columns and Rows shelves, Marks Card, Filters shelf, Pages shelf, and worksheet tabs.

2. **What is the difference between a blue pill and a green pill in Tableau?**  

   *Answer*: Blue pills represent discrete (categorical) fields – typically dimensions. Green pills represent continuous (numeric) fields – typically measures. Discrete fields create headers, while continuous fields create axes.

3. **What is the Marks Card and what can you do with it?**  

   *Answer*: The Marks Card controls the appearance of marks (bars, lines, circles, etc.) in a visualisation. It allows you to set colour, size, label, detail, and tooltip.

---

### Assignment and Dashboard Projects

**Assignment 1.4** – Create a one-page "cheat sheet" of the Tableau interface:

- Label all key components (Data pane, Columns/Rows shelves, Marks Card, etc.).

- Include a brief description of what each component does.

- Save it for future reference.


---

### Summary and Revision Notes

- Tableau's interface is divided into: Data pane, Columns/Rows shelves, Marks Card, Filters shelf.

- **Dimensions** (blue) – categorical; **Measures** (green) – numeric and aggregatable.

- Discrete fields create headers; continuous fields create axes.

- The Marks Card controls colour, size, labels, detail, and tooltips.

---

## Lesson 1.5 – Understanding Workbooks, Worksheets, Dashboards, and Stories

### Concept Explanation

Tableau organises content in a hierarchical structure. Understanding this hierarchy is fundamental to building effective visualisations and dashboards.

**The Tableau Hierarchy** (bottom to top):

1. **Pills** – The visual representation of a data item (dimension or measure) placed on shelves.

2. **Worksheet** – A single view (chart, map, or table) containing shelves, cards, legends, and the Data pane.

3. **Dashboard** – A collection of views from multiple worksheets arranged on a single canvas.

4. **Story** – A sequence of worksheets or dashboards that work together to convey information; each page is called a **story point**.

5. **Workbook** – The entire Tableau file (`.twb` or `.twbx`) containing all worksheets, dashboards, and stories.

6. **Packaged Workbook (`.twbx`)** – A single zip file containing a workbook along with any supporting local file data sources and background images.

---

### Importance and Real-World Use Cases

- **Why it matters**: This hierarchy allows you to build modular, reusable visualisations. You can create a single worksheet and use it in multiple dashboards and stories.

- **Use cases**:

  - A **sales analyst** creates individual worksheets for revenue, profit, and customer count, then combines them into a dashboard.

  - A **marketing manager** uses a story to present a narrative: "Here's the problem → here's our analysis → here's our recommendation."

  - A **consultant** saves a packaged workbook (`.twbx`) to share with a client who doesn't have access to the original data.


---

### Step-by-Step Demonstration

**Creating a Worksheet**:

1. In Tableau, connect to Sample - Superstore.

2. Click the **Sheet 1** tab at the bottom.

3. Drag `Sales` to Columns, `Category` to Rows – a bar chart appears.

4. Rename the worksheet: right-click the tab → **Rename** → type "Sales by Category".

**Creating a Dashboard**:

1. Click the **New Dashboard** icon (the one with a grid) at the bottom.

2. In the Dashboard pane on the left, you'll see your worksheet ("Sales by Category").

3. Drag it onto the canvas.

4. Add a filter: drag `Region` from the Data pane to the dashboard canvas → choose "West".


**Creating a Story**:

1. Click the **New Story** icon (the one with pages) at the bottom.

2. Drag your dashboard onto the first story point.

3. Add a second story point with a different filter or view.

4. Use the navigation arrows to move between story points.

---

### Practical Examples

- **Example 1**: A **worksheet** shows sales by product category. A **dashboard** combines this with a map showing sales by region and a table of top customers. A **story** walks the CEO through the quarterly performance, page by page.

- **Example 2**: You create a packaged workbook (`.twbx`) containing all your dashboards and send it to a colleague. They can open it without needing access to the original data sources.

---

### Hands-on Exercises

1. Connect to Sample - Superstore.

2. Create three worksheets:

   - **Sales by Category** – bar chart.

   - **Sales by Region** – bar chart.

   - **Sales over Time** – line chart.

3. Create a **dashboard** that combines all three worksheets.

4. Add a filter to the dashboard that filters all worksheets simultaneously.

5. Create a **story** with two pages: one showing the dashboard, and one with a summary text box.

6. Save your workbook as a packaged workbook (`.twbx`).


---

### Mini Quiz

1. What is the difference between a worksheet and a dashboard?

2. What is a story point?

3. What is the difference between a `.twb` and a `.twbx` file?

4. How do you rename a worksheet?

5. Can a dashboard contain multiple worksheets?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Putting too many worksheets on one dashboard – cluttered | Limit dashboards to 3-5 key worksheets |
| Not naming worksheets and dashboards clearly – "Sheet 1" is not helpful | Always give descriptive names (e.g., "Sales by Category", "Executive Dashboard") |
| Using `.twb` when sharing with others who don't have data access | Use `.twbx` (packaged workbook) to include data sources |
| Not using stories for presentations – sending users to navigate dashboards themselves | Use stories to guide users through a narrative |

---

### Interview Questions

1. **What is the hierarchy of content in Tableau?**  

   *Answer*: Worksheet → Dashboard → Story → Workbook. A worksheet is a single view; a dashboard combines multiple worksheets; a story sequences dashboards/worksheets; a workbook contains everything.

2. **What is the difference between a workbook and a packaged workbook?**  

   *Answer*: A workbook (`.twb`) contains only the workbook file. A packaged workbook (`.twbx`) includes the workbook along with any local data sources and background images, making it self-contained for sharing.

3. **How do you create a story in Tableau?**  

   *Answer*: Click the New Story icon, then drag worksheets or dashboards onto the story canvas. Each page is called a story point.

---

### Assignment and Dashboard Projects

**Assignment 1.5** – Create a complete Tableau project:

- **Three worksheets**: Sales by Category, Sales by Region, Profit over Time.

- **One dashboard** containing all three worksheets with a filter.

- **One story** with at least three story points explaining the data.

- Save as a packaged workbook (`.twbx`).

---

### Summary and Revision Notes

- **Worksheet** = single view (chart/map/table).

- **Dashboard** = collection of worksheets.

- **Story** = sequence of worksheets/dashboards.

- **Workbook** = entire file (`.twb` or `.twbx`).

- Packaged workbook (`.twbx`) includes data sources for easy sharing.

---

## Lesson 1.6 – Connecting to Data Sources

### Concept Explanation

Tableau can connect to a wide variety of data sources – from simple spreadsheets to complex databases and cloud platforms. Tableau offers **native connectors** built and optimised for many databases and files.

**Types of data sources**:

- **Files**: Microsoft Excel, CSV, PDF, Spatial files, JSON, etc.

- **Server-based platforms**: Google Drive, Amazon Redshift, Oracle, SQL Server, Snowflake, Google BigQuery, etc.

- **Cloud and web data**: Salesforce, Google Analytics, web data connectors, etc.

- **Published data sources**: Connect to data already published to Tableau Cloud or Tableau Server.


**Connection options**:

- **Live Connection** – queries the data source directly (real-time).

- **Extract** – imports a snapshot of the data into Tableau's high-performance engine (covered in Lesson 1.7).


---

### Importance and Real-World Use Cases

- **Why it matters**: Data lives everywhere – in spreadsheets, databases, and the cloud. Tableau's ability to connect to all these sources makes it a versatile tool for any organisation.

- **Use cases**:

  - A **financial analyst** connects to an Excel file containing monthly budget data.

  - A **data engineer** connects to a Snowflake data warehouse to build enterprise dashboards.

  - A **marketing analyst** connects to Google Analytics to visualise campaign performance.


---

### Step-by-Step Demonstration

**Connecting to Excel**:

1. Open Tableau Desktop.

2. On the Start Page, under **Connect**, click **Microsoft Excel**.

3. Browse and select your Excel file.

4. In the Data Source page, drag the sheet(s) you want to use onto the canvas.

5. Click **Sheet 1** (bottom) to start building your visualisation.


**Connecting to CSV**:

1. On the Start Page, click **Text file**.

2. Browse and select your CSV file.

3. Tableau will detect the delimiter and structure.

4. Click **Sheet 1** to start.


**Connecting to a Database (e.g., SQL Server)**:

1. On the Start Page, click **SQL Server** (or your database of choice).

2. Enter the server name and database.

3. Choose authentication method (Windows or SQL Server).

4. Select the tables or write a custom SQL query.

5. Click **Sheet 1** to start.

**Using Sample Data**:
- On the Start Page, under **Saved Data Sources**, click **Sample - Superstore**.

---

### Practical Examples

- **Example 1**: You have monthly sales data in an Excel file. You connect to it, drag the sheet onto the canvas, and immediately start building visualisations.

- **Example 2**: Your organisation stores data in Snowflake. You connect to Snowflake, select the relevant tables, and build a dashboard that refreshes with the latest data.

---

### Hands-on Exercises

1. Download a sample CSV or Excel file from the internet (e.g., from Kaggle).

2. Connect to it in Tableau using the appropriate connector.

3. Explore the Data Source page – note the left pane, canvas, and data grid.

4. Drag a table onto the canvas.

5. Click **Sheet 1** and verify that the data fields appear in the Data pane.


---

### Mini Quiz

1. What are the three main types of data sources Tableau can connect to?

2. How do you connect to an Excel file in Tableau?

3. What is the built-in sample dataset in Tableau called?

4. What is a published data source?

5. What is the Data Source page used for?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Connecting to the wrong sheet or table | Preview the data in the Data Source page before building visualisations |
| Not checking field data types – numbers may be imported as strings | Verify and adjust data types in the Data Source page |
| Using a live connection when an extract would be faster | Consider using extracts for better performance (Lesson 1.7) |
| Connecting to too many tables without a clear data model | Plan your data model before connecting multiple tables |

---

### Interview Questions

1. **What types of data sources can Tableau connect to?**  

   *Answer*: Tableau can connect to files (Excel, CSV, PDF, etc.), server-based platforms (SQL Server, Oracle, Snowflake, etc.), cloud applications (Salesforce, Google Analytics), and published data sources on Tableau Server/Cloud.

2. **How do you connect Tableau to a SQL Server database?**  

   *Answer*: On the Start Page, click SQL Server, enter the server name and database, choose authentication, and select the tables or write a custom SQL query.

3. **What is the Data Source page used for?**  

   *Answer*: The Data Source page allows you to view your data, set up relationships between tables, change field data types, and prepare your data before building visualisations.

---

### Assignment and Dashboard Projects

**Assignment 1.6** – Connect to three different data sources:

- One Excel file.

- One CSV file.

- One database or cloud source (if available).

- Document the steps for each connection.

---

### Summary and Revision Notes

- Tableau connects to files, databases, and cloud platforms.

- Use the **Start Page** to select a connector.

- The **Data Source page** allows you to preview and prepare data.

- **Sample - Superstore** is the built-in dataset for practice.

---

## Lesson 1.7 – Live Connections vs Extracts

### Concept Explanation

When you connect to a data source, Tableau gives you a critical choice: **Live Connection** or **Extract**.

**Live Connection**:

- Queries the source database directly every time you interact with the dashboard.

- Data is always up-to-date.

- Performance depends on the source database and network.


**Extract**:

- Creates a snapshot of the data stored in Tableau's high-performance engine.

- Much faster performance because data is local.

- Data is static until you refresh the extract.

**When to use each**:

| **Live Connection** | **Extract** |
|---------------------|-------------|
| Real-time data is critical | Performance is more important than real-time |
| Data changes frequently | Data is relatively static |
| Source database can handle query load | You want to reduce load on the source database |
| You need to see the latest data instantly | You want to use Tableau's faster in-memory engine |
| Working with small to medium datasets | Working with large datasets that need optimisation |

---

### Importance and Real-World Use Cases

- **Why it matters**: Your choice has a huge impact on dashboard performance and data freshness. Choosing the wrong option can lead to slow dashboards or stale data.

- **Use cases**:

  - A **stock trading dashboard** uses a live connection to show real-time prices.

  - A **monthly sales report** uses an extract because data is only updated monthly and performance is critical.

  - A **data engineer** uses extracts to reduce load on the production database during business hours.


---

### Step-by-Step Demonstration

**Using a Live Connection**:

1. Connect to a data source (e.g., SQL Server).

2. In the connection dialog, ensure **Live** is selected.

3. Build your visualisation – each interaction queries the database.


**Creating an Extract**:

1. Connect to a data source.

2. In the Data Source page, click **Extract** in the top-right corner.

3. Choose which data to extract (all rows or a subset).

4. Click **Extract** – Tableau creates the extract.

5. You can now work offline and enjoy faster performance.


**Refreshing an Extract**:
- In the Data Source page, click **Extract** → **Refresh**.

---

### Practical Examples

- **Example 1**: You are building a dashboard for a call centre that needs to show live call volumes. You use a **live connection** to the call centre database.

- **Example 2**: You are building a sales dashboard with data from the last 5 years. The data changes monthly. You use an **extract** and refresh it monthly for optimal performance.

---

### Hands-on Exercises

1. Connect to Sample - Superstore (which is automatically an extract in Tableau Public).

2. If you have access to a database, connect using Live mode and observe the performance.

3. Create an extract from a data source and compare the performance with a live connection.

4. Refresh the extract and observe the update.


---

### Mini Quiz

1. What is the main difference between a live connection and an extract?

2. When would you use a live connection?

3. When would you use an extract?

4. How do you create an extract in Tableau?

5. How do you refresh an extract?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using live connections for all dashboards – slowing performance | Use extracts for dashboards that don't require real-time data |
| Using extracts for data that changes by the minute – stale data | Use live connections for real-time requirements |
| Not refreshing extracts regularly – outdated dashboards | Schedule extract refreshes (in Tableau Server/Cloud) |
| Extracting entire tables when only a subset is needed | Use filters in the extract to limit data |

---

### Interview Questions

1. **What is the difference between a live connection and an extract in Tableau?**  

   *Answer*: A live connection queries the source database directly in real-time. An extract creates a snapshot of the data stored in Tableau's in-memory engine for faster performance.

2. **When would you choose a live connection over an extract?**  

   *Answer*: When real-time data is critical, such as in operational dashboards monitoring live systems.

3. **How do you refresh an extract in Tableau?**  

   *Answer*: In the Data Source page, click Extract → Refresh. In Tableau Server/Cloud, you can schedule refreshes.

---

### Assignment and Dashboard Projects

**Assignment 1.7** – Create two versions of the same dashboard:

- Version 1: Using a live connection.

- Version 2: Using an extract.

- Compare the performance and document your findings.


---

### Summary and Revision Notes

- **Live Connection**: Real-time, queries source directly, slower.

- **Extract**: Snapshot, faster, requires refreshing.

- Choose based on: data freshness needs, performance requirements, and source database load.

- Extracts are preferred for most analytical dashboards.

---

## Lesson 1.8 – Tableau Workflow

### Concept Explanation

The Tableau workflow is the end-to-end process of turning raw data into actionable insights. Understanding this workflow helps you plan your projects and avoid common pitfalls.

**The Tableau Workflow** (step-by-step):

1. **Connect to Data** – Choose a data source (file, database, or cloud).

2. **Prepare Data** – Clean, shape, and combine data (using Tableau Prep or the Data Source page).

3. **Build Visualisations** – Create worksheets using drag-and-drop.

4. **Create Dashboards** – Combine worksheets into interactive dashboards.

5. **Tell a Story** – Sequence dashboards into a narrative.

6. **Share** – Publish to Tableau Server, Tableau Cloud, or Tableau Public.

7. **Iterate** – Gather feedback and refine.


**Tableau Prep**:

- A separate tool in the Tableau suite designed to make data preparation easy and intuitive.

- Use Tableau Prep to combine, shape, and clean your data before analysis.

---

### Importance and Real-World Use Cases

- **Why it matters**: Following a structured workflow ensures you don't skip critical steps. It helps you deliver high-quality dashboards on time.

- **Use cases**:

  - A **data analyst** follows the workflow: connects to a SQL database, uses Tableau Prep to clean the data, builds visualisations, creates a dashboard, and publishes to Tableau Cloud.

  - A **consultant** uses the workflow to deliver a client dashboard: connect, prepare, visualise, dashboard, story, share.
  
---

### Step-by-Step Demonstration

Let's walk through a complete workflow:

1. **Connect**: Open Tableau, click **Microsoft Excel**, and select a sales file.

2. **Prepare**: In the Data Source page, rename fields, change data types, and join tables.

3. **Build Visualisations**: Create worksheets for sales by region, sales by product, and sales over time.

4. **Create Dashboard**: Combine the worksheets into a dashboard with filters.

5. **Tell a Story**: Create a story with pages explaining the data.

6. **Share**: Save as a packaged workbook (`.twbx`) and share with colleagues.

---

### Practical Examples

- **Example 1**: A retail analyst needs to create a weekly sales dashboard. They connect to the sales database, use Tableau Prep to clean the data, build visualisations, create a dashboard, and publish to Tableau Server for the team.

- **Example 2**: A marketing agency creates a campaign performance dashboard for a client. They follow the workflow, then share the dashboard via Tableau Public.

---

### Hands-on Exercises

1. Follow the complete workflow using Sample - Superstore:

   - Connect to the data.

   - Explore the Data Source page.

   - Build 2-3 worksheets.

   - Create a dashboard.

   - Create a story.

   - Save as a packaged workbook.

2. Document each step.


---

### Mini Quiz

1. What are the steps in the Tableau workflow?

2. What is Tableau Prep used for?

3. What is the difference between a dashboard and a story?

4. How do you share a Tableau workbook?

5. Why is iteration important in the workflow?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Skipping data preparation – building dashboards on messy data | Always clean and shape your data before building visualisations |
| Building dashboards without a clear goal | Define the business question before you start |
| Not testing with stakeholders before finalising | Gather feedback early and iterate |
| Forgetting to document your work | Add tooltips, titles, and annotations to help users understand |

---

### Interview Questions

1. **Walk me through your process for creating a Tableau dashboard.**  

   *Answer*: I start by understanding the business question. Then I connect to the data, prepare it (using Tableau Prep if needed), build visualisations, create a dashboard, add interactivity, and share it. I iterate based on feedback.

2. **What is Tableau Prep and why is it useful?**  

   *Answer*: Tableau Prep is a data preparation tool that makes it easy to clean, shape, and combine data. It's useful because it reduces the time spent on data preparation and improves data quality.

3. **How do you handle feedback on a dashboard?**  

   *Answer*: I gather feedback from stakeholders, prioritise changes, update the dashboard, and share the updated version. Iteration is a normal part of the workflow.

---

### Assignment and Dashboard Projects

**Assignment 1.8** – Complete a full Tableau project from start to finish:

- Choose a dataset (or use Sample - Superstore).

- Follow the complete workflow: Connect → Prepare → Visualise → Dashboard → Story → Share.

- Submit the packaged workbook (`.twbx`) and a one-page summary of your process.

---

### Summary and Revision Notes

- The Tableau workflow is: Connect → Prepare → Visualise → Dashboard → Story → Share → Iterate.

- Tableau Prep is used for data preparation.

- A story sequences dashboards into a narrative.

- Iteration based on feedback is essential.

---

## Final Phase 1 Assessment

Now that you have completed all lessons, it's time to consolidate your knowledge.

### Self-Evaluation Checklist

-  I can explain what Tableau is and its main products.

-  I understand BI concepts (ETL, star schema, dimensions, measures, KPIs).

-  I have installed Tableau Desktop (or Tableau Public).

-  I am familiar with the Tableau interface (Data pane, shelves, Marks Card).

-  I understand the hierarchy: worksheets, dashboards, stories, workbooks.

-  I can connect to various data sources.

-  I understand the difference between live connections and extracts.

-  I know the Tableau workflow.

---

### Answers to Mini Quizzes

**Lesson 1.1**: 1. Desktop, Server/Cloud, Public, Prep. 2. Desktop is full-featured; Public is free with limitations. 3. Sample - Superstore. 4. Columns shelf. 5. Explore data without IT assistance.

**Lesson 1.2**: 1. Extract, Transform, Load. 2. Fact = measures, Dimension = attributes. 3. A KPI is a quantifiable measure; e.g., Revenue Growth. 4. A centralised data repository. 5. To model data for analysis.

**Lesson 1.3**: 1. 4GB (16GB recommended). 2. tableau.com/products/desktop/download. 3. Public is free with limitations. 4. Windows and Mac. 5. 14 days.

**Lesson 1.4**: 1. Dimensions are categorical; Measures are numeric. 2. Blue. 3. Colour, size, labels, etc. 4. Rows shelf. 5. To filter data in the worksheet.

**Lesson 1.5**: 1. Worksheet = single view; Dashboard = collection of worksheets. 2. A page in a story. 3. .twb = workbook only; .twbx = includes data. 4. Right-click the tab → Rename. 5. Yes.

**Lesson 1.6**: 1. Files, servers, cloud. 2. Start Page → Microsoft Excel. 3. Sample - Superstore. 4. A data source published to Tableau Server/Cloud. 5. To preview and prepare data.

**Lesson 1.7**: 1. Live = real-time; Extract = snapshot. 2. When real-time data is needed. 3. For performance and offline work. 4. Data Source page → Extract. 5. Data Source page → Extract → Refresh.

**Lesson 1.8**: 1. Connect, Prepare, Visualise, Dashboard, Story, Share, Iterate. 2. Data preparation. 3. Dashboard = collection of worksheets; Story = sequence of dashboards/worksheets. 4. Publish to Server/Cloud or save as .twbx. 5. To improve based on feedback.

---

**Congratulations!** You have completed Phase 1 of Tableau. You now have a solid foundation in Tableau fundamentals.

----








<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>