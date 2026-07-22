# Phase 9: Performance Optimization and Security

Welcome to **Phase 9** – the final technical phase of your Tableau journey! You have mastered data connection, preparation, calculation, visualisation, dashboard design, and deployment. Now, you will learn how to ensure your dashboards are **fast, secure, and enterprise-ready**.

Performance and security are the hallmarks of professional-grade analytics. A beautiful dashboard that loads slowly or exposes sensitive data is worse than no dashboard at all. In this phase, we cover:

- **Performance Recording** – diagnosing bottlenecks.

- **Optimizing Calculations** – making your formulas faster.

- **Optimizing Data Sources** – speeding up data retrieval.

- **Row-Level Security (RLS)** – restricting data at the user level.

- **Data Security Best Practices** – protecting sensitive information.

- **Tableau Performance Tuning** – holistic optimisation strategies.


These skills will set you apart as a Tableau expert who can build solutions that are not only insightful but also reliable and secure.

---

## Lesson 9.1 – Performance Recording

### Concept Explanation

**Performance Recording** is Tableau's built‑in diagnostic tool that tracks the performance of your dashboard and workbook. It helps you identify which elements are slow – queries, calculations, rendering, or data transfers.

**What Performance Recording captures**:

- **Query execution** – time taken to execute each query against the data source.

- **Compilation** – time to compile queries and calculations.

- **Rendering** – time to draw the visualisations.

- **Data transfer** – time to transfer data from the data source to Tableau.


**How to use Performance Recording**:

1. In Tableau Desktop, go to **Help** → **Settings and Performance** → **Start Performance Recording**.

2. Interact with your dashboard (open it, change filters, etc.).

3. Go to **Help** → **Settings and Performance** → **Stop Performance Recording**.

4. A new workbook opens with a Performance Summary dashboard.

5. Analyse the timings to identify bottlenecks.


**Key metrics to look for**:

- **Total time** – overall performance.

- **Query time** – if high, the data source is slow.

- **Rendering time** – if high, the visual is complex.

- **Compilation time** – if high, calculations are heavy.


---

### Importance and Real‑World Use Cases

- **Why it matters**: You cannot fix what you cannot measure. Performance Recording gives you objective data on where your dashboard is slow, so you can target your optimisation efforts.


- **Use cases**:

  - A **data analyst** uses Performance Recording to identify a slow map that is causing a 10‑second load time.

  - A **dashboard developer** uses it to compare performance before and after optimisation.

  - A **BI team** uses it as part of their quality assurance process.

---

### Step‑by‑Step Demonstration

**Running Performance Recording**:

1. Open your dashboard in Tableau Desktop.

2. Go to **Help** → **Settings and Performance** → **Start Performance Recording**.

3. Refresh your dashboard or interact with it (e.g., change a filter).

4. Go to **Help** → **Settings and Performance** → **Stop Performance Recording**.

5. The Performance Summary workbook opens.


**Analysing the Performance Summary**:

1. The **Summary** tab shows total time and a breakdown.

2. The **Events** tab shows each query and its duration.

3. Look for events with high duration:

   - **Query** events – slow data source queries.

   - **Rendering** events – slow drawing.

   - **Compilation** events – slow calculations.


**Identifying the Slowest Element**:

1. Sort the Events tab by **Duration** (descending).

2. The top event is your biggest bottleneck.

3. Investigate that event (e.g., a specific worksheet or query).


---

### Practical Examples

- **Example 1**: Performance Recording shows that a map with 50,000 marks takes 8 seconds to render. The solution: reduce the number of marks by aggregating data.


- **Example 2**: Performance Recording shows that a query to a SQL database takes 15 seconds. The solution: optimise the query or use an extract.

---

### Hands‑on Exercises

1. Open a dashboard you have built.

2. Start Performance Recording.

3. Interact with the dashboard (open it, change filters).

4. Stop Performance Recording.

5. Open the Performance Summary workbook.

6. Identify the slowest event.

7. Document your findings.


---

### Mini Quiz

1. What is Performance Recording in Tableau?

2. How do you start Performance Recording?

