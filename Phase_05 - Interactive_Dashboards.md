# Phase 5: Interactive Dashboards

Welcome to **Phase 5** – the art of bringing your visualisations to life! In Phases 1 through 4, you learned to connect to data, prepare it, calculate new fields, and create stunning visualisations. Now, you will learn how to combine those visualisations into **interactive dashboards** that tell a complete story.

A great dashboard is more than just a collection of charts. It is a **cohesive, interactive experience** that guides users to insights. It responds to their clicks, filters data dynamically, and presents information in a clear, actionable way.

In this phase, we will cover everything you need to build professional dashboards:

- Building dashboards from multiple worksheets.

- Layout principles and containers.

- Filters, actions, and parameters for interactivity.

- Navigation and dynamic titles.

- Device layouts for mobile and tablet.

By the end of this phase, you will be able to build dashboards that are not only beautiful but also highly functional and user‑friendly.

---

## Lesson 5.1 – Building Dashboards

### Concept Explanation

A **dashboard** in Tableau is a single page that combines multiple worksheets (charts, maps, tables, etc.) into a unified view. It allows users to see key metrics and insights at a glance, with interactivity across all elements.

**Key components of a dashboard**:

- **Worksheets**: Individual charts you've created.

- **Layout**: How the worksheets are arranged on the canvas.

- **Filters**: Controls that filter data across the dashboard.

- **Actions**: Interactions triggered by user clicks (filtering, highlighting, URL navigation).

- **Parameters**: User‑controlled variables that change calculations or views.

- **Navigation**: Buttons or links to move between dashboard pages or stories.


**Dashboard size**:
- **Fixed size**: Best for specific screen resolutions (e.g., 1920×1080).

- **Automatic**: Resizes to fit the user's screen.

- **Custom**: Specify exact dimensions.

**When to use a dashboard**:

- To provide an executive summary.

- To combine multiple views into one coherent story.

- To enable interactive exploration.


---

### Importance and Real‑World Use Cases

- **Why it matters**: A dashboard is the final product that users interact with. A well‑designed dashboard enables faster, better decisions. A poorly designed one frustrates users and is ignored.

- **Use cases**:

  - A **sales dashboard** combines a map, a bar chart, and a table to show performance by region, product, and rep.

  - A **financial dashboard** shows revenue, expenses, profit, and key ratios in one view.
  
  - A **marketing dashboard** combines campaign performance, website traffic, and lead conversion data.

---

### Step‑by‑Step Demonstration

**Creating a Dashboard**:

1. Open Tableau and connect to Sample - Superstore.

2. Create three worksheets:

   - **Sales by Category**: Bar chart.

   - **Sales over Time**: Line chart.

   - **Sales by Region**: Map.

3. Click the **New Dashboard** icon at the bottom (it looks like a grid).

4. In the **Dashboard** pane on the left, you'll see your worksheets listed.

5. Drag `Sales by Category` onto the canvas – it appears as a tile.

6. Drag `Sales over Time` onto the canvas.

7. Drag `Sales by Region` onto the canvas.

8. Arrange them by dragging to reposition.


**Adding a Title**:

1. From the left pane, under **Objects**, drag a **Text** object onto the dashboard.

2. Type your title: "Sales Performance Dashboard".

3. Format it (font size, colour, alignment).


**Sizing the Dashboard**:

1. In the **Size** section of the Dashboard pane, choose **Fixed Size**.

2. Set the width and height (e.g., 1920×1080 for full HD).


---

### Practical Examples

- **Example 1**: A "Sales Performance Dashboard" with a map of sales by region, a bar chart of sales by category, a line chart of sales over time, and a table of top customers.

- **Example 2**: A "Financial Dashboard" with a profit and loss summary, a revenue trend chart, a profit margin gauge, and a list of key ratios.

---

### Hands‑on Exercises

1. Create three worksheets:

   - Sales by Category (bar chart).
   
   - Sales over Time (line chart).
   
   - Profit by Region (map).
   
2. Create a new dashboard.

3. Drag all three worksheets onto the dashboard.

4. Add a title text box.

5. Adjust the size to 1920×1080.

6. Save your dashboard.


---

### Mini Quiz

1. What is a dashboard in Tableau?

2. How do you add a worksheet to a dashboard?

3. What are the different sizing options for dashboards?

4. How do you add a title to a dashboard?

5. What is the difference between a worksheet and a dashboard?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Adding too many worksheets to one dashboard – cluttered | Limit to 4‑6 key worksheets |
| Using default sizes – worksheets may be cut off | Set a fixed size that matches your target display |
| Not adding a title – users don't know what they're looking at | Always add a clear, descriptive title |
| Placing worksheets randomly – no logical flow | Arrange worksheets logically (KPIs top, trends middle, details bottom) |
| Ignoring whitespace – cramped look | Use containers and padding for breathing room |

---

### Interview Questions

1. **What is a dashboard in Tableau and how is it different from a worksheet?**  

   *Answer*: A dashboard is a single page that combines multiple worksheets (charts, maps, tables) into a unified view. A worksheet is a single visualisation. Dashboards are used for summarising and presenting multiple insights together.

2. **How do you create a dashboard in Tableau?**  

   *Answer*: Click the New Dashboard icon, then drag worksheets from the Dashboard pane onto the canvas. You can also add text, images, and filters from the Objects pane.

3. **What are the sizing options for dashboards?**  

   *Answer*: Fixed Size (pixel dimensions), Automatic (resizes to fit the screen), and Custom (you set the dimensions). Fixed size is most common for consistent display.

---

### Assignment and Dashboard Projects

