# Phase 10: Real-World Projects

Welcome to **Phase 10** – the culmination of your Tableau journey! Over the past nine phases, you have mastered every aspect of Tableau: from connecting to data and preparing it, to building calculations and stunning visualisations, to designing interactive dashboards and securing enterprise deployments.

Now, it is time to **put it all together**.

This phase is unique. Instead of introducing new concepts, we will apply everything you have learned to build **eight complete, end‑to‑end business dashboards**. Each project is a real‑world scenario that you will encounter in your career as a data analyst or BI developer. These projects span multiple industries and functional areas, giving you a well‑rounded portfolio.

---

## Project 10.1 – Sales Performance Dashboard

### Concept Explanation

A **Sales Performance Dashboard** is one of the most common and critical BI solutions. It provides sales leaders and teams with a real‑time view of revenue, quotas, pipeline, and performance trends. The goal is to enable data‑driven decisions about territories, products, and sales strategies.

**Core Metrics and KPIs**:

- **Revenue**: Total sales, growth rate, average deal size.

- **Quota Attainment**: % of quota achieved by sales reps, teams, and regions.

- **Pipeline**: Open opportunities, expected revenue, stages.

- **Performance**: Top products, top reps, regional breakdowns.

- **Trends**: Monthly/quarterly revenue trends, seasonality.

**Key Dimensions**: Time (Date), Geography (Region/Country), Product, Sales Rep, Customer Segment.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Sales is the lifeblood of most organisations. A sales dashboard helps identify which products are winning, which regions are underperforming, and which sales reps need coaching – all in real time.

- **Use cases**:

  - A **Sales Director** monitors team performance against quarterly targets and reallocates resources.
  
  - A **Regional Manager** drills down to individual reps to provide targeted coaching.
  
  - A **Product Manager** identifies which products are driving growth and which are declining.
  

---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Connect to a sales fact table (e.g., `Sales` with columns: `OrderID`, `OrderDate`, `ProductID`, `CustomerID`, `SalesRepID`, `Revenue`, `Quantity`, `Discount`) and dimension tables: `Product`, `Customer`, `SalesRep`, `Date`, `Region`.

2. **Data Modeling**:

   - Build a star schema – `Sales` (fact) connected to dimensions: `Product`, `Customer`, `SalesRep`, `Date`, `Region`.

   - Create a separate date table covering the full date range (using a data source or Tableau Prep).

3. **Calculated Fields**:

   - `Total Revenue = SUM([Revenue])`

   - `Total Units = SUM([Quantity])`

   - `YTD Revenue = { FIXED YEAR([Order Date]) : SUM([Revenue]) }`

   - `Revenue Growth % = (SUM([Revenue]) - [Revenue LY]) / [Revenue LY]`

   - `Average Deal Size = AVG([Revenue])`

   - `Quota Attainment % = SUM([Revenue]) / SUM([Quota])` – assuming a quota table.


4. **Visuals**:

   - **Top‑row KPI Cards**: Total Revenue, YTD Revenue, Growth %, Average Deal Size.

   - **Line Chart**: Monthly revenue trend with year‑over‑year comparison.

   - **Bar Chart**: Revenue by Product (top 10).

   - **Map**: Revenue by Region.

   - **Matrix**: Revenue and Quota Attainment by Sales Rep and Region.

   - **Slicers**: Year, Region, Product Category.


5. **Dashboard**:

   - Use a horizontal container for KPIs.

   - Use a vertical container for charts.

   - Add a title: "Sales Performance Dashboard".

   - Add filters for Year, Region, and Product Category.


6. **Publish and Share**:

   - Publish to Tableau Server/Cloud.

   - Set up extract refresh (daily).

   - Share with the sales team.


---

### Practical Examples

- **Example**: A sales dashboard shows that the Western region is underperforming. The director drills down to see that two reps in that region have not met their quotas for three months. They schedule coaching sessions and reallocate leads.

---

### Hands‑on Exercises

1. **Dataset**: Use the Sample - Superstore dataset (or a larger sales dataset from Kaggle).

2. **Build the Model**:

   - Create a star schema with fact and dimension tables.

   - Create a date table using Tableau Prep or a calculated field.