3. What metrics does Performance Recording capture?

4. What does a high query time indicate?

5. How do you identify the slowest element in a dashboard?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not using Performance Recording – guessing instead of measuring | Always use Performance Recording to diagnose issues |
| Running Performance Recording on a cold cache – misleading results | Run it after the dashboard has loaded once (warm cache) |
| Ignoring the results – not acting on the data | Use the results to prioritise optimisation efforts |
| Only focusing on one metric | Look at the whole picture – query time, rendering time, compilation time |

---

### Interview Questions

1. **What is Performance Recording and how do you use it?**  

   *Answer*: Performance Recording is a built‑in tool in Tableau Desktop that tracks dashboard performance. I start it from Help → Settings and Performance → Start Performance Recording, interact with the dashboard, and stop it. The resulting Performance Summary workbook shows query, rendering, and compilation times, helping me identify bottlenecks.



2. **What would you do if Performance Recording shows a high query time?**  

   *Answer*: I would investigate the data source – check if I can use an extract instead of a live connection, optimise the SQL query, or add filters to reduce the data volume.

3. **What is the difference between query time and rendering time?**  

   *Answer*: Query time is the time taken to retrieve data from the data source. Rendering time is the time taken to draw the visualisation on the screen.


---

### Assignment and Dashboard Projects

**Assignment 9.1** – Run Performance Recording on a dashboard:

- Start Performance Recording.

- Interact with the dashboard.

- Stop Performance Recording.

- Identify the slowest event.

- Propose a fix.

- Document your findings.


---

### Summary and Revision Notes

- Performance Recording diagnoses slow dashboards.

- Captures query, rendering, and compilation times.

- Use Help → Settings and Performance → Start/Stop Performance Recording.

- Analyse the Performance Summary workbook.

- Act on the findings to optimise.

---

## Lesson 9.2 – Optimizing Calculations

### Concept Explanation

Calculations are a common source of performance issues. Slow calculations can dramatically increase query and compilation times. This lesson covers techniques to make your calculations faster.

**Key Optimisation Techniques**:

1. **Use Simple Aggregations** – `SUM([Sales])` is faster than `SUMX(...)` (in Tableau, `SUMX` is not a function, but the concept applies).

2. **Minimize LOD Expressions** – LODs are powerful but can be slow. Use them only when necessary.

3. **Avoid Row‑Level Calculations** – Row‑level calculations (like `[Sales] * [Quantity]`) are slower than aggregate calculations (`SUM([Sales])`).

   - If you need a row‑level calculation, try to do it in the data source (ETL) or in Tableau Prep.

4. **Use `IF` Efficiently** – `CASE` is often faster than `IF` for multiple conditions.

   - `CASE [Category] WHEN "Furniture" THEN 1 WHEN "Office Supplies" THEN 2 END` is faster than a nested `IF`.
5. **Avoid Excessive `IFNULL`** – Use `ZN()` instead of `IFNULL` for numeric fields.

6. **Reduce Calculation Complexity** – Break complex calculations into smaller, simpler calculations.

7. **Use Table Calculations Judiciously** – Table calculations are computed after aggregation; use them when you need to.

**Using the Performance Recorder**:

- After making changes, run Performance Recording again to measure the improvement.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Slow calculations can make a dashboard unusable. Optimising them can dramatically improve performance.


- **Use cases**:

  - A **financial dashboard** has a complex LOD that takes 5 seconds to compute. Simplifying it reduces the time to 1 second.
  
  - A **sales dashboard** uses a row‑level calculation that is moved to the data source, improving performance.

---

### Step‑by‑Step Demonstration

**Optimising an LOD Expression**:

1. Original: `{ FIXED [Customer ID] : SUM([Sales]) }`

2. If you only need the average customer sales, you can use `AVG({ FIXED [Customer ID] : SUM([Sales]) })`.

3. However, if the LOD is used in multiple places, consider creating a data source calculation in Tableau Prep.


**Using `CASE` Instead of `IF`**:

1. Original: `IF [Category] = "Furniture" THEN 1 ELSEIF [Category] = "Office Supplies" THEN 2 ELSE 3 END`