**Assignment 5.1** – Create a dashboard with:

- At least four worksheets.

- A clear title.

- A logical layout (KPIs at the top, charts in the middle, details at the bottom).

- Fixed size of 1920×1080.

- Save the dashboard.


---

### Summary and Revision Notes

- Dashboards combine multiple worksheets into a single page.

- Use the Dashboard pane to add worksheets, text, images, and filters.

- Choose a sizing option that fits your audience.

- Always add a title and organise content logically.

---

## Lesson 5.2 – Dashboard Layouts

### Concept Explanation

**Layout** is how you arrange elements on your dashboard. A good layout guides the user's eye, makes information easy to find, and creates a professional look.

**Layout containers** are the building blocks of dashboard layout:

- **Horizontal Container**: Arranges elements side‑by‑side.

- **Vertical Container**: Arranges elements top‑to‑bottom.

- **Floating**: Elements can be placed anywhere (overlapping allowed).


**Layout principles**:

- **Top‑to‑Bottom**: KPIs at the top, supporting charts in the middle, details at the bottom.

- **Left‑to‑Right**: Most important information on the left (in Western cultures).

- **Whitespace**: Leave breathing room between elements.

- **Grouping**: Put related elements together.


**Using containers**:

- Drag a container onto the canvas.

- Drag worksheets into the container.

- Use **Distribute Evenly** to space elements equally.


---

### Importance and Real‑World Use Cases

- **Why it matters**: A well‑laid‑out dashboard reduces cognitive load – users can quickly find what they need. A poor layout frustrates users and hides insights.

- **Use cases**:

  - An **executive dashboard** uses a horizontal container for KPI cards at the top.

  - A **sales dashboard** uses a vertical container to stack a map, bar chart, and table.

  - A **financial dashboard** uses floating elements for annotations and callouts.


---

### Step‑by‑Step Demonstration

**Using a Horizontal Container**:

1. In the Dashboard pane, drag a **Horizontal Container** onto the canvas.

2. Drag your KPI worksheets (cards) into the container.

3. Resize the container to fit the dashboard width.


**Using a Vertical Container**:

1. Drag a **Vertical Container** onto the canvas.

2. Drag your charts into the container – they stack vertically.


**Tiled vs Floating**:

- **Tiled** (default): Elements snap into a grid and do not overlap.

- **Floating**: Elements can be placed anywhere, allowing overlapping.


**Distributing Elements**:

1. Select multiple elements in a container.

2. Click the **Distribute Evenly** button on the toolbar (or right‑click → Distribute).


---

### Practical Examples

- **Example 1**: A dashboard with a horizontal container for KPIs, a vertical container for the main charts, and a floating container for a callout box.

- **Example 2**: A dashboard with a left sidebar for filters and the main area for charts.


---

### Hands‑on Exercises

1. Create a new dashboard.

2. Add a **Horizontal Container** and place three KPI cards inside it.

3. Add a **Vertical Container** and place three charts inside it.

4. Add a **Floating** text box for an annotation.

5. Distribute the elements evenly.

6. Resize the dashboard to fit a 1920×1080 screen.

---

### Mini Quiz

1. What is the difference between a horizontal and a vertical container?

2. What is the difference between tiled and floating layout?

3. How do you distribute elements evenly in a container?

4. Why is whitespace important in dashboard layout?

5. What is a container used for?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not using containers – elements float chaotically | Always use containers to organise elements |
| Ignoring alignment – elements look messy | Use alignment and distribute tools |
| Overlapping elements unintentionally (floating mode) | Use tiled layout for most elements; use floating sparingly |
| Too much clutter – no breathing room | Use padding and margins inside containers |
| Not considering the user's screen – elements cut off | Test the dashboard on different screen sizes |

---

### Interview Questions

1. **What are containers used for in Tableau dashboards?**  

   *Answer*: Containers are used to organise and lay out elements on a dashboard. Horizontal containers arrange elements side‑by‑side; vertical containers arrange them top‑to‑bottom. They help create a clean, structured layout.

2. **What is the difference between tiled and floating layout?**  

   *Answer*: Tiled layout snaps elements into a grid without overlapping. Floating layout allows elements to be placed anywhere, including overlapping.

3. **How would you create a dashboard with a sidebar for filters?**  

   *Answer*: I would use a horizontal container to split the dashboard into a sidebar (left) and main area (right). The sidebar would contain filter objects, and the main area would contain the charts.

---

### Assignment and Dashboard Projects

**Assignment 5.2** – Redesign your dashboard from Assignment 5.1 using containers:

- Use a horizontal container for KPIs.

- Use a vertical container for charts.

- Add a floating text box for a note.

- Use distribute evenly.

- Save the redesigned dashboard.


---

### Summary and Revision Notes

- Layout containers organise dashboard elements.

- **Horizontal**: side‑by‑side; **Vertical**: top‑to‑bottom.

- **Tiled**: grid layout; **Floating**: free‑form placement.

- Use **Distribute Evenly** for balanced spacing.

- Whitespace improves readability.

---

## Lesson 5.3 – Filters

### Concept Explanation

**Filters** are controls that allow users to limit the data displayed on a dashboard. They are essential for interactivity, enabling users to focus on specific subsets of data.

**Types of filters in Tableau**:

| **Type** | **Description** | **Where to place** |
|----------|-----------------|-------------------|
| **Quick Filters** | Interactive controls on the dashboard (checkboxes, dropdowns, sliders). | Dashboard canvas. |
| **Worksheet Filters** | Filters applied within a specific worksheet. | Data pane (in the worksheet). |
| **Dashboard Filters** | Filters that apply to all worksheets on the dashboard. | Dashboard canvas. |
| **Global Filters** | Filters that apply across multiple dashboards (using actions). | Dashboard actions. |
| **Filter Actions** | Filters triggered by selecting a data point on a chart. | Dashboard Actions. |

