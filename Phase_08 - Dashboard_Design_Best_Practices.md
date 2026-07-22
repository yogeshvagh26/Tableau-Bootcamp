# Phase 8: Dashboard Design Best Practices

Welcome to **Phase 8** – the art and science of designing dashboards that people actually use and love! Throughout the previous seven phases, you have mastered the technical skills of Tableau. Now, we focus on **design** – the principles that transform a collection of charts into a clear, compelling, and actionable dashboard.

A technically perfect dashboard that is confusing, cluttered, or visually unappealing will be ignored. Design is not about making things "pretty"; it's about **clarity, efficiency, and trust**. A well‑designed dashboard reduces the time it takes for a user to find an answer, minimises errors, and builds confidence in the data.

In this phase, we will cover:

- Choosing the right chart for your data and message.

- Core dashboard design principles.

- Color theory and effective use of colour.

- Typography for readability.

- User Experience (UX) best practices.

- Storytelling with data.

- Accessibility considerations.

- Mobile dashboard design.


These principles apply to **all** BI tools – Tableau, Power BI, and beyond. Master them, and you'll be a designer, not just a developer.

---

## Lesson 8.1 – Choosing the Right Chart

### Concept Explanation

Before you build any dashboard, you must answer: **What is the message I want to communicate?** The chart type you choose should make that message instantly clear.

**Chart Selection Framework**:

| **Goal** | **Best Chart(s)** |
|----------|-------------------|
| Compare categories | Bar/Column chart |
| Show trends over time | Line chart |
| Show part-to-whole (few parts) | Pie/Donut chart (use sparingly) |
| Show part-to-whole (many parts) | Stacked bar, Tree map |
| Show distribution | Histogram, Box plot |
| Show relationship (two variables) | Scatter plot |
| Show relationship (three variables) | Bubble chart |
| Show geographic data | Map (symbol, filled) |
| Display a single KPI | KPI card, Gauge, Scorecard |
| Show detailed data | Table, Highlight table |
| Show progression through stages | Funnel chart |
| Show cumulative effects | Waterfall chart |

**Ask yourself**:

- **How many variables?** (1, 2, 3, more?)

- **What is the data type?** (categorical, numeric, date, geographic)

- **What comparison is needed?** (ranking, trend, composition, correlation, distribution)


**Rule of thumb**: If you're unsure, start with a bar chart. It is the most universally understood chart type.

---

### Importance and Real‑World Use Cases

- **Why it matters**: The wrong chart type can hide or distort your message. A line chart with categorical data (e.g., product names) implies a continuity that doesn't exist. A pie chart with 20 slices is unreadable.

- **Use cases**:

  - A **sales manager** wants to compare sales across regions – use a **bar chart**.

  - A **financial analyst** wants to show revenue trends over 5 years – use a **line chart**.

  - A **marketing analyst** wants to show the composition of traffic by channel – use a **pie chart** (if ≤5 channels) or a **stacked bar**.


---

### Step‑by‑Step Demonstration

1. Open Tableau and connect to Sample - Superstore.

2. Suppose you want to **compare sales by category**. This is a categorical comparison. Choose a **Bar chart**.

   - Drag `Category` to Columns, `Sales` to Rows.

3. Suppose you want to **show sales trends over time**. Choose a **Line chart**.

   - Drag `Order Date` to Columns (continuous), `Sales` to Rows.

4. Suppose you want to **show the relationship between sales and profit**. Choose a **Scatter plot**.

   - Drag `Sales` to Columns, `Profit` to Rows.

5. Now, experiment by changing the chart type for each – notice how the message changes.

---

### Practical Examples

- **Example 1**: A dashboard showing **sales by region** – a bar chart is clear and easy to compare.

- **Example 2**: A dashboard showing **monthly revenue** – a line chart shows the trend over time.

- **Example 3**: A dashboard showing **market share by product** – a pie chart with 4 products is acceptable, but a bar chart is often better.


---

### Hands‑on Exercises

1. For each of the following scenarios, choose the best chart type:

   - Compare sales across 10 products.

   - Show the trend of website traffic over the last 12 months.

   - Show the breakdown of expenses by department.

   - Show the relationship between advertising spend and revenue.

2. Build each chart in Tableau.

3. Experiment with changing the chart type – note how the message changes.


---

### Mini Quiz

1. What chart type is best for comparing categories?

2. What chart type is best for showing trends over time?

3. When would you use a pie chart?

4. What is the main limitation of a pie chart?

5. What chart type shows the relationship between two numeric variables?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using a line chart for categorical data | Use bar charts for categories |
| Using a pie chart with >5 categories | Use a bar chart or tree map |
| Using 3D charts – they distort perception | Keep charts 2D |
| Using a scatter plot with too many points – cluttered | Use transparency or reduce the sample |
| Not sorting bar charts – random order | Sort bars by value (descending) |

---

### Interview Questions

1. **How do you decide which chart type to use for a given dataset?**  

   *Answer*: I first identify the business question and the type of data (categorical, numeric, time). Then I match the goal – comparison (bar chart), trend (line chart), composition (pie or stacked bar), relationship (scatter plot), or geographic (map).