2. Optimised: `CASE [Category] WHEN "Furniture" THEN 1 WHEN "Office Supplies" THEN 2 ELSE 3 END`


**Using `ZN()` Instead of `IFNULL`**:

1. Original: `IFNULL([Sales], 0)`

2. Optimised: `ZN([Sales])`


---

### Practical Examples

- **Example 1**: A complex `IF` statement with 10 conditions is replaced with a `CASE` statement, reducing compilation time.

- **Example 2**: A row‑level calculation `[Profit] = [Sales] - [Cost]` is moved to the data source (ETL), improving dashboard performance.


---

### Hands‑on Exercises

1. Identify a slow calculation in your dashboard.

2. Optimise it using one of the techniques above.

3. Run Performance Recording to measure the improvement.

4. Document the before and after performance.


---

### Mini Quiz

1. Why are LOD expressions sometimes slow?

2. What is the difference between `IF` and `CASE` in terms of performance?

3. What is the advantage of using `ZN()` over `IFNULL()`?

4. When should you use a table calculation instead of a calculated field?

5. How can you measure the impact of your optimisation?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using complex LODs unnecessarily | Use LODs only when needed; consider alternatives |
| Using `IF` for multiple conditions | Use `CASE` for multiple discrete conditions |
| Using row‑level calculations in the view | Move row‑level calculations to the data source or Prep |
| Not testing performance after changes | Always re‑measure performance after optimisation |

---

### Interview Questions

1. **How do you optimise calculations in Tableau?**  

   *Answer*: I use simple aggregations (`SUM`, `AVG`), minimise LOD expressions, use `CASE` instead of `IF` for multiple conditions, use `ZN()` for null handling, and move row‑level calculations to the data source or Tableau Prep. I always measure performance before and after.

2. **What is the difference between a row‑level calculation and an aggregate calculation in terms of performance?**  

   *Answer*: Row‑level calculations are evaluated for each row, which can be slow for large datasets. Aggregate calculations are evaluated after aggregation, which is faster. If possible, I do row‑level calculations in the data source or Tableau Prep.

3. **How do you know if a calculation is causing performance issues?**  

   *Answer*: I use Performance Recording to identify which events have high compilation or query times. I then investigate the calculations involved in those events.

---

### Assignment and Dashboard Projects

**Assignment 9.2** – Optimise calculations in a dashboard:

- Identify a slow calculation.

- Apply optimisation techniques.

- Measure performance before and after.

- Document the changes.


---

### Summary and Revision Notes

- Optimise LODs – use only when needed.

- Use `CASE` for multiple conditions.

- Use `ZN()` instead of `IFNULL()`.

- Move row‑level calculations to the data source.

- Always measure performance.

---

## Lesson 9.3 – Optimizing Data Sources

### Concept Explanation

Data source optimisation focuses on making the connection between Tableau and your data faster. This is often the biggest performance bottleneck.

**Key Optimisation Techniques**:

1. **Use Extracts** – Extracts are faster than live connections for most use cases.

   - Create an extract with only the data you need (filter at extraction time).

   - Use incremental extracts for large, growing datasets.


2. **Reduce Data Volume** – Filter data at the source to reduce the amount transferred.

   - Use data source filters in Tableau.

   - Use custom SQL to filter and aggregate at the source.


3. **Optimise Joins** – Joins can be slow; use them carefully.

   - Avoid unnecessary joins.

   - Use a data warehouse with pre‑joined tables.


4. **Use Data Blending Sparingly** – Blends can be slow; use joins or extracts instead.


5. **Use a Data Warehouse** – Pre‑aggregate data in a data warehouse for faster queries.


6. **Use Custom SQL** – Write efficient SQL queries that filter and aggregate at the source.


---

### Importance and Real‑World Use Cases

- **Why it matters**: The data source is the foundation. If it's slow, everything else will be slow.


- **Use cases**:

  - A **global sales dashboard** uses an extract with a filter for the last 2 years, reducing query time from 30 seconds to 2 seconds.

  - A **financial dashboard** uses a data warehouse with pre‑aggregated data, eliminating the need for complex joins in Tableau.