**Adding a Quick Filter**:

1. On a dashboard, right‑click a worksheet → **Quick Filter**.

2. Choose the field you want to filter by.

3. The filter appears on the dashboard.

4. Choose the filter style (dropdown, list, slider, etc.).

**Applying a Filter to All Worksheets**:

- When you add a filter, you can specify which worksheets it applies to.
- In the filter drop‑down, select **All** or specific worksheets.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Filters allow users to explore data on their own – drilling into specific regions, time periods, or products without needing to modify the underlying data.

- **Use cases**:

  - A **sales manager** uses a Region filter to view sales for a specific area.

  - A **marketing analyst** uses a Date filter to focus on a specific campaign period.

  - A **product manager** uses a Category filter to analyse a specific product line.


---

### Step‑by‑Step Demonstration

**Adding a Quick Filter**:


1. Open your dashboard from the previous lesson.

2. Right‑click on the `Sales by Category` worksheet → **Quick Filter** → **Category**.

3. A filter appears on the dashboard.

4. Click the drop‑down arrow on the filter → choose **Single Value (Dropdown)**.


**Applying the Filter to All Worksheets**:

1. Click the drop‑down arrow on the filter.

2. Click **Apply to Worksheets**.

3. Select **All worksheets** in the dashboard.

4. Now, changing the Category filter updates all worksheets.


**Changing Filter Style**:

1. Click the filter's drop‑down arrow → **Filter Type**.

2. Choose from: Checkbox, Dropdown, Radio, List, Slider, etc.


---

### Practical Examples

- **Example 1**: A dashboard with a Region filter and a Date filter – users can select a region and date range to see performance for that segment.

- **Example 2**: A dashboard with a Product Category filter that updates all charts on the page.

---

### Hands‑on Exercises

1. Add a Quick Filter for `Category` to your dashboard.

2. Add a Quick Filter for `Region`.

3. Apply both filters to all worksheets.

4. Change the `Category` filter to a dropdown style.

5. Change the `Region` filter to a list style.

6. Test the filters.


---

### Mini Quiz

1. What is a Quick Filter?

2. How do you add a Quick Filter to a dashboard?

3. How do you apply a filter to all worksheets in a dashboard?

4. What are the different filter styles available in Tableau?

5. What is the difference between a dashboard filter and a worksheet filter?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Adding too many filters – overwhelms users | Limit to 3‑5 key filters |
| Not applying filters to all relevant worksheets – inconsistency | Always check which worksheets a filter applies to |
| Using filters that are not intuitive – users don't understand them | Label filters clearly and choose the right style |
| Forgetting to set a default selection | Set a meaningful default (e.g., "All") |
| Not testing filters – they may break the dashboard | Test all filter combinations |

---

### Interview Questions

1. **How do you add a filter to a dashboard in Tableau?**  

   *Answer*: Right‑click a worksheet on the dashboard and select Quick Filter, then choose the field. The filter appears on the dashboard. You can then apply it to other worksheets.

2. **What is the difference between a quick filter and a filter action?**  
   *Answer*: A quick filter is a user‑interactive control (dropdown, checkbox, etc.) that the user manually adjusts. A filter action is triggered when the user clicks on a data point in a chart.

3. **How do you apply a filter to all worksheets on a dashboard?**  
   *Answer*: Click the drop‑down arrow on the filter, select Apply to Worksheets, and choose All.

---

### Assignment and Dashboard Projects

**Assignment 5.3** – Enhance your dashboard with filters:

- Add Quick Filters for `Category`, `Region`, and `Segment`.

- Apply all filters to all worksheets.

- Use different filter styles (dropdown for Category, list for Region, slider for a numeric field).

- Test the filters.

- Save the dashboard.


---

### Summary and Revision Notes

- Quick Filters are user‑interactive controls on the dashboard.

- Apply filters to specific worksheets or all worksheets.

- Filter styles: dropdown, list, checkbox, slider, radio.

- Label filters clearly.

---

## Lesson 5.4 – Actions

### Concept Explanation

**Actions** in Tableau are interactive features that allow users to interact with a dashboard by clicking on data points. Actions create a dynamic experience – filtering, highlighting, or navigating based on user selections.

**Three types of actions**:

| **Type** | **Description** | **Use Case** |
|----------|-----------------|--------------|
| **Filter Action** | Clicking on a data point filters other worksheets. | Click on a region on a map to filter a bar chart. |
| **Highlight Action** | Clicking on a data point highlights related data across worksheets. | Click on a product in a bar chart to highlight it in other charts. |
| **URL Action** | Clicking on a data point opens a URL. | Click on a customer to open their profile page. |

**How to create an action**:

1. On the dashboard, go to **Dashboard** → **Actions**.

2. Click **Add Action** → select the action type.

3. Configure the source sheet (where the user clicks) and the target sheets (what updates).

4. Configure the target field (what data to pass).

5. Click **OK**.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Actions turn a static dashboard into an interactive exploration tool. Users can "drill into" the data by clicking, without needing to understand the underlying structure.

- **Use cases**:

  - A **sales dashboard**: Click on a region on the map → the bar chart and table update to show data for that region.

  - A **customer dashboard**: Click on a customer name → open their profile page (URL action).

  - A **product dashboard**: Click on a product → highlight it across all charts.


---

### Step‑by‑Step Demonstration