3. **Create Calculated Fields**:

   - `Total Revenue`, `Total Quantity`, `YTD Revenue`, `Revenue vs Target %` (create a target table if you don't have one).

4. **Design the Dashboard**:

   - Use a 1920×1080 canvas.

   - Add KPIs at the top.

   - Add a line chart for trends and a bar chart for product performance.

   - Add a matrix for rep‑level details.

5. **Add Interactivity**: Slicers for Year, Region, and Product Category.


---

### Mini Quiz

1. What is the most important KPI on a sales dashboard for a sales manager?

2. Why is a date table essential for a sales performance dashboard?

3. How would you calculate Year‑over‑Year growth in Tableau?

4. What visual would you use to compare revenue across regions?

5. How can you add quota attainment to a sales dashboard?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using a flat table – limits analysis | Build a star schema with separate dimension tables |
| Not using a proper date table – time intelligence fails | Always use a separate date table |
| Overwhelming the dashboard with too many visuals | Focus on 6‑8 key visuals; use drill‑through for details |
| Not including targets – users can't see performance against goals | Always include targets or quotas |
| Ignoring data freshness – reports show old data | Set up scheduled extract refresh |

---

### Interview Questions

1. **How would you design a sales performance dashboard for a multinational company?**  

   *Answer*: I would use a star schema with Sales (fact) connected to Date, Product, Customer, SalesRep, and Region dimensions. I would create measures for revenue, YTD, growth, and quota attainment. I would use a map for regional analysis, a line chart for trends, and a matrix for rep‑level detail. I would apply Row‑Level Security to restrict regional managers to their regions.

2. **What calculated field would you use to calculate the top 5 products by revenue?**  

   *Answer*: I would use a table calculation – `RANK(SUM([Revenue]))` – and then filter to show only rank <= 5.

3. **How do you handle sales data that changes frequently (e.g., returns and cancellations)?**  

   *Answer*: I would ensure the data source is updated regularly through scheduled extracts. I would also include a `ReturnAmount` or `Adjustment` field in the fact table and net it against revenue.

---

### Assignment and Dashboard Projects

**Assignment 10.1** – Build a complete Sales Performance Dashboard:

- Use a dataset of your choice (or Sample - Superstore).

- Include at least 5 KPIs.

- Include a trend chart, a product performance chart, a regional map, and a rep performance matrix.

- Add dynamic measure switching using a parameter (e.g., switch between Revenue, Units, and Profit).

- Add Row‑Level Security for regional managers (if publishing).

- Submit the `.twbx` file and a one‑page report on your design choices.


---

### Summary and Revision Notes

- Sales dashboards focus on **revenue, growth, quotas, and pipeline**.

- Use a **star schema** for optimal performance.

- Key visuals: KPIs, line charts, bar charts, maps, matrices.

- **Time intelligence** is critical – use date parts and table calculations.

- Always include **targets** and **filters** for interactivity.


---

## Project 10.2 – Executive KPI Dashboard

### Concept Explanation

An **Executive KPI Dashboard** is the ultimate high‑level view of organisational performance. It is designed for C‑suite executives (CEO, CFO, COO) and board members, summarising the most critical KPIs across the entire business.

**Core Metrics and KPIs** (varies by industry):

- **Financial**: Revenue, Profit, Margin %, Cash Flow, EBITDA.

- **Operational**: Customer Satisfaction (NPS), Employee Engagement, Inventory Turnover.

- **Sales**: Total Sales, Growth %, Market Share.

- **Customer**: Customer Lifetime Value, Churn Rate.

- **Strategic**: Goal Progress (e.g., ESG targets, Project Milestones).


**Key Principles**:

- **Simplicity**: Only the most important KPIs – no more than 8‑10.

- **Visual Hierarchy**: KPIs at the top, trends in the middle, details on request.

- **Context**: Show targets and comparisons (vs prior period, vs budget).

- **Actionable**: Enable drill‑through to detailed reports for investigation.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Executives are time‑poor. They need to understand the health of the business in seconds, not minutes. An executive dashboard provides that "pulse".

- **Use cases**:

  - A **CEO** starts every morning by reviewing the executive dashboard to see if anything needs urgent attention.
  
  - A **Board** uses the dashboard during quarterly meetings to review strategic progress.
  
  - A **COO** monitors operational KPIs and identifies areas needing intervention.
  

---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**: Consolidate data from multiple sources – sales, finance, HR, customer, operations. This often involves a data warehouse or published data sources.


2. **Data Modeling**: Create a star schema with a central facts table or multiple facts (Sales, Finance, HR) sharing common dimensions (Date, Department).


3. **Calculated Fields**:

   - `Total Revenue = SUM([Revenue])`

   - `Net Profit = SUM([Profit])`

   - `Profit Margin % = SUM([Profit]) / SUM([Revenue])`

   - `Customer NPS` (Net Promoter Score) – likely from survey data.

   - `Employee Engagement Score` – from survey data.

   - `Inventory Turnover = SUM([COGS]) / AVG([Inventory Value])`

   - `Sales Growth % = (SUM([Revenue]) - [Revenue LY]) / [Revenue LY]`

4. **Visuals**:

   - **Top‑row KPI Cards**: 4‑6 key numbers with trend arrows.

   - **Line Charts**: Revenue and Profit trends over time.

   - **Gauges**: Showing performance against targets (e.g., Profit Margin vs Target).

   - **Matrix**: KPI performance across business units or regions.

   - **Slicers**: Year and Quarter (to compare periods).

   - **Drill‑through**: Clicking on a KPI opens a detailed report page.


5. **Design**:

   - Use a clean, minimalist theme with brand colours.

   - Avoid clutter.

   - Ensure mobile responsiveness.


---

### Practical Examples

- **Example**: The CEO opens the dashboard and sees that the Profit Margin KPI has dropped from 18% to 15%. They drill through to the financial report, see that COGS increased, and initiate a cost‑cutting review.

---

### Hands‑on Exercises

1. **Dataset**: Consolidate at least three different data sources (e.g., Sales, Finance, HR).

2. **Build the Model**:

   - Create a unified date table.

   - Connect all facts to common dimensions.

3. **Create Calculated Fields**:

   - Revenue, Profit, Margin %, NPS, Employee Engagement, Turnover.

   - Include targets for each.
   
4. **Design the Dashboard**:

   - Use a minimal layout with KPIs at the top.

   - Add trend lines and gauges.

   - Add drill‑through to detailed pages.

5. **Add Interactivity**: Slicers for Year and Business Unit.


---

### Mini Quiz

1. What is the primary goal of an Executive KPI Dashboard?

2. How many KPIs should an executive dashboard typically display?

3. Why is it important to show targets on executive dashboards?

4. What visual types are best for executive dashboards?

5. How can you make an executive dashboard actionable?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Too many KPIs – information overload | Limit to 6‑10 key numbers |
| No context (targets, comparisons) – numbers alone don't tell the story | Include targets, prior period, and variance |
| Cluttered design – hard to read | Use whitespace, consistent fonts, and brand colours |
| No drill‑through – users can't investigate | Implement drill‑through for deeper analysis |
| Ignoring mobile – executives view on phones | Design mobile‑optimised layout |

---

### Interview Questions

1. **How would you design a dashboard for the CEO?**  

   *Answer*: I would start by interviewing the CEO and their leadership team to understand their top priorities. I would limit the dashboard to 6‑10 key KPIs, show them with targets and trends, and provide drill‑through for deeper investigation. I would use a clean, brand‑aligned design and ensure mobile responsiveness.

2. **What is the difference between an executive dashboard and a departmental dashboard?**  

   *Answer*: An executive dashboard is high‑level and cross‑functional, summarising the overall health of the organisation. Departmental dashboards are more detailed and focus on specific areas (e.g., sales, HR, operations).

3. **How do you ensure the executive dashboard remains relevant over time?**  

   *Answer*: I would schedule regular reviews with the executive team to update KPIs as business priorities evolve. I would also monitor usage metrics to see which KPIs are most viewed.

---

### Assignment and Dashboard Projects

**Assignment 10.2** – Build an Executive KPI Dashboard:

- Use data from at least three different areas (e.g., Sales, Finance, HR).

- Define 6‑8 KPIs with targets.

- Create trend lines and gauges.

- Implement drill‑through to at least one detailed report.

- Submit the `.twbx` file and a one‑page explanation of your KPI selection.


---

### Summary and Revision Notes

- Executive dashboards are **high‑level, focused, and actionable**.

- Limit to **6‑10 KPIs**.

- Always include **context** (targets, trends, comparisons).

- Use **clean design** and **brand colours**.

- Enable **drill‑through** for deeper investigation.

---

## Project 10.3 – HR Analytics Dashboard

### Concept Explanation

An **HR Analytics Dashboard** provides insights into workforce dynamics – headcount, attrition, diversity, hiring, and employee engagement. It helps HR leaders and management make data‑driven decisions about talent management.

**Core Metrics and KPIs**:

- **Headcount**: Total employees, by department, location, and job level.

- **Attrition / Turnover Rate**: Overall and segmented by department, tenure, performance rating.

- **Hiring Metrics**: Time‑to‑fill, cost‑per‑hire, source of hire.

- **Diversity & Inclusion**: Gender, ethnicity, age distribution.

- **Employee Engagement**: Survey scores, satisfaction ratings.

- **Promotion Rates**: % of employees promoted, average tenure to promotion.

- **Absenteeism**: Average days absent, by department.


**Key Dimensions**: Time (Date of hire, termination), Department, Location, Job Level, Gender, Age Group, Tenure Band.


---

### Importance and Real‑World Use Cases

- **Why it matters**: People are an organisation's greatest asset. HR dashboards help reduce attrition, improve diversity, and ensure the right talent is in the right place.

- **Use cases**:

  - A **HR Director** monitors attrition and identifies departments with high turnover.

  - A **Talent Acquisition Manager** tracks hiring metrics to optimise recruitment.

  - A **Diversity Officer** tracks diversity metrics and reports to the board.


---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Employee master data (EmployeeID, Name, Gender, Ethnicity, Date of Birth, Department, Job Level, Salary, Hire Date, Termination Date, ManagerID).

   - Attrition data (terminations).

   - Hiring data (applications, offers, hires).

   - Employee engagement surveys.


2. **Data Modeling**:

   - Fact tables: `Employee` (current snapshot) and `Terminations` (events).

   - Dimension tables: `Date`, `Department`, `Location`, `Job Level`.


3. **Calculated Fields**:

   - `Headcount = COUNT([EmployeeID])`

   - `Active Employees = COUNT(IF [Status] = "Active" THEN [EmployeeID] END)`

   - `Terminations = COUNT([Terminations])`

   - `Attrition Rate % = [Terminations] / ([Active Employees] + [Terminations])`

   - `Turnover Rate = SUM([Terminations]) / AVG([Headcount])` – more sophisticated.

   - `Average Tenure = AVG(DATEDIFF('day', [Hire Date], IFNULL([Termination Date], TODAY())))`

   - `Gender Diversity % = COUNT(IF [Gender] = "Female" THEN [EmployeeID] END) / [Headcount]`

   - `Time to Fill = AVG(DATEDIFF('day', [JobOpenDate], [HireDate]))`


4. **Visuals**:

   - **Top‑row KPIs**: Headcount, Attrition Rate %, Average Tenure, Time to Fill.

   - **Line Chart**: Headcount trend over time.

   - **Column Chart**: Attrition Rate by Department and Tenure Band.

   - **Donut Chart**: Headcount by Gender and by Department.

   - **Matrix**: Headcount and Turnover by Department and Job Level.

   - **Slicers**: Year, Department, Location.

---

### Practical Examples

- **Example**: The HR dashboard shows that the Engineering department has a 25% attrition rate, well above the company average of 12%. The HR Director investigates exit interviews and finds that engineers are leaving for higher salaries. They propose a salary review.

---

### Hands‑on Exercises

1. **Dataset**: Find or create an HR dataset with at least 500 employees, including hire and termination dates, department, gender, age, and salary.


2. **Build the Model**:

   - Load employee data, date table, and any other dimensions.

   - For attrition, calculate active vs terminated status in a calculated field.


3. **Create Calculated Fields**:

   - Headcount, Active Headcount, Terminated.

   - Attrition Rate (monthly and YTD).

   - Average Tenure.

   - Diversity % (e.g., Female %).


4. **Design the Dashboard**:

   - Add KPIs at the top.

   - Add a line chart for headcount trend.

   - Add a bar chart for attrition by department.

   - Add a donut chart for gender diversity.

   - Add a matrix for detailed department metrics.

---

### Mini Quiz

1. How would you calculate the attrition rate in Tableau?

2. Why is average tenure an important HR metric?

3. How do you calculate the number of active employees at any point in time?

4. What visual would you use to show diversity composition?

5. How can you measure time‑to‑fill in an HR dashboard?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not handling leavers correctly – headcount is overstated | Use a snapshot table or calculate active headcount based on hire and termination dates |
| Using a single employee snapshot – doesn't show trends | Use a date table and calculate headcount over time |
| Ignoring part‑time or contract employees – skews averages | Clearly define the employee population |
| Not including visual indicators for diversity targets | Include target lines or reference values |
| Forgetting to secure sensitive data (PII) | Apply RLS to restrict access to sensitive employee details |

---

### Interview Questions

1. **How would you calculate the attrition rate in Tableau?**  

   *Answer*: Attrition Rate = (Number of Terminations in Period / Average Headcount in Period). I would use a calculated field: `SUM([Terminations]) / AVG([Headcount])`.

2. **What measures would you include in an HR dashboard for the board?**  

   *Answer*: Total Headcount, Attrition Rate, Gender Diversity %, Average Tenure, and Promotion Rate.

3. **How do you handle employee transfers between departments in an attrition analysis?**  

   *Answer*: I would use the department at the time of termination. For active employees, I would use their current department. I might also create a separate "movement" table for transfers.

---

### Assignment and Dashboard Projects

**Assignment 10.3** – Build an HR Analytics Dashboard:

- Use a sample HR dataset.

- Include headcount, attrition, diversity, and hiring metrics.

- Create at least 5 calculated fields.

- Design a professional dashboard with KPIs, charts, and a matrix.

- Submit the `.twbx` file.


---

### Summary and Revision Notes

- HR dashboards track **headcount, attrition, diversity, and hiring**.

- Attrition is calculated as **terminations / average headcount**.

- Use a **date table** to track headcount over time.

- Secure **PII** with RLS.

- Include **diversity targets** and **benchmarks**.

---

## Project 10.4 – Financial Dashboard

### Concept Explanation

A **Financial Dashboard** provides a comprehensive view of an organisation's financial health. It is used by CFOs, finance directors, and analysts to monitor profit and loss (P&L), cash flow, budget vs actual, and key financial ratios.

**Core Metrics and KPIs**:

- **Revenue** (Gross and Net)

- **Cost of Goods Sold (COGS)** and **Gross Profit**

- **Operating Expenses** (SG&A, R&D, etc.)

- **Operating Income / EBIT**

- **Net Income**

- **Profit Margins** (Gross, Operating, Net)

- **Budget vs Actual Variance**

- **Cash Flow**

- **Financial Ratios** (Current Ratio, Quick Ratio, Debt-to-Equity)

**Key Dimensions**: Time (Fiscal Year, Quarter, Month), Account Category, Department, Product Line, Region.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Financial dashboards are used in board meetings, investor presentations, and strategic planning. They provide a single source of truth for financial performance.

- **Use cases**:

  - A **CFO** presents monthly financial results to the board.

  - A **Financial Controller** monitors budget vs actual and investigates variances.

  - An **Investment Analyst** uses the dashboard to assess the company's financial health.


---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - General Ledger data (accounts, debits, credits).

   - P&L structure (account hierarchy).

   - Budget data (planned vs actual).

   - Balance sheet data (assets, liabilities, equity).


2. **Data Modeling**:

   - Fact tables: `FinancialTransactions` and `Budget`.

   - Dimension tables: `Account` (with hierarchy), `Date`, `Department`.

   - Connect facts to `Account` and `Date`.


3. **Calculated Fields**:

   - `Revenue = SUM(IF [Account Type] = "Revenue" THEN [Amount] END)`

   - `COGS = SUM(IF [Account Type] = "COGS" THEN [Amount] END)`

   - `Gross Profit = [Revenue] - [COGS]`

   - `Gross Margin % = [Gross Profit] / [Revenue]`

   - `Operating Expenses = SUM(IF [Account Type] = "Expense" THEN [Amount] END)`

   - `Net Income = [Gross Profit] - [Operating Expenses]`

   - `Budget Variance = [Actual] - [Budget]`

   - `Variance % = [Budget Variance] / [Budget]`


4. **Visuals**:

   - **Top‑row KPI Cards**: Revenue, Net Income, Gross Margin %, Operating Margin %.

   - **Waterfall Chart**: Show the journey from Revenue to Net Income.

   - **Column Chart**: Revenue and Net Income by Quarter (with budget overlay).

   - **Bar Chart**: Budget vs Actual by Account Category.

   - **Matrix**: P&L statement with Actual, Budget, Variance, and Variance %.

   - **Slicers**: Fiscal Year, Quarter, Department.


---

### Practical Examples

- **Example**: The CFO sees that Operating Expenses are 10% over budget due to higher marketing spend. They drill down to the marketing department and adjust the Q4 forecast.

---

### Hands‑on Exercises

1. **Dataset**: Create or download a financial dataset with at least 5 years of monthly data, including account hierarchy, actuals, and budget.


2. **Build the Model**:

   - Load transactions, budget, account hierarchy, and date.

   - Create relationships.

   - Define the account hierarchy in the `Account` table.


3. **Create Calculated Fields**:

   - Revenue, COGS, Gross Profit, Operating Expenses, Net Income.

   - Budget measures (if you have a budget table).

   - Variance measures.


4. **Design the Dashboard**:

   - Add a waterfall chart.

   - Add a column chart with budget overlay.

   - Add a matrix showing the full P&L.


5. **Add Interactivity**: Slicers for Year and Department.


---

### Mini Quiz

1. What is the difference between Gross Profit and Net Income?

2. Why is a waterfall chart useful for financial analysis?

3. How do you calculate Budget Variance in Tableau?

4. What is the purpose of an account hierarchy in a financial model?

5. How can you show both actuals and budget in the same visual?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not having a proper account hierarchy – ad‑hoc groupings | Use a dimension table with account hierarchy for consistent reporting |
| Mixing up debit and credit signs – wrong numbers | Ensure all amounts are normalised (e.g., revenue as positive, expenses as positive or negative consistently) |
| Not handling fiscal year correctly | Use a fiscal calendar if needed |
| Ignoring currency conversion – global companies need USD reporting | Apply currency rates using calculated fields or Tableau Prep |
| Not including budget – actuals alone are meaningless | Always include budget or forecast for context |

---

### Interview Questions

1. **How would you design a financial dashboard that shows actual vs budget?**  

   *Answer*: I would use a fact table with actuals and a separate budget fact table, both connected to Account and Date dimensions. I would create calculated fields for Actual, Budget, Variance, and Variance %. I would use a matrix for the P&L and a bar chart for variance by department.

2. **What Tableau feature would you use to show the journey from revenue to net income?**  

   *Answer*: I would use a **waterfall chart** – it shows the cumulative effect of each component (revenue, COGS, expenses, etc.) leading to net income.

3. **How do you handle exchange rates in a financial dashboard?**  

   *Answer*: I would have a currency dimension and an exchange rate fact table. In Tableau, I would use `SUMX`-style calculations to multiply local currency amounts by the relevant exchange rate for the given date and currency. Since Tableau doesn't have `SUMX`, I would use a data source calculation or Tableau Prep to apply the exchange rate before loading.

---

### Assignment and Dashboard Projects

**Assignment 10.4** – Build a Financial Dashboard:

- Use a sample financial dataset or create one.

- Include actual and budget data.

- Create calculated fields for P&L and variances.

- Build a waterfall chart and a matrix P&L.

- Add slicers for Year and Department.

- Submit the `.twbx` file.


---

### Summary and Revision Notes

- Financial dashboards focus on **P&L, margins, and budget vs actual**.

- Use a **waterfall chart** to show the journey from revenue to net income.

- **Account hierarchy** is essential for structured reporting.

- **Variance analysis** (budget vs actual) is a core requirement.

- Always include **context** – comparisons to prior periods and budgets.

---

## Project 10.5 – Customer Segmentation Dashboard

### Concept Explanation

A **Customer Segmentation Dashboard** analyses customer data to group customers into meaningful segments based on behaviour, demographics, or value. It helps marketing, sales, and product teams personalise their approach and maximise customer lifetime value.

**Core Metrics and KPIs**:

- **RFM Analysis**: Recency, Frequency, Monetary.

- **Customer Lifetime Value (CLV)**.

- **Customer Acquisition Cost (CAC)**.

- **Churn Rate**.

- **Average Order Value (AOV)**.

- **Purchase Frequency**.

- **Segmentation**: High‑value, loyal, at‑risk, lost.

**Key Dimensions**: Customer, Date, Product, Channel, Region.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Understanding customer segments enables personalised marketing, better retention, and optimised resource allocation.

- **Use cases**:

  - A **Marketing Director** uses RFM to target high‑value customers with exclusive offers.
  
  - A **Customer Success Manager** identifies at‑risk customers and intervenes proactively.
  
  - A **Product Manager** analyses purchase patterns to improve product recommendations.
  

---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Customer master (CustomerID, Name, Region, JoinDate, Segment).

   - Transaction table (OrderID, CustomerID, OrderDate, Revenue, ProductID).

   - Product table.


2. **Data Modeling**:

   - Fact: `Transactions`.

   - Dimensions: `Customer`, `Product`, `Date`.


3. **Calculated Fields**:

   - `Total Revenue = SUM([Revenue])`

   - `Total Customers = COUNTD([CustomerID])`

   - `Average Order Value (AOV) = SUM([Revenue]) / COUNTD([OrderID])`

   - `Purchase Frequency = COUNTD([OrderID]) / COUNTD([CustomerID])`

   - `Customer Lifetime Value (CLV) = AVG({ FIXED [CustomerID] : SUM([Revenue]) })`

   - `Churn Rate = COUNT(IF [Last Purchase] < DATEADD('month', -3, TODAY()) THEN [CustomerID] END) / COUNTD([CustomerID])`

   - `RFM Scores`: Create calculated fields for Recency (days since last purchase), Frequency (count of orders), Monetary (total spend).


4. **Visuals**:

   - **KPIs**: Total Revenue, Total Customers, AOV, CLV, Churn Rate.

   - **Scatter Chart**: Frequency vs Monetary (to identify high‑value customers).

   - **RFM Grid (Matrix)** : Segment customers into RFM groups.

   - **Bar Chart**: Revenue by Customer Segment (RFM groups).

   - **Slicers**: Region, Product Category, Time period.

---

### Practical Examples

- **Example**: The dashboard shows that 10% of customers (high‑value segment) account for 60% of revenue. The marketing team creates a loyalty program targeted at these customers.

---

### Hands‑on Exercises

1. **Dataset**: Use a transaction dataset with at least 10,000 records, including CustomerID, OrderDate, and Revenue.


2. **Build the Model**:

   - Load transactions, customers, and products.

   - Create relationships.

3. **Create Calculated Fields**:

   - Revenue, Customers, AOV, CLV, Churn Rate.

   - RFM scores (use calculated fields or table calculations).

4. **Design the Dashboard**:

   - Add KPIs.

   - Add a scatter chart for frequency vs monetary.

   - Add a matrix showing RFM segments.

   - Add a cohort analysis (if possible).


---

### Mini Quiz

1. What does RFM stand for?

2. How is Customer Lifetime Value (CLV) typically calculated?

3. What is the difference between churn rate and retention rate?

4. Why is Average Order Value (AOV) important?

5. How can you identify at‑risk customers?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using average CLV without considering lifetime – misleading | Use cohort‑based CLV or predictive models |
| Not including time dimension – churn is time‑based | Always include date filters for churn analysis |
| Ignoring customer acquisition cost – CLV without CAC is incomplete | Include CAC if available |
| Using only transaction data – missing customer attributes | Enrich with customer demographics and behaviour |
| Not using RFM segmentation – losing actionable insights | Implement RFM analysis for segmentation |

---

### Interview Questions

1. **How would you calculate churn rate in Tableau?**  

   *Answer*: Churn Rate = (Customers lost in period / Customers at start of period). I would identify customers who made a purchase in the previous period but not in the current period, divide by the count at the start.

2. **What is RFM analysis and why is it useful?**  

   *Answer*: RFM stands for Recency, Frequency, Monetary. It segments customers based on how recently they bought, how often they buy, and how much they spend. It helps identify your best customers and those at risk.

3. **How do you calculate Customer Lifetime Value in Tableau?**  

   *Answer*: A simple approach is `AVG({ FIXED [CustomerID] : SUM([Revenue]) })` for historical CLV. A more advanced approach would project future purchases using predictive analytics.

---

### Assignment and Dashboard Projects

**Assignment 10.5** – Build a Customer Segmentation Dashboard:

- Use a transaction dataset.

- Include KPIs: Revenue, Customers, AOV, CLV, Churn Rate.

- Implement RFM segmentation.

- Include a cohort analysis (monthly cohorts).

- Submit the `.twbx` file.


---

### Summary and Revision Notes

- Customer dashboards focus on **value, churn, and segmentation**.

- **RFM analysis** is a powerful segmentation tool.

- **CLV** helps prioritise high‑value customers.

- **Cohort analysis** reveals retention patterns over time.


---

## Project 10.6 – Marketing Campaign Dashboard

### Concept Explanation

A **Marketing Campaign Dashboard** provides a consolidated view of marketing activities, campaigns, and their effectiveness. It helps marketing leaders optimise spend, channels, and messaging.

**Core Metrics and KPIs**:

- **Marketing Spend**: Total spend, by channel (Paid Search, Social, Email, etc.).

- **Impressions, Clicks, CTR (Click‑Through Rate)**.

- **Conversions and Conversion Rate**.

- **Cost per Lead (CPL) and Cost per Acquisition (CPA)**.

- **Return on Investment (ROI)** and **ROAS (Return on Ad Spend)**.

- **Channel Performance**: Comparison of channels on key metrics.

- **Pipeline Contribution**: Revenue generated from marketing‑sourced leads.

**Key Dimensions**: Campaign, Channel, Date, Product, Lead Source, Geography.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Marketing budgets are often large and under scrutiny. A marketing dashboard provides transparency on ROI, identifies best‑performing channels, and enables data‑driven budget allocation.

- **Use cases**:

  - A **CMO** reviews channel performance and reallocates budget to the highest‑ROI channels.

  - A **Digital Marketing Manager** monitors daily campaign performance and adjusts bids.

  - A **Marketing Analyst** reports on marketing‑sourced revenue.


---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Campaign spend (Channel, Campaign, Date, Spend).
   
   - Web analytics (Impressions, Clicks, Sessions).
   
   - CRM data (Leads, Opportunities, Closed Won).
   
   - Attribution data (Lead Source, First Touch, Last Touch).
   

2. **Data Modeling**:

   - Fact tables: `Spend`, `WebAnalytics`, `Leads`, `Opportunities`.
   
   - Dimensions: `Campaign`, `Channel`, `Date`, `Lead Source`.
   

3. **Calculated Fields**:

   - `Total Spend = SUM([Spend])`
   
   - `Impressions = SUM([Impressions])`
   
   - `Clicks = SUM([Clicks])`
   
   - `CTR = [Clicks] / [Impressions]`
   
   - `Conversions = COUNT([Leads])`
   
   - `Conversion Rate = [Conversions] / [Clicks]`
   
   - `CPL = [Total Spend] / [Conversions]`
   
   - `ROI = ([Revenue from Marketing] - [Total Spend]) / [Total Spend]`
   
   - `ROAS = [Revenue from Marketing] / [Total Spend]`
   

4. **Visuals**:

   - **KPIs**: Total Spend, Conversions, CPL, ROAS.

   - **Bar Chart**: Spend and Revenue by Channel.

   - **Line Chart**: Clicks, Conversions, and Spend over time.

   - **Scatter Chart**: Spend vs Revenue by Campaign (to identify over/under performers).

   - **Matrix**: Channel performance with Spend, Clicks, Conversions, CPL, ROI.

   - **Slicers**: Date range, Channel, Campaign.


---

### Practical Examples

- **Example**: The marketing dashboard shows that social media has a ROAS of 5x, while paid search is only 2x. The CMO reallocates 20% of the budget from search to social.

---

### Hands‑on Exercises

1. **Dataset**: Create or download a marketing dataset with spend, clicks, conversions, and revenue by campaign and channel.

2. **Build the Model**:

   - Load the data and create relationships.

3. **Create Calculated Fields**:

   - Spend, Clicks, CTR, Conversions, CPL, ROI, ROAS.

4. **Design the Dashboard**:

   - Add KPIs.

   - Add a bar chart for channel performance.

   - Add a scatter chart for campaign ROI.

   - Add a matrix for detailed campaign data.

---

### Mini Quiz

1. What is the difference between CPL and CPA?

2. How is ROAS calculated?

3. Why is CTR an important marketing metric?

4. What visual would you use to compare channel performance?

5. How can you attribute revenue to marketing campaigns?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not including attribution – revenue is misattributed | Use multi‑touch attribution models |
| Ignoring lead quality – conversions alone aren't enough | Include pipeline revenue and conversion rates |
| Not comparing channels on a common metric – apples vs oranges | Use consistent metrics like ROI or CPA across channels |
| Using last‑touch attribution only – over‑emphasises the last channel | Use first‑touch, linear, or weighted attribution models |
| Not tracking spend accurately – ROI is incorrect | Ensure spend data is granular and aligned with campaign dates |

---

### Interview Questions

1. **How would you calculate marketing ROI in Tableau?**  

   *Answer*: ROI = (Revenue from Marketing - Marketing Spend) / Marketing Spend. I would use a calculated field `ROI = ([Marketing Revenue] - [Total Spend]) / [Total Spend]`.

2. **What is the difference between cost per lead and cost per acquisition?**  

   *Answer*: CPL is the cost to generate a lead (a potential customer). CPA is the cost to acquire a paying customer. CPA is usually higher because only a fraction of leads convert.

3. **How do you handle attribution in a marketing dashboard?**  

   *Answer*: I would use a multi‑touch attribution model. In Tableau, I can assign weights to each touchpoint using a fact table of touchpoints and calculate weighted revenue contribution.

---

### Assignment and Dashboard Projects

**Assignment 10.6** – Build a Marketing Performance Dashboard:

- Use a sample marketing dataset.

- Include KPIs: Spend, Conversions, CPL, ROAS.

- Include channel comparison and campaign ROI.

- Submit the `.twbx` file.


---

### Summary and Revision Notes

- Marketing dashboards track **spend, ROI, and channel performance**.

- **CPL, CPA, ROAS** are key metrics.

- **Attribution** is critical for accurate ROI.

- Use **scatter charts** to identify high/low performing campaigns.


---

## Project 10.7 – Supply Chain Dashboard

### Concept Explanation

A **Supply Chain Dashboard** provides visibility into inventory, procurement, logistics, and supplier performance. It helps supply chain managers optimise operations, reduce costs, and ensure product availability.

**Core Metrics and KPIs**:

- **Inventory**: Inventory Value, Inventory Turnover, Days Inventory Outstanding (DIO).

- **Procurement**: Supplier Performance, Lead Time, Purchase Order Cycle Time.

- **Logistics**: On‑Time Delivery Rate, Shipping Cost, Delivery Accuracy.

- **Stock**: Stock‑out Rate, Backorder Rate, Reorder Point.

**Key Dimensions**: Product, Supplier, Warehouse, Region, Time.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Supply chain inefficiencies cost organisations billions. A supply chain dashboard helps identify bottlenecks, reduce costs, and improve customer satisfaction.

- **Use cases**:

  - A **Supply Chain Manager** monitors inventory turnover and identifies slow‑moving items.
  
  - A **Procurement Officer** tracks supplier performance and renegotiates contracts.
  
  - A **Logistics Manager** monitors on‑time delivery and shipping costs.
  

---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Inventory data (Product, Warehouse, Quantity, Value, Last Sale Date).

   - Procurement data (Supplier, Lead Time, Purchase Orders).

   - Logistics data (Shipping Cost, Delivery Date, Order Date).


2. **Data Modeling**:

   - Fact tables: `Inventory`, `Purchases`, `Shipments`.

   - Dimensions: `Product`, `Supplier`, `Warehouse`, `Date`.


3. **Calculated Fields**:

   - `Inventory Value = SUM([Quantity] * [Unit Cost])`

   - `Inventory Turnover = SUM([COGS]) / AVG([Inventory Value])`

   - `Days Inventory Outstanding (DIO) = AVG([Inventory Value]) / [Daily COGS]`

   - `Stock‑out % = COUNT(IF [Quantity] = 0 THEN [ProductID] END) / COUNT([ProductID])`

   - `On‑Time Delivery % = COUNT(IF [Delivery Date] <= [Expected Date] THEN [OrderID] END) / COUNT([OrderID])`

   - `Supplier Performance = AVG([Lead Time])`


4. **Visuals**:

   - **KPIs**: Inventory Value, Inventory Turnover, DIO, Stock‑out %.

   - **Bar Chart**: Inventory Value by Product Category.

   - **Scatter Chart**: Inventory Value vs Turnover (to identify slow‑moving high‑value items).

   - **Pareto Chart**: ABC Analysis.

   - **Matrix**: Inventory Quantity and Value by Warehouse and Product.

   - **Slicers**: Category, Supplier, Warehouse.

---

### Practical Examples

- **Example**: The supply chain dashboard shows that 20% of items (A items) account for 80% of the inventory value. The supply chain manager focuses on optimising replenishment for these high‑value items.

---

### Hands‑on Exercises

1. **Dataset**: Create or download a supply chain dataset with inventory, purchasing, and shipping information.

2. **Build the Model**:

   - Load inventory, purchases, and shipment data.

   - Create relationships.

3. **Create Calculated Fields**:

   - Inventory Value, Turnover, DIO, Stock‑out %, ABC Classification.

4. **Design the Dashboard**:

   - Add KPIs.

   - Add a bar chart for category value.

   - Add a scatter chart for value vs turnover.

   - Add a matrix for warehouse breakdown.

   - Add an aging table.

---

### Mini Quiz

1. What does Inventory Turnover measure?

2. What is Days Inventory Outstanding (DIO)?

3. How do you classify items using ABC analysis?

4. What visual would you use to show aging inventory?

5. Why is stock‑out rate an important KPI?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not using average inventory – turnover must be calculated over time | Use average inventory over the period |
| Ignoring seasonal fluctuations – turnover may vary | Use rolling averages or year‑over‑year comparisons |
| Not tracking aging – obsolete inventory hides in the system | Always include aging buckets |
| Using only quantity, not value – ignores the financial impact | Use both quantity and value |
| Not including reorder points – users can't act | Include reorder point and suggested order quantity |

---

### Interview Questions

1. **How would you calculate inventory turnover in Tableau?**  

   *Answer*: Inventory Turnover = COGS / Average Inventory. Average Inventory = `AVG({ FIXED [Date] : [Inventory Value] })` over the period.

2. **What is the purpose of ABC analysis in inventory management?**  

   *Answer*: ABC analysis classifies inventory based on value. A items are high‑value, low‑quantity and need tight control; C items are low‑value, high‑quantity and can be managed with simpler controls.

3. **How do you identify slow‑moving inventory?**  

   *Answer*: I calculate the days since the last sale for each SKU and use aging buckets. I can also compare turnover rates to identify items with low turnover.

---

### Assignment and Dashboard Projects

**Assignment 10.7** – Build a Supply Chain Dashboard:

- Use a sample supply chain dataset.

- Include KPIs: Inventory Value, Turnover, DIO, Stock‑out %.

- Include ABC analysis and aging analysis.

- Add a matrix for warehouse and product details.

- Submit the `.twbx` file.

---

### Summary and Revision Notes

- Supply chain dashboards focus on **inventory value, turnover, and aging**.

- **ABC analysis** helps prioritise management efforts.

- **Aging** prevents obsolescence.

- Use **scatter charts** to identify outliers (high value, low turnover).

- Include **reorder points** for actionable insights.

---

## Project 10.8 – Healthcare Analytics Dashboard

### Concept Explanation

A **Healthcare Analytics Dashboard** provides insights into patient outcomes, operational efficiency, and financial performance in healthcare settings. It is used by hospital administrators, clinicians, and public health officials.

**Core Metrics and KPIs**:

- **Patient Metrics**: Patient Volume, Average Length of Stay (ALOS), Readmission Rate, Patient Satisfaction (HCAHPS).

- **Operational Metrics**: Bed Occupancy Rate, Emergency Department (ED) Wait Time, Surgical Turnaround Time.

- **Financial Metrics**: Cost per Patient, Revenue per Patient, Payer Mix.

- **Clinical Quality**: Mortality Rate, Infection Rate, Treatment Compliance.


**Key Dimensions**: Date, Department, Diagnosis, Procedure, Patient Demographics (Age, Gender, Region), Payer.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Healthcare is data‑intensive and high‑stakes. Dashboards help improve patient outcomes, reduce costs, and ensure regulatory compliance.

- **Use cases**:

  - A **Hospital Administrator** monitors bed occupancy to manage capacity.

  - A **Quality Manager** tracks readmission rates to identify improvement areas.

  - A **Financial Analyst** monitors cost per patient and payer mix.


---

### Step‑by‑Step Demonstration

**Project Plan**:

1. **Data Acquisition**:

   - Patient records (PatientID, Admission Date, Discharge Date, Diagnosis, Procedure, Age, Gender, Payer).

   - Operational data (Bed Occupancy, ED Wait Times, Surgical Turnaround).

   - Financial data (Costs, Revenue, Payer Mix).


2. **Data Modeling**:

   - Fact tables: `PatientVisits`, `SurgicalCases`, `FinancialTransactions`.

   - Dimensions: `Date`, `Department`, `Diagnosis`, `Procedure`, `Patient Demographics`, `Payer`.


3. **Calculated Fields**:

   - `Patient Volume = COUNT([PatientID])`

   - `Average Length of Stay (ALOS) = AVG(DATEDIFF('day', [Admission Date], [Discharge Date]))`

   - `Readmission Rate = COUNT(IF [Readmission] = TRUE THEN [PatientID] END) / [Patient Volume]`

   - `Bed Occupancy Rate = SUM([Occupied Beds]) / SUM([Total Beds])`

   - `ED Wait Time = AVG([Wait Time])`

   - `Cost per Patient = SUM([Cost]) / [Patient Volume]`

   - `Revenue per Patient = SUM([Revenue]) / [Patient Volume]`


4. **Visuals**:

   - **KPIs**: Patient Volume, ALOS, Readmission Rate, Bed Occupancy Rate.

   - **Line Chart**: Patient Volume and ALOS over time.

   - **Bar Chart**: Readmission Rate by Department or Diagnosis.

   - **Scatter Chart**: Cost vs Revenue per Patient (to identify outliers).

   - **Matrix**: Patient Metrics by Department and Payer.

   - **Slicers**: Date, Department, Payer.

---

### Practical Examples

- **Example**: A hospital dashboard shows that the Cardiology department has a higher than average readmission rate. The quality team investigates and implements a new discharge follow‑up protocol, reducing readmissions by 15%.

---

### Hands‑on Exercises

1. **Dataset**: Find or create a healthcare dataset with patient visits, operations data, and financial data.

2. **Build the Model**:

   - Load patient, operational, and financial data.

   - Create relationships.


3. **Create Calculated Fields**:

   - Patient Volume, ALOS, Readmission Rate, Bed Occupancy Rate, ED Wait Time, Cost per Patient.


4. **Design the Dashboard**:

   - Add KPIs.

   - Add a line chart for patient volume and ALOS.

   - Add a bar chart for readmission rates.

   - Add a matrix for department‑level metrics.


---

### Mini Quiz

1. What is Average Length of Stay (ALOS) and why is it important?

2. How do you calculate readmission rate?

3. What is bed occupancy rate used for?

4. Why is patient satisfaction important in healthcare analytics?

5. What is the difference between cost per patient and revenue per patient?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not including readmission data – misses a key quality metric | Always include readmission rates |
| Ignoring patient demographics – misses disparities | Segment by age, gender, and region |
| Not handling patient privacy (PII) – compliance risk | Apply RLS to restrict access to sensitive patient data |
| Using only financial metrics – missing clinical outcomes | Balance financial and clinical metrics |
| Not including trends – can't see improvement or decline | Include time‑based analysis for all key metrics |

---

### Interview Questions

1. **How would you design a healthcare dashboard for a hospital administrator?**  

   *Answer*: I would start by understanding their key priorities – patient outcomes, operational efficiency, and financial performance. I would include KPIs like patient volume, ALOS, readmission rate, bed occupancy, and cost per patient. I would use a clean layout with KPIs at the top, trend charts in the middle, and detailed matrices at the bottom.

2. **What is Average Length of Stay (ALOS) and how would you calculate it in Tableau?**  

   *Answer*: ALOS is the average number of days a patient stays in the hospital. I would calculate it as `AVG(DATEDIFF('day', [Admission Date], [Discharge Date]))`.

3. **How do you handle patient privacy in a healthcare dashboard?**  

   *Answer*: I would use Row‑Level Security to restrict access to patient‑level data. I would also anonymise patient IDs and ensure only authorised users have access to sensitive data.

---

### Assignment and Dashboard Projects

**Assignment 10.8** – Build a Healthcare Analytics Dashboard:

- Use a sample healthcare dataset.

- Include KPIs: Patient Volume, ALOS, Readmission Rate, Bed Occupancy Rate.

- Include trends and department breakdowns.

- Submit the `.twbx` file.


---

### Summary and Revision Notes

- Healthcare dashboards balance **clinical, operational, and financial** metrics.

- **ALOS, readmission rate, and bed occupancy** are key operational metrics.

- **Patient satisfaction** is a critical quality metric.

- Always ensure **patient privacy** through RLS and anonymisation.

---

## Final Phase 10 Assessment

Now that you have completed all eight projects, test your overall understanding of real‑world application.

### Self‑Evaluation Checklist

-  I can design a Sales Performance Dashboard with KPIs, trends, and territory analysis.

-  I can build an Executive KPI Dashboard that consolidates key metrics for leadership.

-  I can create an HR Analytics Dashboard with headcount, attrition, and diversity metrics.

-  I can develop a Financial Dashboard with P&L, waterfall, and variance analysis.

-  I can construct a Customer Segmentation Dashboard with RFM and cohort analysis.

-  I can design a Marketing Campaign Dashboard with ROI, channel performance, and attribution.

-  I can build a Supply Chain Dashboard with inventory value, turnover, and ABC analysis.

-  I can create a Healthcare Analytics Dashboard with patient, operational, and financial metrics.


If you have completed all assignments and feel confident, you are now a **Tableau Expert** ready for any challenge!

---

### Portfolio Recommendations

1. **Select your best 3 projects** and polish them – ensure consistent theming, clear titles, and tooltips.

2. **Publish them to Tableau Public** – make them publicly accessible for your portfolio.

3. **Write case studies** – for each project, write a one‑page summary covering:

   - Business problem.

   - Data sources and transformations.

   - Model design.

   - Key calculated fields.

   - Visuals and interactivity.

   - Insights you would present to stakeholders.

4. **Add to your LinkedIn** – update your profile with links to your published dashboards.

---

**Final Congratulations!**🎉 You have completed all ten phases of this comprehensive Tableau curriculum. You started as a complete beginner and have become a full‑stack Tableau expert, capable of:

- Acquiring and preparing data from any source.

- Building sophisticated data models.

- Writing advanced calculations and LOD expressions.

- Creating stunning, interactive dashboards.

- Designing with accessibility and UX in mind.

- Deploying, sharing, and governing solutions at scale.

- Optimising for performance and security.

- Leading end‑to‑end BI projects across multiple domains.

Remember that the learning never stops – Tableau evolves, and new features are released regularly. Follow the Tableau blog, join the Tableau community, and continue building.

Good luck with your career as a Tableau professional!

---



<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>