---

### Step‑by‑Step Demonstration

**Creating an Extract with Filters**:

1. In the Data Source page, click **Extract**.

2. Click **Edit** to set filters (e.g., `Order Date >= 2023-01-01`).

3. Click **Extract**.


**Using Custom SQL**:

1. When connecting to a database, select **Custom SQL**.

2. Write a SQL query that filters and aggregates data:
   ```sql
   SELECT
       Category,
       Region,
       SUM(Sales) AS Sales,
       SUM(Profit) AS Profit
   FROM SalesTable
   WHERE OrderDate >= '2023-01-01'
   GROUP BY Category, Region
   ```
3. Click **OK**.

**Using a Data Source Filter**:

1. In the Data Source page, click **Add** next to **Filters**.

2. Choose a field and set a filter (e.g., `Region = "West"`).

---

### Practical Examples

- **Example 1**: A dashboard with a live connection to a 50‑million‑row table is slow. An extract with a filter for the last 2 years reduces the data to 5 million rows, dramatically improving performance.

- **Example 2**: A dashboard with multiple joins is slow. A data warehouse with a pre‑joined table eliminates the joins, improving performance.


---

### Hands‑on Exercises

1. Create an extract of Sample - Superstore with a filter for the last 2 years.

2. Compare the performance of the extract vs the live connection.

3. If you have a database, write a custom SQL query that aggregates data.

4. Compare the performance of the custom SQL vs loading the full table.


---

### Mini Quiz

1. Why are extracts faster than live connections?

2. How do you create an extract with filters?

3. What is the advantage of using custom SQL?

4. Why should you avoid unnecessary joins?

5. What is the purpose of a data warehouse?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using live connections for large datasets | Use extracts for large datasets |
| Not filtering data at the source | Use data source filters or custom SQL |
| Using too many joins | Use a data warehouse with pre‑joined tables |
| Using data blending for large datasets | Use joins or extracts instead |

---

### Interview Questions

1. **How do you optimise a data source in Tableau?**  

   *Answer*: I use extracts instead of live connections, filter data at the source (using data source filters or custom SQL), minimise joins, use a data warehouse for pre‑aggregated data, and avoid unnecessary data blending.

2. **What is the difference between an extract and a live connection in terms of performance?**  

   *Answer*: Extracts are stored in Tableau's in‑memory engine and are much faster for queries. Live connections query the source database each time, which can be slow if the database is large or the network is slow.

3. **How do you use custom SQL to optimise performance?**  

   *Answer*: I write SQL queries that filter and aggregate data at the source, reducing the amount of data transferred to Tableau. For example, `SELECT Category, SUM(Sales) FROM SalesTable GROUP BY Category`.

---

### Assignment and Dashboard Projects

**Assignment 9.3** – Optimise a data source:

- Create an extract with filters.

- If you have a database, write a custom SQL query.

- Compare performance before and after.

- Document the changes.

---

### Summary and Revision Notes

- Use extracts for faster queries.

- Filter data at the source.

- Minimise joins.

- Use custom SQL for aggregation.

- Use a data warehouse for pre‑aggregated data.

---

## Lesson 9.4 – Row-Level Security

### Concept Explanation

**Row-Level Security (RLS)** restricts data access at the row level based on the user's identity. For example, a sales manager should see only their region's sales data.

**How RLS works in Tableau**:

1. You define **user filters** (also known as **row-level security**) using Tableau's built‑in functions.

2. The filter is applied when a user opens the workbook.

3. Users see only the data they are allowed to see.


**Key functions for RLS**:

- `USERNAME()` – returns the username (e.g., `john.doe`).

- `USERPRINCIPALNAME()` – returns the user's full name (e.g., `john.doe@company.com`).

- `ISFULLMEMBER()` – checks if the user belongs to an Active Directory group.


**Implementation steps**:

1. Create a data source that maps users to allowed values (e.g., a table with `Username` and `Region`).

2. In Tableau, create a **User Filter**.