**Filter Action**:

1. Create a dashboard with a map (Sales by Country) and a bar chart (Sales by Category).

2. Go to **Dashboard** → **Actions** → **Add Action** → **Filter**.

3. **Source Sheet**: Select the map.

4. **Target Sheets**: Select the bar chart.

5. **Action**: Select **Select** (click) as the trigger.

6. Click **OK**.

7. Now, clicking on a country in the map filters the bar chart to show data for that country.


**Highlight Action**:

1. Add another action: **Add Action** → **Highlight**.

2. Source: bar chart, Target: map.

3. Now, clicking on a category highlights the corresponding countries on the map.


**URL Action**:

1. **Add Action** → **URL**.

2. Source: a table with Customer Names.

3. URL: `https://example.com/customer/` + the Customer ID field.

4. Clicking on a customer opens their profile page.

---

### Practical Examples

- **Example 1**: A sales dashboard where clicking a region on a map filters all charts to show data for that region.

- **Example 2**: A product dashboard where hovering over a product highlights it across all charts.

- **Example 3**: A customer dashboard where clicking a customer name opens their detailed profile in a web application.


---

### Hands‑on Exercises

1. Create a dashboard with a map (Sales by Country) and a bar chart (Sales by Category).

2. Add a **Filter Action** so that clicking a country filters the bar chart.

3. Add a **Highlight Action** so that selecting a category highlights countries on the map.

4. Test the actions.

5. Add a URL action that opens a search for the selected country (e.g., `https://www.google.com/search?q=` + Country).


---

### Mini Quiz

1. What are the three types of actions in Tableau?

2. What is a filter action?

3. What is the difference between a filter action and a highlight action?

4. How do you create an action in Tableau?

5. What is a URL action used for?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Creating actions that are too complex – users get confused | Start with simple filter actions |
| Not testing actions – they may not work as expected | Test all actions thoroughly |
| Forgetting to clear selections – users may get stuck | Add a "Clear Selections" button or use a filter action with a reset |
| Using URL actions without proper authentication | Ensure URL actions are secure |
| Not providing visual feedback – users don't know they can click | Use tooltips to indicate that elements are interactive |

---

### Interview Questions

1. **What are actions in Tableau dashboards?**  

   *Answer*: Actions are interactive features that allow users to interact with a dashboard by clicking on data points. They can filter, highlight, or navigate based on the user's selection.

2. **How would you create a dashboard where clicking on a region in a map filters a bar chart?**  

   *Answer*: I would create a filter action. In the Dashboard menu, select Actions, add a Filter action, set the source sheet to the map, the target sheets to the bar chart, and choose the target field.

3. **What is the difference between a filter action and a highlight action?**  

   *Answer*: A filter action filters the data in the target sheets to show only the selected data. A highlight action highlights the selected data in the target sheets without filtering out the rest.

---

### Assignment and Dashboard Projects

**Assignment 5.4** – Create a dashboard with actions:

- A map and a bar chart.

- Add a filter action: clicking a country filters the bar chart.

- Add a highlight action: clicking a category highlights countries on the map.

- Add a URL action: clicking a country opens a search in a browser.

- Save the dashboard.


---

### Summary and Revision Notes

- Actions add interactivity: Filter, Highlight, URL.

- Filter actions filter target sheets.

- Highlight actions highlight data without filtering.

- URL actions navigate to web pages.

- Create actions via Dashboard → Actions.


---

## Lesson 5.5 – Parameters

### Concept Explanation

**Parameters** are user‑controlled variables that allow users to change values in calculations, filters, or views. They are like "knobs" that users can turn to see different scenarios.

**Common uses of parameters**:

- **What‑if analysis**: Change a discount rate, exchange rate, or growth rate.

- **Measure switching**: Let users choose which measure to display (e.g., Sales, Profit, Quantity).

- **Dynamic ranking**: Let users choose the number of items in a "Top N" list.

- **Date selection**: Let users choose a specific date or date range.

**Creating a parameter**:

1. In the Data pane, click the drop‑down arrow → **Create Parameter**.

2. Choose the data type (integer, float, string, date).

3. Set the allowable values (list, range, or all).

4. Set a default value.

5. Click **OK**.


**Using a parameter**:

- Create a calculated field that references the parameter.

- Add the parameter to the dashboard as a control (dropdown or slider).

---

### Importance and Real‑World Use Cases

- **Why it matters**: Parameters empower users to explore "what‑if" scenarios and customise views without needing to modify the underlying data or calculations.

- **Use cases**:

  - A **financial analyst** uses a parameter to adjust the discount rate and see its impact on net present value.


  - A **sales manager** uses a parameter to choose the number of products in a "Top N" chart.

  - A **marketing analyst** uses a parameter to switch between different metrics (e.g., impressions, clicks, conversions).


---

### Step‑by‑Step Demonstration

**Creating a Parameter**:

1. In the Data pane, click the drop‑down arrow → **Create Parameter**.

2. Name it: `Discount Rate`.

3. Data type: **Float**.

4. Allowable values: **Range** (min: 0, max: 0.2, step: 0.01).

5. Default value: 0.05.

6. Click **OK**.


**Using the Parameter in a Calculation**:

1. Create a calculated field: `Discounted Sales = SUM([Sales]) * (1 - [Discount Rate])`.

2. Drag `Discounted Sales` to the view.


**Adding the Parameter to the Dashboard**:

1. In the Dashboard pane, under **Objects**, drag **Parameter** onto the dashboard.

2. Select `Discount Rate`.

3. Users can now adjust the slider to see discounted sales.


**Measure Switching Parameter**:

1. Create a parameter: `Measure Selector` (String).

2. Allowable values: List → "Sales", "Profit", "Quantity".

3. Default: "Sales".

4. Create a calculated field:

   ```
   CASE [Measure Selector]
       WHEN "Sales" THEN SUM([Sales])
       WHEN "Profit" THEN SUM([Profit])
       WHEN "Quantity" THEN SUM([Quantity])
   END
   ```
5. Drag this calculated field to the view.


---

### Practical Examples

- **Example 1**: A financial dashboard with a parameter for `Discount Rate` – users can see how changes in discount rate affect revenue.

- **Example 2**: A sales dashboard with a parameter for `Top N` – users can choose to see the top 5, 10, or 20 products.

- **Example 3**: A marketing dashboard with a parameter for `Metric` – users can switch between impressions, clicks, and conversions.


---

### Hands‑on Exercises

1. Create a parameter called `Top N` (integer, range 1 to 20, default 10).

2. Create a calculated field `Top N Filter` that uses the parameter to filter products.

3. Add the parameter to the dashboard.

4. Create a parameter called `Metric` (string, list: "Sales", "Profit", "Quantity").

5. Create a calculated field `Dynamic Measure` using a `CASE` statement.

6. Add the metric parameter to the dashboard.


---

### Mini Quiz

1. What is a parameter in Tableau?

2. How do you create a parameter?

3. How do you use a parameter in a calculation?

4. How do you add a parameter to a dashboard?

5. What is the difference between a parameter and a filter?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Creating parameters without clear labels – users don't know what they control | Label parameters clearly (e.g., "Discount Rate (%)") |
| Using parameters where a filter would be simpler | Use filters for categorical selection; parameters for numeric/calculation changes |
| Not testing the parameter with sample data | Test the parameter to ensure it works correctly |
| Forgetting to add the parameter to the dashboard – users can't use it | Always add the parameter as a control on the dashboard |

---

### Interview Questions

1. **What is a parameter in Tableau and how is it different from a filter?**  

   *Answer*: A parameter is a user‑controlled variable that can be used in calculations, filters, or views. A filter directly limits the data displayed. Parameters are used for scenarios like what‑if analysis and dynamic calculations, while filters are for data selection.

2. **How would you create a parameter that allows users to switch between Sales, Profit, and Quantity?**  

   *Answer*: Create a string parameter with allowable values: Sales, Profit, Quantity. Then create a calculated field with a `CASE` statement that returns the corresponding aggregation based on the parameter selection.

3. **How do you add a parameter to a dashboard?**  

   *Answer*: In the Dashboard pane, under Objects, drag the Parameter object onto the dashboard and select the parameter. It will appear as a control (dropdown or slider).

---

### Assignment and Dashboard Projects

**Assignment 5.5** – Create a dashboard with parameters:

- A `Top N` parameter to show the top N products in a bar chart.

- A `Metric` parameter to switch between Sales, Profit, and Quantity.

- Add both parameters to the dashboard.

- Test the dashboard.

---

### Summary and Revision Notes

- Parameters are user‑controlled variables.

- Used for what‑if analysis, measure switching, and dynamic rankings.

- Created in the Data pane.

- Added to the dashboard as controls.

---

## Lesson 5.6 – Navigation Buttons

### Concept Explanation

**Navigation buttons** allow users to move between different pages in a dashboard or story. They are essential for multi‑page dashboards, providing a clear and intuitive way to navigate.

**Use cases for navigation**:

- Switching between overview and detail pages.

- Moving between different sections of a large dashboard.

- Guiding users through a story.


**How to create navigation buttons**:

1. In the Dashboard pane, under **Objects**, drag a **Button** or **Text** object onto the canvas.

2. Format it as a button (colour, shape, text).

3. In the Dashboard pane, select **Actions** → **Add Action** → **Navigate to Sheet**.

4. Set the source sheet (the current dashboard) and the target sheet (the destination).

5. Click **OK**.

**Alternative**: You can use an image as a button or create a navigation bar with multiple buttons.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Navigation buttons make dashboards user‑friendly, especially when there are multiple pages. They reduce confusion and guide users to the right information.

- **Use cases**:

  - A **sales dashboard** has an Overview page and a Details page. Buttons allow users to switch between them.

  - A **financial dashboard** has pages for P&L, Balance Sheet, and Cash Flow. Buttons provide easy access.

  - A **story** has multiple story points. Buttons allow users to move forward and backward.


---

### Step‑by‑Step Demonstration

**Creating a Navigation Button**:


1. Create a second dashboard (or worksheet) that you want to navigate to.

2. On your main dashboard, drag a **Text** object from the Objects pane.

3. Type "Go to Details" and format it as a button (e.g., blue background, white text).

4. In the Dashboard pane, under **Actions**, click **Add Action** → **Navigate to Sheet**.

5. Source: Select the current dashboard.

6. Target: Select the destination dashboard.

7. Click **OK**.


**Creating a Navigation Bar**:

1. Drag a **Horizontal Container** to the top of the dashboard.

2. Add multiple buttons or text objects inside it.

3. Create actions for each button to navigate to different sheets.


---

### Practical Examples

- **Example 1**: A dashboard with "Overview" and "Details" pages. Buttons at the top allow users to switch between them.

- **Example 2**: A story with "Introduction", "Analysis", and "Conclusion" points. Navigation buttons guide the user through the narrative.

---

### Hands‑on Exercises

1. Create two dashboards: "Overview" and "Details".

2. On the Overview dashboard, add a "Go to Details" button.

3. Create an action so the button navigates to the Details dashboard.