2. **Why would you choose a bar chart over a pie chart?**  

   *Answer*: Bar charts are better for comparing values across categories because the human eye can more easily compare bar lengths than pie slice angles. Pie charts are acceptable for showing part-to-whole with very few categories.

3. **What is the best way to show a time series?**  

   *Answer*: A line chart with a continuous date axis is the standard for time series. It clearly shows trends, seasonality, and patterns.

---

### Assignment and Dashboard Projects

**Assignment 8.1** – Create a "Chart Selection Guide" for your team:

- List common business questions.

- Recommend the best chart type for each.

- Include a brief justification.

- Save it as a reference document.


---

### Summary and Revision Notes

- Match the chart type to the message: comparison, trend, composition, distribution, relationship, geography.

- Bar charts are the most versatile.

- Use pie charts sparingly (≤5 categories).

- Always sort bar charts.

- Test different chart types to see which best communicates your message.

---

## Lesson 8.2 – Dashboard Design Principles

### Concept Explanation

Great dashboard design is guided by timeless principles. These principles apply whether you're using Tableau, Power BI, or any other BI tool.

**The Core Principles**:

1. **Visual Hierarchy** – Guide the user's eye from the most important information to the least.

   - Place KPIs at the top.

   - Use size, position, and colour to indicate importance.

2. **Simplicity** – Less is more. Remove anything that doesn't serve a purpose.

   - "Charts should not be overcrowded with unnecessary ink" – Edward Tufte.

3. **Consistency** – Use consistent fonts, colours, and styles across all charts.

   - A consistent design builds trust and reduces cognitive load.

4. **Proximity** – Group related information together.

   - Put related charts next to each other.

5. **Alignment** – Align elements to create a clean, organised look.

   - Use grids and alignment tools.

6. **Whitespace** – Give elements breathing room.

   - Whitespace improves readability and reduces clutter.

7. **Context** – Always provide context.

   - Add titles, subtitles, and annotations so users know what they're looking at.

**The 5-Second Rule**: A user should understand the overall message of a dashboard within 5 seconds. If they can't, the design needs improvement.

---

### Importance and Real‑World Use Cases

- **Why it matters**: A well‑designed dashboard is used; a poorly designed one is ignored. Good design reduces the time to insight, increases trust, and drives better decisions.

- **Use cases**:

  - A **sales dashboard** uses visual hierarchy: KPIs at the top, a trend chart in the middle, and a detailed table at the bottom.

  - A **financial dashboard** uses consistent colour coding: blue for revenue, green for profit, red for losses.

  - A **marketing dashboard** groups related campaigns together using proximity.


---

### Step‑by‑Step Demonstration

**Applying Visual Hierarchy**:

1. Open a dashboard with multiple worksheets.

2. Resize the most important KPI cards to be larger.

3. Place them at the top of the dashboard.

4. Place supporting charts in the middle.

5. Place detailed tables at the bottom.


**Using Whitespace**:

1. Add padding between elements (using containers or margins).

2. Don't cram elements together – leave space around each element.


**Ensuring Consistency**:

1. Set a theme with consistent colours and fonts.

2. Use the same font size for all titles.

3. Use the same colour palette across all charts.

---

### Practical Examples

- **Example 1**: A dashboard with 4 KPIs at the top in a horizontal row, a line chart in the middle, and a table at the bottom – clear hierarchy.

- **Example 2**: A dashboard with consistent blue colour scheme and same font for all titles – professional and trustworthy.

---

### Hands‑on Exercises

1. Open any dashboard you have built.

2. Apply visual hierarchy: move KPIs to the top, resize them.

3. Add whitespace: increase padding between elements.

4. Ensure consistency: check fonts, colours, and styles.

5. Apply the 5‑second rule: ask a colleague to look at your dashboard for 5 seconds and describe what they see.


---

### Mini Quiz

1. What is visual hierarchy in dashboard design?

2. Why is consistency important?

3. What is the purpose of whitespace?

4. What is the 5‑second rule?

5. How do you group related information on a dashboard?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Putting everything on one page – information overload | Use multiple pages with clear navigation |
| Inconsistent formatting – looks unprofessional | Use a theme and stick to it |
| No visual hierarchy – users don't know where to look | Place KPIs prominently; use size to indicate importance |
| No whitespace – cramped and hard to read | Add padding between elements |

---

### Interview Questions

1. **What are the key principles of dashboard design?**  

   *Answer*: Visual hierarchy, simplicity, consistency, proximity, alignment, whitespace, and context.

2. **How do you apply visual hierarchy to a dashboard?**  

   *Answer*: I place the most important information (KPIs) at the top and make them larger. I use position and colour to guide the user's eye from the most important to the least important elements.

3. **What is the 5‑second rule and why is it important?**  

   *Answer*: A user should understand the overall message of a dashboard within 5 seconds. If they can't, the dashboard is too cluttered or lacks clear visual hierarchy.

---

### Assignment and Dashboard Projects

**Assignment 8.2** – Redesign a dashboard you have built:

- Apply visual hierarchy.

- Add whitespace.

- Ensure consistency.