3. Use `USERPRINCIPALNAME()` to filter the data.

   - Example: `[Region] = LOOKUPVALUE([UserAccess], [Username], USERPRINCIPALNAME())`


**In Tableau Server/Cloud**:

1. Publish the workbook.

2. In the **Data Source** settings, set the **User Filter**.

3. Users are automatically filtered based on their identity.


---

### Importance and Real‑World Use Cases

- **Why it matters**: RLS ensures that sensitive data is only accessible to authorised users. It enables a single dashboard to serve different audiences without creating multiple versions.


- **Use cases**:

  - A **sales dashboard** where each sales rep sees only their own region.

  - An **HR dashboard** where managers see only their team's data.

  - A **financial dashboard** where users see only their department's data.


---

### Step‑by‑Step Demonstration

**Creating a User Mapping Table**:
1. In Tableau Desktop, create a data source with a table:
   | Username | Region |
   |----------|--------|
   | john.doe@company.com | West |
   | jane.smith@company.com | East |

2. Connect to this data source alongside your main data.

**Creating a User Filter**:

1. In the main data source, click **Data** → **New Data Source** → **Create User Filter**.

2. Name the filter (e.g., "Region Filter").

3. Select the field to filter (e.g., `Region`).

4. Use `USERPRINCIPALNAME()` to match the user mapping table.

   - `[Region] = LOOKUPVALUE([UserAccess], [Username], USERPRINCIPALNAME())`

5. Click **OK**.

**Testing the User Filter**:

1. In Tableau Desktop, use **Data** → **Filters** → **User Filter** to test.

2. Enter a username to see the filtered view.

**Publishing**:

1. Publish the workbook to Tableau Server/Cloud.

2. The filter is automatically applied based on the logged‑in user.

---

### Practical Examples

- **Example 1**: A sales dashboard with a user filter on `Region`. John sees only the West region; Jane sees only the East region.

- **Example 2**: An HR dashboard with a user filter on `Department`. Managers see only their department's data.


---

### Hands‑on Exercises

1. Create a user mapping table (Excel or CSV).

2. Connect to it in Tableau.

3. Create a user filter using `USERPRINCIPALNAME()`.

4. Test the filter with different usernames.

5. Publish (if possible) and verify the filter works.


---

### Mini Quiz

1. What is Row-Level Security in Tableau?

2. What Tableau functions are used for RLS?

3. How do you create a user filter?

4. How do you test a user filter?

5. Where is RLS applied in Tableau Server/Cloud?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using `USERNAME()` when `USERPRINCIPALNAME()` is needed – inconsistent results | Use `USERPRINCIPALNAME()` for consistency |
| Not testing the filter – users may see the wrong data | Test with different user identities |
| Creating user filters on fact tables – inefficient | Create user filters on dimension tables |
| Not planning for data source updates – user mapping becomes stale | Ensure the user mapping table is kept up‑to‑date |

---

### Interview Questions

1. **How do you implement Row-Level Security in Tableau?**  

   *Answer*: I create a user mapping table that links usernames to allowed values. Then I create a user filter using `USERPRINCIPALNAME()` to match the user to their allowed data. This filter is applied when the workbook is opened in Tableau Server/Cloud.

2. **What is the difference between `USERNAME()` and `USERPRINCIPALNAME()`?**  

   *Answer*: `USERNAME()` returns the username (e.g., `john.doe`). `USERPRINCIPALNAME()` returns the full name (e.g., `john.doe@company.com`). I prefer `USERPRINCIPALNAME()` for consistency.

3. **Where is RLS enforced in Tableau?**  

   *Answer*: RLS is enforced at the data source level in Tableau Server/Cloud. It is not enforced in Tableau Desktop unless you test it using the User Filter feature.

---

### Assignment and Dashboard Projects

**Assignment 9.4** – Implement Row-Level Security:

- Create a user mapping table.

- Create a user filter.

- Test the filter with different usernames.

- Publish (if possible) and verify.

- Document the implementation.


---

### Summary and Revision Notes

- RLS restricts rows based on user identity.

- Use `USERPRINCIPALNAME()` and a user mapping table.

- Create a user filter in the data source.