4. On the Details dashboard, add a "Back to Overview" button.

5. Test the navigation.


---

### Mini Quiz

1. What is a navigation button used for in Tableau?

2. How do you create a navigation button?

3. What is the difference between a navigation button and a URL action?

4. How do you create a navigation bar?

5. Can navigation buttons be used to navigate to worksheets?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not labelling buttons clearly – users don't know where they go | Use clear labels like "Go to Details" or "Back to Overview" |
| Creating too many buttons – cluttered navigation bar | Limit to 3‑5 main navigation options |
| Not testing navigation – links may be broken | Test all navigation actions |
| Using default formatting – buttons look plain | Format buttons to look like buttons (colour, border, hover effect) |

---

### Interview Questions

1. **How do you create navigation between dashboards in Tableau?**  

   *Answer*: I use a text or image object as a button, then create a Navigate to Sheet action. The action is triggered when the user clicks on the button.

2. **What is the difference between a navigation action and a URL action?**  

   *Answer*: A navigation action navigates to another sheet or dashboard within the Tableau workbook. A URL action navigates to an external web page.

3. **How would you create a navigation bar on a dashboard?**  

   *Answer*: I would use a horizontal container at the top of the dashboard, place text objects (or image objects) inside it, and create navigation actions for each one.

---

### Assignment and Dashboard Projects

**Assignment 5.6** – Create a multi‑page dashboard with navigation:

- Create two dashboards: "Overview" and "Details".

- Add navigation buttons on both pages to switch between them.

- Format the buttons with consistent styling.

- Save the dashboard.

---

### Summary and Revision Notes

- Navigation buttons guide users between pages.

- Created via Navigate to Sheet actions.

- Use text or image objects as buttons.

- Test all navigation actions.


---

## Lesson 5.7 – Tooltips

### Concept Explanation

**Tooltips** are pop‑up boxes that appear when a user hovers over a data point in a worksheet. They provide additional context without cluttering the dashboard.

**Default tooltips**:
- Tableau automatically generates tooltips showing the data point's values.

**Custom tooltips**:

- You can customise tooltips to show additional fields, images, or even charts.

- You can format the text and add visual elements.


**Adding to tooltips**:

1. In a worksheet, click the **Tooltip** button on the Marks Card.

2. In the tooltip editor, type your custom text and use the Insert dropdown to add fields.

3. You can also add a **mini‑chart** (a small chart) to the tooltip.


**Tooltip on a dashboard**:
- Tooltips work the same way on dashboards as they do on worksheets.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Tooltips provide "just‑in‑time" information, giving users context without taking up space on the dashboard.


- **Use cases**:

  - A **sales dashboard**: Hovering over a bar shows the exact sales value, growth rate, and number of transactions.

  - A **map**: Hovering over a region shows the population, sales, and profit.

  - A **scatter plot**: Hovering over a point shows the product name, sales, profit, and category.


---

### Step‑by‑Step Demonstration

**Customising a Tooltip**:

1. In a worksheet, click the **Tooltip** button on the Marks Card.

2. In the tooltip editor, you'll see the default text.

3. Delete or modify the text.

4. Click **Insert** to add fields (e.g., `Sales`, `Profit`, `Category`).

5. You can also add formatting (bold, italic, colour).

6. Click **OK**.


**Adding a Mini‑Chart to a Tooltip**:

1. In the tooltip editor, click **Add** → **Insert Sheet**.

2. Select a worksheet (e.g., a small line chart of sales over time for that product).

3. The mini‑chart appears in the tooltip.


---

### Practical Examples

- **Example 1**: A bar chart showing sales by product. The tooltip shows the product name, sales, profit, and a mini‑chart of sales over time for that product.

- **Example 2**: A map showing sales by country. The tooltip shows the country name, sales, profit, and a list of top products sold in that country.


---

### Hands‑on Exercises

1. Create a bar chart of Sales by Category.

2. Click the Tooltip button on the Marks Card.

3. Customise the tooltip to show Category, Sales, Profit, and Quantity.

4. Add a mini‑chart of sales over time for the selected category.

5. Test the tooltip by hovering over a bar.

---

### Mini Quiz

1. What is a tooltip in Tableau?

2. How do you customise a tooltip?

3. How do you add a mini‑chart to a tooltip?

4. Can tooltips be used on dashboards?

5. What is the difference between a tooltip and a comment?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Including too much information – tooltips become cluttered | Keep tooltips concise (3‑5 pieces of information) |
| Not using formatting – tooltips look plain | Use bold, colour, and spacing to make tooltips readable |
| Forgetting to test tooltips – they may be empty | Test tooltips on all worksheets |
| Adding complex mini‑charts – they slow down performance | Keep mini‑charts simple |

---

### Interview Questions

1. **What is a tooltip in Tableau and how can it be customised?**  

   *Answer*: A tooltip is a pop‑up box that appears when you hover over a data point. It can be customised by clicking the Tooltip button on the Marks Card and editing the text, adding fields, or inserting mini‑charts.

2. **How would you add a mini‑chart to a tooltip?**  

   *Answer*: In the tooltip editor, click Add → Insert Sheet, then select a worksheet that contains the mini‑chart. The chart will appear in the tooltip.

3. **Why are tooltips useful in dashboards?**  

   *Answer*: Tooltips provide additional context without cluttering the dashboard. They allow users to see detailed information on‑demand.

---

### Assignment and Dashboard Projects

**Assignment 5.7** – Enhance your dashboard with custom tooltips:

- Customise the tooltips on all worksheets.

- Add at least two fields to each tooltip.

- Add a mini‑chart to at least one tooltip.