- Test with the 5‑second rule.

- Document your changes.


---

### Summary and Revision Notes

- Visual hierarchy guides the user's eye.

- Simplicity: remove unnecessary elements.

- Consistency builds trust.

- Proximity groups related items.

- Whitespace improves readability.

- Always provide context.

---

## Lesson 8.3 – Color Theory

### Concept Explanation

Color is a powerful tool in dashboard design. Used correctly, it guides attention, encodes data, and conveys meaning. Used poorly, it confuses and misleads.

**Key Color Concepts**:

1. **Hue** – The basic color (red, blue, green, etc.).

2. **Saturation** – The intensity of the color.

3. **Brightness** – How light or dark the color is.


**Color Schemes**:

| **Scheme** | **Description** | **Use Case** |
|------------|-----------------|--------------|
| **Monochromatic** | Variations of one hue | Simple, clean, professional |
| **Analogous** | Colors next to each other on the color wheel | Harmonious, natural |
| **Complementary** | Colors opposite on the color wheel | High contrast, attention‑grabbing |
| **Sequential** | Light to dark of one color | Ordered data (low to high) |
| **Diverging** | Two contrasting colors with a midpoint | Positive vs negative values |

**Best Practices**:

- Use **blue** as the default for most data.

- Use **red** and **green** sparingly; many people are color‑blind.

- Ensure sufficient **contrast** between text and background.

- Use **color‑blind‑friendly** palettes (e.g., blue‑orange, blue‑yellow).

- Use **sequential** palettes for ordered data (sales, profit).

- Use **diverging** palettes for data with a meaningful midpoint (e.g., profit vs loss).

**Common Color Palettes**:

- **Tableau Default**: The blue-orange palette is a good starting point.

- **Color‑Blind‑Friendly**: Blue‑orange, blue‑yellow.

- **Corporate**: Use your company's brand colors.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Color influences how users perceive and interpret data. Consistent, thoughtful color use makes dashboards more intuitive and accessible.

- **Use cases**:

  - A **sales dashboard** uses blue for total sales and green for profit.
  
  - A **financial dashboard** uses red for negative values and green for positive values (though this can be problematic for color‑blind users).
  
  - A **marketing dashboard** uses brand colours for consistency.
  

---

### Step‑by‑Step Demonstration

**Applying a Color Scheme**:

1. In Tableau, open a worksheet.

2. Click on **Color** on the Marks Card.

3. In the color dialog, choose a palette.

4. For **sequential** data (e.g., sales), use a sequential palette (e.g., Blue).

5. For **diverging** data (e.g., profit with positive and negative), use a diverging palette (e.g., Red‑Green, but consider Blue‑Orange for accessibility).


**Customizing Colors**:

1. In the color dialog, click **Edit Colors**.