- Test using the User Filter feature.

- Publish and verify.

---

## Lesson 9.5 – Data Security Best Practices

### Concept Explanation

Data security in Tableau goes beyond row‑level security. It encompasses protecting data at every stage – from connection to consumption.

**Key Data Security Practices**:

1. **Authentication** – Use single sign‑on (SSO) and multi‑factor authentication (MFA) to secure access.

   - Tableau supports Microsoft Entra ID, SAML, and OAuth.

2. **Authorization** – Use site roles and content permissions to control who can do what.

   - Grant the minimum necessary permissions.

3. **Encryption** – Ensure data is encrypted in transit (SSL/TLS) and at rest.

   - Tableau Server/Cloud encrypts data by default.

4. **Data Extraction** – Be careful with extracts; they contain copies of the data.

   - Use encryption for extracts.

   - Restrict who can create and download extracts.
   
5. **Audit Logging** – Track user activities to detect anomalies.

   - Tableau Server/Cloud provide audit logs.

   - Export logs to a SIEM (Security Information and Event Management) system.

6. **Sensitivity Classification** – Use data tags or labels to classify sensitive data.

7. **Regular Reviews** – Regularly review user permissions and data sources.


   - Remove unnecessary permissions.
   
   - Archive or delete stale data sources.

**Best Practices for Sharing**:

- Share with **groups**, not individuals.

- Use **View‑only** permissions for most users.

- Use **Row‑Level Security** for sensitive data.

- Never share embedded credentials.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Data breaches are costly – financially and reputationally. Implementing security best practices protects your organisation's most valuable asset: data.


- **Use cases**:

  - A **financial services firm** uses encryption and audit logging to meet regulatory requirements.

  - A **healthcare organisation** uses Row‑Level Security to protect patient data.

  - A **government agency** uses SSO and MFA for secure access.


---

### Step‑by‑Step Demonstration

**Enabling Audit Logging**:

1. In Tableau Server/Cloud, go to **Settings** → **Audit**.

2. Enable logging for activities (e.g., login, view, export).

3. Configure the retention period.

4. Export logs to a SIEM if needed.


**Configuring Authentication**:

1. In Tableau Server, go to **Settings** → **Authentication**.

2. Choose the authentication method (e.g., SAML, Microsoft Entra ID).

3. Configure the settings.


**Managing Permissions**:

1. Use **groups** for permissions.

2. Assign the minimum necessary site role.

3. Set content permissions at the project level.

**Encrypting Extracts**:

1. In Tableau Desktop, when creating an extract, select **Encrypt the extract**.

2. This encrypts the data in the extract file.

---

### Practical Examples

- **Example 1**: A company uses Microsoft Entra ID with MFA for all Tableau Server users.

- **Example 2**: A financial firm uses audit logging to track all data exports and views.


---

### Hands‑on Exercises

1. Review the security settings in your Tableau environment.

2. Identify if audit logging is enabled.

3. Identify the authentication method used.

4. Review the permission groups and their access.

5. Document any security gaps.


---

### Mini Quiz

1. What are the key data security practices in Tableau?

2. Why is authentication important?

3. What is the purpose of audit logging?

4. Why should you use groups for permissions?

5. How can you encrypt extracts?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using individual permissions instead of groups – unmanageable | Use groups for permissions |
| Not enabling audit logging – blind to security incidents | Enable audit logging |
| Using weak authentication – vulnerable to attacks | Use SSO and MFA |
| Sharing embedded credentials – security risk | Use server‑managed credentials |
| Not reviewing permissions regularly – stale access | Conduct regular permission reviews |

---

### Interview Questions

1. **What are the key elements of data security in Tableau?**  

   *Answer*: Authentication (SSO, MFA), authorisation (site roles, permissions), encryption (SSL/TLS, encrypt extracts), audit logging, and regular permission reviews.

2. **How do you secure a Tableau Server deployment?**  

   *Answer*: I use SSO with MFA for authentication, assign the minimum necessary site roles, use groups for permissions, enable audit logging, and encrypt extracts.