- Test the tooltips.


---

### Summary and Revision Notes

- Tooltips provide on‑hover context.

- Customise via the Tooltip button on the Marks Card.

- Insert fields for additional data.

- Insert mini‑charts for visual context.

---

## Lesson 5.8 – Dynamic Titles

### Concept Explanation

**Dynamic titles** are titles that change based on the data, filters, or parameters. They make your dashboards more informative and personalised.

**Why use dynamic titles**:

- They tell the user what they are looking at (e.g., "Sales for 2025").

- They adapt to filters (e.g., "Sales for [Region]").

- They reduce the need for static text.


**How to create a dynamic title**:

1. Use a **Text** object on the dashboard.

2. Insert dynamic content using the **Insert** button in the text editor.

3. You can insert fields, parameters, or sheet names.


**Alternative**:

- You can also use a worksheet title that references parameters or fields.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Dynamic titles provide context and reduce confusion. They adapt to user selections, making the dashboard feel responsive and personalised.

- **Use cases**:

  - A **sales dashboard**: Title shows "Sales for [Selected Region]".

  - A **financial dashboard**: Title shows "Profitability Analysis: [Selected Year]".

  - A **marketing dashboard**: Title shows "Campaign Performance: [Selected Campaign]".


---

### Step‑by‑Step Demonstration

**Creating a Dynamic Title**:

1. On your dashboard, drag a **Text** object from the Objects pane.

2. Type your title, e.g., "Sales for ".

3. Click the **Insert** button in the text editor.

4. Select a field, e.g., `Region`.

5. The title now reads "Sales for [Region]" and will update when the Region filter changes.


**Using a Parameter in a Title**:

1. Create a parameter `Metric Selector` (as in Lesson 5.5).

2. In the title text, type "Analysis of ".

3. Insert the `Metric Selector` parameter.

4. The title now shows "Analysis of Sales" or "Analysis of Profit" based on the parameter.


**Using a Sheet Name in a Title**:

- You can also insert the sheet name to show which view is active.

---

### Practical Examples

- **Example 1**: A title that reads "Sales Performance: [Region]" – if the user selects "West", the title becomes "Sales Performance: West".

- **Example 2**: A title that reads "Financial Summary – [Year]" – if the user selects "2025", it becomes "Financial Summary – 2025".


---

### Hands‑on Exercises

1. On your dashboard, add a Text object at the top.

2. Type "Sales Dashboard – ".

3. Insert the `Region` field using the Insert button.

4. Add another text object below it: "Analysis by [Metric]".

5. Insert your `Metric Selector` parameter.

6. Test the dynamic titles by changing filters and parameters.

---

### Mini Quiz

1. What is a dynamic title?

2. How do you create a dynamic title in Tableau?

3. How can you use a parameter in a title?

4. How can you use a field in a title?

5. Why are dynamic titles useful?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Forgetting to include a default – title may be blank | Always include a meaningful default |
| Making titles too long – they get cut off | Keep titles concise (1‑2 lines) |
| Not testing dynamic titles – they may not update correctly | Test with different filter selections |
| Using dynamic titles in every text object – overkill | Use dynamic titles strategically (e.g., main heading only) |

---

### Interview Questions

1. **What is a dynamic title in Tableau?**  

   *Answer*: A dynamic title is a title that changes based on data, filters, or parameters. It provides context by reflecting the current selection.

2. **How do you create a dynamic title using a field?**  

   *Answer*: Add a Text object, type your title, and use the Insert button to add a field. For example, "Sales for " + [Region].

3. **How do you create a dynamic title using a parameter?**  

   *Answer*: In the Text object, insert the parameter using the Insert button. For example, "Analysis of " + [Metric Selector].

---

### Assignment and Dashboard Projects

**Assignment 5.8** – Add dynamic titles to your dashboard:

- Add a main title that includes the selected Region.

- Add a subtitle that includes the selected Metric.

- Add a title that includes the selected Year (if you have a Year filter).

- Test the dynamic titles.

---

### Summary and Revision Notes

- Dynamic titles change based on filters or parameters.

- Created using Text objects with inserted fields or parameters.

- Provide context and personalisation.


---

## Lesson 5.9 – Device Layouts

### Concept Explanation

**Device layouts** allow you to create different views of your dashboard for different devices: desktop, tablet, and phone. This ensures your dashboard looks great on any screen.

**Why device layouts matter**:

- Users access dashboards on various devices.

- A dashboard designed for a large screen may be unusable on a phone.

- Device layouts let you optimise for each device without creating separate dashboards.


**Device types**:

- **Desktop**: Full‑sized view.

- **Tablet**: Optimised for tablets (e.g., iPad).

- **Phone**: Optimised for smartphones.


**Creating a device layout**:

1. On your dashboard, click the **Device Preview** button (the mobile icon) in the toolbar.

2. Choose a device type.

3. The dashboard shows how it will look on that device.

4. Click **Edit** to customise the layout for that device.

5. You can rearrange, resize, and hide elements.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Many users access dashboards on mobile devices. A dashboard that is unreadable on a phone will be ignored.

- **Use cases**:

  - A **sales team** accesses the dashboard on tablets during client meetings.

  - A **CEO** checks the executive dashboard on their phone.

  - A **field service team** uses a phone to view customer data.


---

### Step‑by‑Step Demonstration

**Creating a Phone Layout**:

1. Open your dashboard.

2. Click the **Device Preview** button (mobile icon).

3. Select **Phone**.

4. The dashboard preview shows the current layout shrunk to phone size.

5. Click **Edit**.

6. Remove or hide elements that are not essential for the phone view.