2. Assign specific colors to specific values (e.g., "Furniture" = #FF9900).

3. Save the palette for reuse.


**Using Color‑Blind‑Friendly Palettes**:

1. Search for color‑blind‑friendly palettes online.

2. In Tableau, you can import custom palettes using a preference file.

---

### Practical Examples

- **Example 1**: A bar chart using a sequential blue palette – the darkest bar shows the highest value.

- **Example 2**: A map using a diverging orange‑blue palette – orange for high sales, blue for low sales, white for average.

- **Example 3**: A dashboard using only brand colors – professional and consistent.


---

### Hands‑on Exercises

1. Create a bar chart of Sales by Category.

2. Apply a sequential blue color palette.

3. Change the palette to a diverging palette and observe the difference.

4. Create a map and apply a diverging palette.

5. Test your dashboard with a color‑blind simulator (available online).


---

### Mini Quiz

1. What is the difference between a sequential and a diverging color palette?

2. Why should you avoid using red and green together?

3. What is a color‑blind‑friendly palette?

4. What is the purpose of contrast in color design?

5. How can you customize colors in Tableau?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using too many colors – chaotic | Limit to 3‑5 main colors |
| Using red and green together – problematic for color‑blind users | Use blue‑orange or blue‑yellow |
| Low contrast – text is hard to read | Ensure sufficient contrast (4.5:1 for normal text) |
| Using color for no reason – adds clutter | Use color meaningfully (to encode data) |
| Not considering branding – inconsistent with corporate identity | Use brand colors where appropriate |

---

### Interview Questions

1. **What are the key considerations when choosing colors for a dashboard?**  

   *Answer*: I consider the type of data (sequential vs diverging), accessibility (color‑blind friendliness), contrast, branding, and the overall aesthetic. I aim for consistency and meaning – using color to encode data, not just for decoration.

2. **Why is it important to use color‑blind‑friendly palettes?**  

   *Answer*: Approximately 8% of men and 0.5% of women have some form of color blindness. Using red and green together makes it impossible for them to distinguish data. Color‑blind‑friendly palettes (blue‑orange, blue‑yellow) ensure your dashboard is accessible to everyone.

3. **How do you choose a color palette for a dashboard?**  

   *Answer*: I start with the data type – sequential for ordered data, diverging for data with a midpoint. I use color‑blind‑friendly palettes and consider the company's brand colours. I test the palette to ensure sufficient contrast and visual appeal.

---

### Assignment and Dashboard Projects

**Assignment 8.3** – Apply color best practices to a dashboard:

- Choose a color‑blind‑friendly palette.

- Apply sequential palettes to ordered data.

- Apply diverging palettes to positive/negative data.

- Ensure sufficient contrast.

- Document your color choices.


---

### Summary and Revision Notes

- Color encodes data and guides attention.

- Use sequential palettes for ordered data.

- Use diverging palettes for data with a meaningful midpoint.

- Avoid red‑green combinations.

- Use color‑blind‑friendly palettes.

- Ensure sufficient contrast.

---

## Lesson 8.4 – Typography

### Concept Explanation

**Typography** – the art of arranging text – is a critical but often overlooked aspect of dashboard design. Good typography makes your dashboard readable, professional, and trustworthy.

**Key Typography Concepts**:

1. **Font Family** – The typeface (e.g., Arial, Helvetica, Georgia).

   - **Serif** fonts (e.g., Times New Roman) have small decorative strokes.

   - **Sans‑Serif** fonts (e.g., Arial, Helvetica) do not have strokes and are generally recommended for dashboards.


2. **Font Size** – The size of the text in points (pt) or pixels (px).

   - Titles: 16‑20pt.

   - Subtitles: 12‑14pt.

   - Body text (axis labels, tooltips): 10‑12pt.

   - KPIs: 24‑36pt.


3. **Font Weight** – Bold, regular, light.

   - Use bold for titles and emphasis.

4. **Line Spacing** – The space between lines of text.

   - Use 1.5x line spacing for body text.

5. **Alignment** – Left, centre, right, justified.

   - Use left alignment for body text; centre for titles.

**Best Practices**:

- Use **sans‑serif** fonts (Arial, Helvetica, Open Sans) for dashboards.

- Use **consistent** fonts across all dashboard elements.

- **Maximum 2 fonts** per dashboard.

- Ensure **sufficient contrast** between text and background.

- Use **proper hierarchy** – titles larger than subtitles, subtitles larger than body text.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Good typography improves readability, reduces eye strain, and makes your dashboard look professional. Poor typography distracts and frustrates users.

- **Use cases**:

  - A **corporate dashboard** uses the company's standard font (e.g., Open Sans) for consistency.

  - A **high‑level executive dashboard** uses large, bold KPIs for quick reading.

  - A **detailed operational dashboard** uses smaller, readable fonts for tables.


---

### Step‑by‑Step Demonstration

**Setting Fonts in Tableau**:

1. In Tableau, click the **Format** menu → **Font**.

2. Set the default font for the workbook.

3. For individual elements (titles, axis labels), right‑click and select **Format**.


**Customizing Text in Tableau**:

1. Click on a worksheet title.

2. In the **Format** pane, change the font, size, weight, and colour.


**Adding a Text Object**:

1. In a dashboard, drag a **Text** object from the Objects pane.

2. Type your text.

3. Use the toolbar to change font, size, and alignment.

---

### Practical Examples

- **Example 1**: A dashboard with a sans‑serif font (Arial), title size 18pt, subtitle size 14pt, and axis labels 10pt.

- **Example 2**: A KPI card with a bold, large font (28pt) for the KPI value and a smaller font (12pt) for the label.

---

### Hands‑on Exercises

1. Open a dashboard.

2. Set the default font to **Arial** (or Open Sans).

3. Change the title font size to 18pt.

4. Change the subtitle font size to 14pt.

5. Ensure all fonts are consistent.


---

### Mini Quiz

1. What is the recommended font type for dashboards?

2. What are the recommended font sizes for titles, subtitles, and body text?

3. How many fonts should you use per dashboard?

4. Why is font consistency important?

5. What is the difference between serif and sans‑serif fonts?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using too many fonts – chaotic | Use 1‑2 fonts maximum |
| Using serif fonts – harder to read on screens | Use sans‑serif fonts |
| Font sizes too small – unreadable | Use appropriate sizes (titles 16‑20pt, body 10‑12pt) |
| Low contrast – text hard to read | Ensure sufficient contrast |
| Inconsistent font usage – looks unprofessional | Use consistent fonts across all elements |

---

### Interview Questions

1. **What are the key considerations for typography in dashboard design?**  

   *Answer*: I consider font type (sans‑serif), font sizes (hierarchy), consistency (1‑2 fonts), contrast with the background, and proper alignment. The goal is readability and a professional look.

2. **Why is font consistency important in dashboards?**  

   *Answer*: Consistency reduces cognitive load – users don't have to re‑adjust to different fonts. It also makes the dashboard look more professional and trustworthy.

3. **What font size would you use for a KPI value?**  

   *Answer*: I would use a large font size, typically 24‑36pt, so the KPI is immediately visible and readable.

---

### Assignment and Dashboard Projects

**Assignment 8.4** – Apply typography best practices to a dashboard:

- Choose a sans‑serif font.

- Set font sizes for titles, subtitles, body text, and KPIs.

- Ensure consistency across all elements.

- Document your typography choices.


---

### Summary and Revision Notes

- Use sans‑serif fonts for dashboards.

- Hierarchy: titles (16‑20pt), subtitles (12‑14pt), body (10‑12pt), KPIs (24‑36pt).

- Use 1‑2 fonts consistently.

- Ensure sufficient contrast.

- Align text properly.

---

## Lesson 8.5 – User Experience (UX)

### Concept Explanation

**User Experience (UX)** is the overall experience a user has when interacting with your dashboard. A good UX means the user can achieve their goals easily, efficiently, and with satisfaction.

**Core UX Principles**:

1. **Know Your Users** – Who is using the dashboard? What are their goals? What is their technical proficiency?

   - Executives want high‑level summaries.

   - Analysts want detailed data and interactivity.

   - Operational users want quick, actionable information.


2. **Make it Intuitive** – Users should not need training to use the dashboard.

   - Use clear labels.

   - Use familiar interactions (clicks, hovers).

   - Provide tooltips for context.


3. **Minimize Clicks** – The most important information should be immediately visible.

   - Put KPIs at the top.

   - Use drill‑through for details, not the main view.


4. **Provide Feedback** – Show users what happens when they interact.

   - Highlight selected items.

   - Show loading indicators for slow operations.


5. **Guide the User** – Use visual cues to show where to go next.

   - Use buttons, titles, and layout to guide the eye.

   - Use tooltips to explain interactivity.


6. **Test with Users** – Observe how users interact with your dashboard and iterate.

   - User testing is the best way to identify UX issues.


---

### Importance and Real‑World Use Cases

- **Why it matters**: A beautiful dashboard that is hard to use will be abandoned. UX is about empathy – putting yourself in the user's shoes.

- **Use cases**:

  - A **sales dashboard** is designed with the sales manager in mind: KPIs at the top, clear filters, and drill‑through for detail.

  - A **customer support dashboard** is designed for quick decisions: alerts for high‑priority issues, easy navigation.


---

### Step‑by‑Step Demonstration

**Defining User Personas**:

1. Identify the different user groups for your dashboard.

2. For each group, define their goals, tasks, and technical proficiency.

3. Design the dashboard to meet the needs of the primary user group.


**Adding Guidance**:

1. Add a text box with instructions: "Click on a region to filter the charts."

2. Use tooltips to explain interactivity.

3. Add a "Help" or "About" section.


**Testing with Users**:

1. Ask a colleague to use your dashboard without any guidance.

2. Observe where they get stuck.

3. Iterate based on their feedback.

---

### Practical Examples

- **Example 1**: A sales dashboard with clear labels, filters at the top, and a note: "Hover over charts for details."

- **Example 2**: A financial dashboard with a "Reset" button to clear all filters.

---

### Hands‑on Exercises

1. Identify the user personas for your dashboard.

2. Add guidance (tooltips, instructions) to your dashboard.

3. Ask a colleague to test your dashboard and provide feedback.

4. Iterate based on the feedback.


---

### Mini Quiz

1. What is UX in the context of dashboard design?

2. Why is it important to know your users?

3. What is the goal of minimizing clicks?

4. How can you provide feedback to users?

5. Why is user testing important?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Assuming users know how to use the dashboard | Add guidance (tooltips, instructions) |
| Requiring too many clicks to find information | Put key information on the main page |
| No feedback on user actions | Highlight selections, show loading indicators |
| Designing for yourself, not the user | Know your users and design for them |
| Not testing with users | Conduct user testing and iterate |

---

### Interview Questions

1. **How do you ensure your dashboard is user‑friendly?**  

   *Answer*: I start by understanding the user's goals and technical proficiency. I design a clear layout with intuitive interactions, provide guidance (tooltips, instructions), and test with real users to identify and fix issues.
   
2. **What is the role of feedback in UX?**  

   *Answer*: Feedback informs users that their action has been registered. Without feedback, users may think the dashboard is broken or slow. Highlighting selections or showing loading indicators improves the experience.

3. **How do you handle different user types on the same dashboard?**  

   *Answer*: I design for the primary user group and provide additional features (like drill‑through) for more advanced users. I might also create different dashboards or views for different user types.

---

### Assignment and Dashboard Projects

**Assignment 8.5** – Conduct a UX review of a dashboard:

- Identify user personas.

- Identify UX issues.

- Propose improvements.

- Implement the improvements.

- Document the changes.


---

### Summary and Revision Notes

- UX is the overall user experience.

- Know your users and their goals.

- Make the dashboard intuitive.

- Minimize clicks for key information.

- Provide feedback for interactions.

- Test and iterate with users.

---

## Lesson 8.6 – Storytelling with Data

### Concept Explanation

**Storytelling with data** is the art of using data, visualisation, and narrative to communicate insights in a compelling and memorable way. A good data story:

1. **Has a clear narrative** – beginning, middle, end.

2. **Focuses on the key insight** – what is the one thing you want the user to remember?

3. **Uses the right visuals** – to support the narrative.

4. **Has a call to action** – what should the user do with this information?


**The Storytelling Framework**:

| **Step** | **Description** | **Example** |
|----------|-----------------|-------------|
| **1. Set the context** | What is the situation? | "Sales in the West region have declined 15% this quarter." |
| **2. Present the conflict** | What is the problem or opportunity? | "The decline is driven by a drop in Furniture sales." |
| **3. Show the analysis** | What does the data say? | "Furniture sales in the West have declined every month since March." |
| **4. Provide a resolution** | What action should be taken? | "Focus marketing efforts on Furniture in the West." |

**Storytelling in Tableau**:

- Use **Stories** (a sequence of story points) to guide the user through the narrative.

- Use **annotations** (text boxes, captions) to explain insights.

- Use **tooltips** to provide additional context.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Data alone is not enough – it needs a narrative. Storytelling makes data memorable and drives action.

- **Use cases**:

  - A **sales presentation** uses a Tableau story to walk the sales team through quarterly performance, highlighting wins and opportunities.

  - A **board report** uses a story to present financial results, starting with the big picture and drilling into details.

---

### Step‑by‑Step Demonstration

**Creating a Story in Tableau**:

1. Click the **New Story** icon at the bottom.

2. Drag a worksheet or dashboard onto the first story point.

3. Add a text box for context: "This quarter's sales performance."

4. Add a second story point with another worksheet.

5. Add text for the conflict: "Furniture sales are declining."

6. Add a third story point with a recommendation: "Focus marketing on Furniture in the West."


**Using Annotations**:

1. In a worksheet, right‑click a data point → **Add Annotation**.

2. Type your insight, e.g., "Decline started in March due to supply chain issues."


**Adding a Call to Action**:

1. In the story, add a final text box: "Next steps: Increase Furniture marketing budget in the West by 20%."


---

### Practical Examples

- **Example 1**: A sales story: "Sales are up overall, but the West region is lagging. Here's why... and here's what we should do."

- **Example 2**: A financial story: "Revenue is growing, but profit margins are shrinking. Here's the cost breakdown... and here's where we can cut costs."

---

### Hands‑on Exercises

1. Create a story with at least 3 story points.

2. Use a text box to set the context on the first point.

3. Use a second point to show the analysis.

4. Use a third point to show a recommendation.

5. Add annotations to highlight key insights.


---

### Mini Quiz

1. What are the four steps of a data story?

2. How do you create a story in Tableau?

3. What is the purpose of an annotation?

4. Why is a call to action important in a data story?

5. How does a story differ from a dashboard?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Presenting data without a narrative – users don't know what to take away | Always have a clear narrative |
| Too much text – users stop reading | Be concise; use visuals to do the talking |
| No call to action – users don't know what to do next | Always include a clear call to action |
| Forgetting the audience – story doesn't resonate | Tailor the story to the audience |

---

### Interview Questions

1. **What is data storytelling and why is it important?**  

   *Answer*: Data storytelling combines data, visualisation, and narrative to communicate insights in a compelling way. It is important because it makes data memorable and drives action.

2. **How do you create a data story in Tableau?**  

   *Answer*: I use the Story feature in Tableau, which allows me to sequence worksheets and dashboards with text explanations. I add annotations to highlight key points and end with a call to action.

3. **What is the difference between a dashboard and a story?**  

   *Answer*: A dashboard is a single page with multiple visuals for exploration. A story is a sequence of pages (story points) that guides the user through a narrative, building from context to conclusion.

---

### Assignment and Dashboard Projects

**Assignment 8.6** – Create a data story for a business question:

- Choose a business question (e.g., "Why is the West region underperforming?").

- Build a story with 3‑5 story points.

- Include context, analysis, and a recommendation.

- Add annotations and a call to action.

- Document the story.


---

### Summary and Revision Notes

- Data stories have: context, conflict, analysis, resolution.

- Use Tableau Stories to sequence content.

- Use annotations to highlight insights.

- Always end with a call to action.

- Tailor the story to the audience.

---

## Lesson 8.7 – Accessibility

### Concept Explanation

**Accessibility** in dashboard design ensures that people with disabilities can use and understand your dashboard. This includes visual, auditory, motor, and cognitive disabilities.

**Key Accessibility Considerations**:

1. **Color Contrast** – Ensure sufficient contrast between text and background.

   - WCAG 2.1 guidelines: 4.5:1 for normal text, 3:1 for large text.

2. **Color‑Blindness** – Avoid red‑green combinations.

   - Use color‑blind‑friendly palettes (blue‑orange, blue‑yellow).

3. **Text Legibility** – Use readable fonts and sizes.

   - Minimum font size: 12pt for body text.

4. **Alternative Text** – Provide text descriptions for images and charts.

   - In Tableau, you can add captions to sheets and dashboards.

5. **Keyboard Navigation** – Ensure users can navigate without a mouse.

   - Tableau Server/Cloud supports keyboard shortcuts.

6. **Screen Reader Support** – Ensure content is readable by screen readers.

   - Use proper heading structures and descriptive labels.

7. **Cognitive Accessibility** – Keep designs simple and intuitive.

   - Avoid clutter; use clear, concise language.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Accessibility is not just a legal requirement – it is the right thing to do. An accessible dashboard ensures that everyone, regardless of ability, can benefit from data insights.

- **Use cases**:

  - A **government agency** must make dashboards accessible to comply with Section 508.
  
  - A **healthcare organisation** ensures dashboards are usable by staff with visual impairments.
  
  - A **large enterprise** adopts accessibility standards as part of their inclusion policy.
  

---

### Step‑by‑Step Demonstration

**Checking Color Contrast**:

1. Use a color contrast checker (e.g., WebAIM) to test your palette.

2. Adjust colors to meet WCAG guidelines.

**Adding Captions**:

1. In Tableau, add a caption to a worksheet: **Worksheet** → **Show Caption**.

2. Write a descriptive caption.

**Using Keyboard Shortcuts**:

1. In Tableau Server/Cloud, use keyboard shortcuts:

   - `Tab` to navigate between elements.

   - `Enter` to select.

---

### Practical Examples

- **Example 1**: A dashboard using a color‑blind‑friendly palette (blue‑orange) instead of red‑green.

- **Example 2**: A dashboard with a caption explaining the chart: "This bar chart shows sales by category for 2025."

---

### Hands‑on Exercises

1. Test your dashboard with a color‑blind simulator.

2. Check the color contrast of your text and background.

3. Add captions to at least two worksheets.

4. Navigate your dashboard using only the keyboard.


---

### Mini Quiz

1. What is the WCAG contrast ratio for normal text?

2. Why should you avoid red‑green color combinations?

3. What is the purpose of alternative text (captions)?

4. Why is keyboard navigation important?

5. What is cognitive accessibility?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Using red‑green combinations | Use blue‑orange or blue‑yellow |
| Low color contrast | Ensure 4.5:1 contrast for text |
| No captions or alt text | Add descriptive captions |
| Mouse‑only navigation | Ensure keyboard support |
| Cluttered, complex designs | Keep designs simple and intuitive |

---

### Interview Questions

1. **What are the key considerations for making a dashboard accessible?**  

   *Answer*: Color contrast (4.5:1), color‑blind‑friendly palettes (avoid red‑green), text legibility (font size, font type), alternative text (captions), keyboard navigation, and screen reader support.

2. **Why is accessibility important in dashboard design?**  

   *Answer*: Accessibility ensures that everyone, regardless of ability, can access and benefit from data insights. It is also a legal requirement in many jurisdictions.

3. **How would you test a dashboard for accessibility?**  

   *Answer*: I would use a color contrast checker, a color‑blind simulator, keyboard navigation testing, and screen reader testing. I would also involve users with disabilities in user testing.

---

### Assignment and Dashboard Projects

**Assignment 8.7** – Make a dashboard accessible:

- Check color contrast and adjust if needed.

- Switch to a color‑blind‑friendly palette.

- Add captions to all worksheets.

- Test keyboard navigation.

- Document the changes.


---

### Summary and Revision Notes

- Accessibility ensures everyone can use the dashboard.

- Color contrast: 4.5:1 for normal text.

- Avoid red‑green combinations.

- Add captions for alt text.

- Support keyboard navigation.

- Keep designs simple and intuitive.

---

## Lesson 8.8 – Mobile Dashboard Design

### Concept Explanation

Many users access dashboards on mobile devices (phones and tablets). Designing for mobile requires a different approach than desktop design.

**Key Mobile Considerations**:

1. **Screen Size** – Mobile screens are small; you need to prioritise.

   - Show only the most important information.

   - Use a single‑column layout.
   
2. **Touch Interaction** – Users interact with touch, not mouse.

   - Make buttons and filters large enough to tap.

   - Use touch‑friendly controls (dropdowns, sliders).

3. **Performance** – Mobile devices have less processing power.

   - Optimise performance (use extracts, reduce marks).

4. **Readability** – Text must be readable on small screens.

   - Use larger font sizes.

5. **Navigation** – Provide clear navigation.

   - Use buttons and menus.

**Device‑Specific Layouts**:

- Tableau allows you to create **device‑specific layouts** (Desktop, Tablet, Phone). You can customise each layout independently.

- In Tableau, use **Device Preview** to design for each device.

---

### Importance and Real‑World Use Cases

- **Why it matters**: More and more users access dashboards on mobile devices. A dashboard that is unusable on a phone will be ignored.

- **Use cases**:

  - A **sales team** accesses dashboards on tablets during client meetings.

  - A **CEO** checks the executive dashboard on their phone.

  - A **field service team** uses a phone to view customer data.

---

### Step‑by‑Step Demonstration

**Creating a Mobile Layout**:

1. Open your dashboard in Tableau.

2. Click the **Device Preview** button (mobile icon).

3. Select **Phone**.

4. Click **Edit** to customise the layout.

5. Remove or hide non‑essential elements.

6. Rearrange the remaining elements vertically.

7. Resize elements to fit the phone screen.


**Creating a Tablet Layout**:

1. Repeat the steps for **Tablet**.

2. Tablet layouts can have more elements than phone layouts.

3. Use a 2‑column grid.


**Testing Mobile Design**:

1. Use the Device Preview to test different screen sizes.

2. If possible, test on a real device.


---

### Practical Examples

- **Example 1**: A mobile dashboard shows only KPIs and one chart; the rest is hidden.

- **Example 2**: A tablet dashboard shows KPIs in a row and two charts side‑by‑side.

---

### Hands‑on Exercises

1. Create a Phone layout for a dashboard:

   - Show only KPIs and one chart.

   - Hide the rest.

2. Create a Tablet layout:

   - Show KPIs in a row.

   - Show two charts side‑by‑side.

3. Test both layouts using Device Preview.


---

### Mini Quiz

1. Why is mobile dashboard design important?

2. What are the key considerations for mobile design?

3. How do you create a phone layout in Tableau?

4. What is the difference between a phone and a tablet layout?

5. How can you test a mobile layout?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Showing the desktop layout on a phone – impossible to read | Always create a phone layout |
| Using small touch targets – users can't tap | Make buttons and filters large enough for touch |
| Ignoring performance – slow on mobile | Optimise performance for mobile |
| Too much clutter – overwhelming on a small screen | Show only the most important information |

---

### Interview Questions

1. **How do you design dashboards for mobile devices?**  

   *Answer*: I use device‑specific layouts in Tableau. For phones, I show only the most important information in a single‑column layout, use large touch targets, and ensure text is readable. For tablets, I can show more information in a grid layout.

2. **What is the difference between a desktop and a mobile dashboard design?**  

   *Answer*: Desktop dashboards can show more information, use mouse interactions, and have smaller text. Mobile dashboards need to prioritise key information, use touch‑friendly controls, and have larger text.

3. **How do you test a mobile dashboard in Tableau?**  

   *Answer*: I use Device Preview to test different screen sizes and layouts. I also test on real devices if possible.

---

### Assignment and Dashboard Projects

**Assignment 8.8** – Create a mobile‑friendly dashboard:

- Create a Phone layout.

- Create a Tablet layout.

- Test both layouts.

- Document the changes.


---

### Summary and Revision Notes

- Mobile dashboards need to prioritise information.

- Use device‑specific layouts (Phone, Tablet).

- Make touch targets large.

- Optimise performance.

- Test on real devices.

---

## Final Phase 8 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can choose the right chart for different data and messages.

-  I understand and can apply dashboard design principles (hierarchy, simplicity, consistency, whitespace).

-  I can apply color theory (sequential, diverging, color‑blind‑friendly).

-  I can apply typography best practices.

-  I understand UX principles and can apply them.

-  I can create a data story using Tableau Stories.

-  I can make dashboards accessible.

-  I can design for mobile devices.


If you have completed all assignments and feel confident, you have achieved **Expert** level in dashboard design!

---

### Answers to Mini Quizzes

**Lesson 8.1**: 1. Bar chart. 2. Line chart. 3. For part‑to‑whole with few categories. 4. Hard to compare angles. 5. Scatter plot.

**Lesson 8.2**: 1. Guiding the user's eye from most to least important. 2. Builds trust and reduces cognitive load. 3. Improves readability. 4. User should understand the message in 5 seconds. 5. Using proximity – placing related items together.

**Lesson 8.3**: 1. Sequential = light to dark (ordered data); Diverging = two contrasting colors with midpoint. 2. Color‑blind users can't distinguish them. 3. Avoids red‑green, uses blue‑orange or blue‑yellow. 4. Makes text readable. 5. Click Color on Marks Card → Edit Colors.

**Lesson 8.4**: 1. Sans‑serif. 2. Titles 16‑20pt, subtitles 12‑14pt, body 10‑12pt, KPIs 24‑36pt. 3. 1‑2 fonts. 4. Reduces cognitive load. 5. Serif has decorative strokes; sans‑serif does not.

**Lesson 8.5**: 1. Overall user experience. 2. To design for their needs. 3. Reduce effort. 4. Highlight selections, show indicators. 5. Identifies UX issues.

**Lesson 8.6**: 1. Context, conflict, analysis, resolution. 2. New Story icon → drag content. 3. Highlight key insights. 4. Tells users what to do next. 5. Story is narrative; dashboard is exploration.

**Lesson 8.7**: 1. 4.5:1. 2. Color‑blind users can't distinguish. 3. To describe the content. 4. For users who can't use a mouse. 5. Designing for cognitive disabilities.

**Lesson 8.8**: 1. Many users access on mobile. 2. Screen size, touch interaction, performance, readability. 3. Device Preview → Phone → Edit. 4. Phone = single column; Tablet = more columns. 5. Device Preview and real devices.

---

**Congratulations!** You have completed all eight phases of this comprehensive Tableau curriculum. You are now a full‑stack Tableau professional with expertise in:

- Data connection and preparation.

- Calculations and LOD expressions.

- Visualisation and chart selection.

- Dashboard design and interactivity.

- Deployment and governance.

- Design best practices for accessibility and mobile.

You are ready to tackle any Tableau project – from a simple dashboard to a complex enterprise deployment. Remember that Tableau and design trends are constantly evolving, so keep learning through the Tableau community, blogs, and official documentation. The best way to maintain your skills is to keep building dashboards and solving real‑world problems.

If you have any further questions, I'm here to help. Good luck on your Tableau journey!


---







<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>