3. **What is the importance of audit logging in Tableau?**  

   *Answer*: Audit logging tracks user activities, helping to detect security incidents, investigate issues, and comply with regulations.

---

### Assignment and Dashboard Projects

**Assignment 9.5** – Conduct a security audit of a Tableau environment:

- Review authentication methods.

- Review permission groups.

- Review audit logging.

- Identify security gaps.

- Propose improvements.

- Document your findings.


---

### Summary and Revision Notes

- Authentication: use SSO and MFA.

- Authorisation: use groups, minimum permissions.

- Encryption: use SSL/TLS, encrypt extracts.

- Audit logging: enable and review regularly.

- Regular reviews: check permissions and data sources.

---

## Lesson 9.6 – Tableau Performance Tuning

### Concept Explanation

**Performance tuning** is the holistic process of optimising a Tableau deployment – from the data source to the dashboard to the server. This lesson brings together all the optimisation techniques covered in this phase and previous phases.

**The Performance Tuning Framework**:

1. **Diagnose** – Use Performance Recording to identify bottlenecks.

2. **Optimise the Data Source** – Use extracts, filters, and custom SQL.

3. **Optimise the Data Model** – Use a star schema, reduce joins, use data blending sparingly.

4. **Optimise Calculations** – Simplify LODs, use `CASE` over `IF`, move row‑level calculations to the source.

5. **Optimise the Dashboard** – Reduce marks, use context filters, limit the number of worksheets.

6. **Optimise the Server** – For Tableau Server, configure resources, use caching, and monitor performance.


**Quick Wins**:

- Use **extracts** instead of live connections.

- Add **context filters** to reduce data early.

- Limit the number of **marks** in a view.

- Use **simple aggregations** (SUM, AVG) over complex calculations.


**Monitoring**:

- In Tableau Server, use the **Administrator** dashboard to monitor server performance.

- In Tableau Desktop, use **Performance Recording** to monitor dashboard performance.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Performance tuning ensures that your dashboards load quickly and respond smoothly, leading to higher user adoption and satisfaction.


- **Use cases**:

  - A **large enterprise** uses performance tuning to ensure that dashboards for 10,000 users load in under 3 seconds.

  - A **data analyst** uses performance tuning to reduce a dashboard's load time from 15 seconds to 2 seconds.


---

### Step‑by‑Step Demonstration

**Applying the Framework**:

1. **Diagnose**: Run Performance Recording. Identify the slowest element.

2. **Optimise Data Source**: If query time is high, create an extract or optimise the SQL query.

3. **Optimise Calculations**: If compilation time is high, simplify LODs and use `CASE` instead of `IF`.

4. **Optimise Dashboard**: If rendering time is high, reduce marks, use context filters, or limit worksheets.

5. **Test**: Run Performance Recording again to measure the improvement.

**Example Walkthrough**:

1. Performance Recording shows a dashboard takes 10 seconds to load.

2. Query time is 6 seconds – create an extract with a filter for the last 2 years (reduces query time to 1 second).

3. Rendering time is 3 seconds – reduce marks by aggregating data (reduces rendering time to 1 second).

4. Total load time is now 2 seconds.


---

### Practical Examples

- **Example 1**: A dashboard with 10 worksheets is slow. By reducing the number of worksheets to 5 and using context filters, the load time drops from 8 seconds to 3 seconds.


- **Example 2**: A dashboard with complex LODs is slow. By moving some LODs to the data source (using Tableau Prep), the load time drops from 12 seconds to 2 seconds.


---

### Hands‑on Exercises

1. Apply the performance tuning framework to a dashboard:

   - Diagnose with Performance Recording.

   - Optimise the data source (extract, filters).

   - Optimise calculations.

   - Optimise the dashboard.

   - Measure the improvement.

2. Document the changes and their impact.

---

### Mini Quiz

1. What are the steps in the performance tuning framework?

2. Why is diagnosing important before optimising?

3. What is a quick win for performance?

4. How do you measure the impact of your optimisation?