7. Rearrange the remaining elements vertically (stack them).

8. Resize elements to fit the phone screen.

9. Save the phone layout.


**Creating a Tablet Layout**:

1. Repeat the steps for **Tablet**.

2. Tablet layouts can have more elements than phone layouts.

3. Arrange elements in a 2‑column grid.

---

### Practical Examples

- **Example 1**: A desktop dashboard has six charts. The phone version shows only three key charts, stacked vertically.

- **Example 2**: A tablet dashboard shows four charts in a 2×2 grid, while the desktop version shows six charts in a 3×2 grid.

---

### Hands‑on Exercises

1. Open your dashboard.

2. Click the Device Preview button.

3. Create a **Phone** layout:

   - Show only the KPIs and the bar chart.

   - Stack them vertically.

   - Hide the map and table.

4. Create a **Tablet** layout:

   - Show KPIs in a horizontal row.

   - Show two charts side‑by‑side.

   - Hide the table or move it to the bottom.

5. Save both layouts.

6. Preview the dashboard on different screen sizes.


---

### Mini Quiz

1. What are device layouts in Tableau?

2. What device types are supported?

3. How do you create a device layout?

4. Why are device layouts important?

5. Can you hide elements in a device layout?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not creating device layouts – phone users see a tiny version of the desktop layout | Always create phone and tablet layouts |
| Adding too many elements to the phone layout – cluttered | Show only the most important elements on phone |
| Not testing on actual devices – layout may not render correctly | Test on real devices or use browser developer tools |
| Forgetting to update device layouts when the dashboard changes | Revisit device layouts when the desktop layout changes |

---

### Interview Questions

1. **What are device layouts in Tableau and why are they important?**  

   *Answer*: Device layouts allow you to create optimised views of your dashboard for desktop, tablet, and phone. They are important because users access dashboards on various devices, and a mobile‑friendly design improves usability.

2. **How do you create a phone layout for a dashboard?**  

   *Answer*: Click the Device Preview button, select Phone, then click Edit. Customise the layout by rearranging, resizing, and hiding elements to fit the phone screen.

3. **Can you have different elements on the phone layout vs the desktop layout?**  

   *Answer*: Yes, you can hide elements on the phone layout by clicking the "Hide" button in the Layout pane. This allows you to show only the most important information.

---

### Assignment and Dashboard Projects

**Assignment 5.9** – Create device layouts for your dashboard:

- Create a **Phone** layout with the most important KPIs and one chart.

- Create a **Tablet** layout with KPIs and two charts.

- Hide non‑essential elements on each layout.

- Save the layouts.

- Preview the dashboard on different device sizes.


---

### Summary and Revision Notes

- Device layouts optimise dashboards for different screens.

- Types: Desktop, Tablet, Phone.

- Use Device Preview to create and edit layouts.

- Hide non‑essential elements for smaller screens.

---

## Final Phase 5 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can build a dashboard by combining worksheets.

-  I can use horizontal and vertical containers for layout.

-  I can add quick filters to a dashboard.

-  I can create filter, highlight, and URL actions.

-  I can create and use parameters in calculations and dashboards.

-  I can add navigation buttons between dashboards.

-  I can customise tooltips.

-  I can create dynamic titles.

-  I can create device layouts for phone and tablet.

---

### Answers to Mini Quizzes

**Lesson 5.1**: 1. A single page combining multiple worksheets. 2. Drag from the Dashboard pane. 3. Fixed, Automatic, Custom. 4. Drag a Text object. 5. Worksheet = single view; Dashboard = collection of worksheets.

**Lesson 5.2**: 1. Horizontal = side‑by‑side; Vertical = top‑to‑bottom. 2. Tiled = grid; Floating = free‑form. 3. Select elements → Distribute Evenly. 4. Improves readability. 5. To organise elements.

**Lesson 5.3**: 1. A user‑interactive filter on the dashboard. 2. Right‑click worksheet → Quick Filter. 3. Apply to Worksheets → All. 4. Dropdown, list, checkbox, slider, radio. 5. Dashboard filter applies to all sheets; worksheet filter applies to one.

**Lesson 5.4**: 1. Filter, Highlight, URL. 2. Click a data point to filter other sheets. 3. Filter removes data; Highlight highlights data without removing. 4. Dashboard → Actions → Add Action. 5. To navigate to a URL.

**Lesson 5.5**: 1. A user‑controlled variable. 2. Data pane → Create Parameter. 3. In a calculated field, reference the parameter. 4. Drag Parameter object from Objects. 5. Parameter is a variable; filter limits data.

**Lesson 5.6**: 1. To navigate between sheets/dashboards. 2. Add a text/button object, then create a Navigate to Sheet action. 3. Navigation = internal; URL = external. 4. Use a horizontal container with multiple buttons. 5. Yes.

**Lesson 5.7**: 1. A pop‑up box on hover. 2. Click Tooltip button on Marks Card. 3. Click Add → Insert Sheet. 4. Yes. 5. Tooltip is interactive; comment is static.

**Lesson 5.8**: 1. A title that changes based on data/filters/parameters. 2. Use a Text object and insert fields/parameters. 3. Insert the parameter using the Insert button. 4. Insert the field using the Insert button. 5. Provides context and personalisation.

**Lesson 5.9**: 1. Optimised views for different devices. 2. Desktop, Tablet, Phone. 3. Device Preview → Select device → Edit. 4. For mobile accessibility. 5. Yes.

---

**Congratulations!** You have completed Phase 5. You now have the skills to build professional, interactive dashboards that engage users and drive decisions. Keep practising!


---








<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>