5. Where can you monitor Tableau Server performance?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Optimising without diagnosing – shooting in the dark | Always diagnose first with Performance Recording |
| Focusing on one area only – missing other bottlenecks | Optimise holistically – data source, calculations, dashboard |
| Not measuring improvement – no evidence of success | Measure performance before and after |
| Forgetting about the server – server performance also matters | Monitor server performance and tune accordingly |

---

### Interview Questions

1. **What is your process for performance tuning a Tableau dashboard?**  

   *Answer*: I start by diagnosing with Performance Recording to identify the bottleneck. Then I optimise the data source (extracts, filters), simplify calculations, and reduce dashboard complexity. I measure performance before and after to confirm improvement.

2. **What are the quickest wins for performance tuning?**  

   *Answer*: Using extracts instead of live connections, adding context filters, reducing the number of marks in a view, and simplifying calculations.

3. **How do you monitor Tableau Server performance?**  

   *Answer*: I use the Tableau Server Administrator dashboard to monitor CPU usage, memory, load times, and query performance. I also use Performance Recording for individual dashboards.

---

### Assignment and Dashboard Projects

**Assignment 9.6** – Complete performance tuning of a dashboard:

- Diagnose with Performance Recording.

- Optimise the data source.

- Optimise calculations.

- Optimise the dashboard.

- Measure the improvement.

- Document the changes and their impact.


---

### Summary and Revision Notes

- Performance tuning is a holistic process.

- Framework: Diagnose → Optimise Data Source → Optimise Calculations → Optimise Dashboard → Measure.

- Quick wins: extracts, context filters, reduce marks.

- Always measure before and after.

- Monitor server performance for enterprise deployments.

---

## Final Phase 9 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can use Performance Recording to diagnose performance issues.

-  I can optimise calculations (LODs, `IF` vs `CASE`, null handling).

-  I can optimise data sources (extracts, filters, custom SQL).

-  I can implement Row-Level Security using user filters.

-  I understand data security best practices (authentication, authorisation, encryption, audit logging).

-  I can apply a holistic performance tuning framework.


If you have completed all assignments and feel confident, you have achieved **Expert** level in Tableau performance and security!

---

### Answers to Mini Quizzes

**Lesson 9.1**: 1. A tool that tracks dashboard performance. 2. Help → Settings and Performance → Start Performance Recording. 3. Query, rendering, compilation time. 4. Slow data source. 5. Sort events by duration.

**Lesson 9.2**: 1. They compute at a different granularity. 2. `CASE` is faster for multiple conditions. 3. `ZN()` is faster. 4. When you need post‑aggregation calculations. 5. Use Performance Recording.

**Lesson 9.3**: 1. Stored in Tableau's fast engine. 2. Data Source page → Extract → Edit filters. 3. Filters and aggregates at the source. 4. They slow down queries. 5. To pre‑aggregate data.

**Lesson 9.4**: 1. Restricting rows based on user identity. 2. `USERNAME()`, `USERPRINCIPALNAME()`. 3. Data → New Data Source → Create User Filter. 4. Data → Filters → User Filter. 5. Data source level.

**Lesson 9.5**: 1. Authentication, authorisation, encryption, audit logging, reviews. 2. Prevents unauthorised access. 3. Tracks user activities. 4. Scalable and manageable. 5. In extract settings.

**Lesson 9.6**: 1. Diagnose → Optimise Data Source → Optimise Calculations → Optimise Dashboard → Measure. 2. To target the right fixes. 3. Use extracts, context filters. 4. Use Performance Recording. 5. Tableau Server Administrator dashboard.

---

**Congratulations!** You have completed all nine phases of this comprehensive Tableau curriculum. You are now a **full‑stack Tableau professional** with expertise in:

- Data connection and preparation.

- Calculations and LOD expressions.

- Visualisation and chart selection.

- Dashboard design and interactivity.

- Deployment and governance.

- Performance optimization and security.

You are ready to tackle any Tableau project – from a simple dashboard to a complex enterprise deployment. Remember that Tableau and design trends are constantly evolving, so keep learning through the Tableau community, blogs, and official documentation. The best way to maintain your skills is to keep building dashboards and solving real‑world problems.

Good luck on your Tableau journey!


---







<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>