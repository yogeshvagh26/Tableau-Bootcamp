# Phase 7: Tableau Server and Cloud

Welcome to **Phase 7** – the deployment and collaboration layer of your Tableau expertise! Throughout the previous six phases, you learned to connect to data, prepare it, build calculations, create stunning visualisations, and design interactive dashboards. Now, you will learn how to **share your work with the world**.

Tableau Server and Tableau Cloud are the platforms that transform your individual dashboards into enterprise‑wide analytics solutions. They enable teams to collaborate, keep data fresh, and govern content at scale.

In this phase, we will cover:

- The difference between Tableau Server (self‑hosted) and Tableau Cloud (SaaS).

- Publishing workbooks and data sources.

- Sharing dashboards with users and groups.

- User roles and permissions.

- Scheduling extract refreshes.

- Collaboration features.

- Governance best practices.

Let's bring your dashboards to life in the enterprise!

---

## Lesson 7.1 – Introduction to Tableau Server

### Concept Explanation

**Tableau Server** is an enterprise analytics platform that you install and manage on your own infrastructure – whether on‑premises or in a public cloud (IaaS) like AWS or Azure. It provides a centralised location for publishing, sharing, and governing Tableau content across your organisation.

**Key characteristics**:

- **Self‑hosted** – You control the hardware, software, and security configurations.

- **Full control** – Infrastructure can be tuned for performance and scaled across multiple nodes.

- **Data governance** – Includes features like Tableau Catalog for end‑to‑end data lineage and governance.

- **Flexible deployment** – Install on‑premises, in your own cloud (AWS, Azure, GCP), or in a hybrid environment.


**What Tableau Server enables**:

- Centralised access to dashboards and reports via web browser or mobile app.

- Scheduled data refreshes to keep extracts up‑to‑date.

- User and group management with fine‑grained permissions.

- Collaboration through comments, subscriptions, and data source sharing.


**Recent evolution**: Tableau Server (and Tableau Cloud) have evolved beyond being simple web servers for publishing reports. They now serve as integrated data hubs combining data warehousing, headless BI, and AI capabilities.

---

### Importance and Real‑World Use Cases

- **Why it matters**: A dashboard on your laptop helps no one. Tableau Server is the bridge between report creators and business users, enabling secure, governed, and scalable distribution of insights.

- **Use cases**:

  - A **financial services firm** deploys Tableau Server on‑premises to meet strict data residency and compliance requirements.

  - A **manufacturing company** uses Tableau Server on AWS to provide real‑time operational dashboards to factory floor managers.

  - A **government agency** uses Tableau Server with Tableau Catalog to maintain audit trails and data lineage for regulatory reporting.


---

### Step‑by‑Step Demonstration

**Accessing Tableau Server**:

1. Open a web browser and navigate to your Tableau Server URL (e.g., `https://tableau.yourcompany.com`).

2. Sign in with your credentials.

3. Explore the **Home** page – you'll see recent content, projects, and navigation options.

4. Navigate to **Projects** to see how content is organised.

5. Click on **Explore** to browse all available content.

**Key navigation elements**:

- **Home** – personalised landing page.

- **Explore** – browse all content.

- **Projects** – organised folders for content.

- **Favorites** – bookmarked content.

- **Recent** – recently accessed content.

- **Collections** – curated groups of content.

---

### Practical Examples

- **Example 1**: A Tableau Server deployment in a bank with 500 users, hosted on‑premises to comply with financial regulations.

- **Example 2**: A Tableau Server deployment on Azure with auto‑scaling to handle peak usage during monthly reporting cycles.

---

### Hands‑on Exercises

1. If you have access to a Tableau Server instance, log in and explore the interface.

2. Identify the Home, Explore, and Projects sections.

3. Find a published workbook and open it.

4. If you don't have access, review the Tableau Server documentation and note the key components.

---

### Mini Quiz

1. What is Tableau Server?

2. What are the key differences between Tableau Server and Tableau Desktop?

3. Where can Tableau Server be deployed?

4. What is Tableau Catalog used for?

5. How has Tableau Server evolved in recent years?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Treating Tableau Server as just a file repository | Use projects, tags, and collections to organise content meaningfully |
| Neglecting regular server maintenance | Plan for regular backups, updates, and performance monitoring |
| Not leveraging Tableau Catalog for governance | Use Tableau Catalog to track data lineage and ensure trust |
| Giving everyone administrative access | Restrict admin privileges to a small, trusted team |

---

### Interview Questions

1. **What is Tableau Server and how does it differ from Tableau Desktop?**  

   *Answer*: Tableau Desktop is the authoring tool for creating visualisations. Tableau Server is the enterprise platform for publishing, sharing, and governing those visualisations across an organisation.

2. **What are the key features of Tableau Server?**  

   *Answer*: Centralised content management, scheduled data refreshes, user and group permissions, collaboration features, Tableau Catalog for data governance, and scalability across multiple nodes.

3. **Why would an organisation choose Tableau Server over Tableau Cloud?**  

   *Answer*: For data sovereignty and compliance requirements, full control over infrastructure and security configurations, and the ability to customise performance tuning.

---

### Assignment and Dashboard Projects

**Assignment 7.1** – Write a one‑page summary comparing Tableau Server and Tableau Cloud. Include:

- Deployment models.

- Infrastructure management.

- Security and governance.

- Use cases for each.


---

### Summary and Revision Notes

- Tableau Server is a self‑hosted enterprise analytics platform.

- Provides centralised content publishing, sharing, and governance.

- Deployable on‑premises or in the cloud (IaaS).

- Features include Tableau Catalog for data lineage and governance.

- Tableau Server has evolved into a comprehensive data hub.

---

## Lesson 7.2 – Tableau Cloud

### Concept Explanation

**Tableau Cloud** (formerly Tableau Online) is the software‑as‑a‑service (SaaS) version of Tableau Server, hosted and managed by Salesforce. It provides the same core functionality as Tableau Server but without the infrastructure management overhead.

**Key characteristics**:

- **Fully hosted** – Salesforce handles infrastructure, updates, and scaling.

- **Multi‑tenant** – Resources are shared among all sites on the same pod.

- **Faster setup** – Get started in minutes, not weeks.

- **Default choice** – The recommended deployment option for most new customers.


**Tableau Cloud Editions**:

| **Edition** | **Key Features** |
|-------------|------------------|
| **Standard Edition** | Core analytics, data sources, and sharing. |
| **Enterprise Edition** | Advanced security, governance, and data management. |
| **Cloud+ Edition** | Included with Tableau+ bundle; includes Tableau Next. |

**Licensing (per user/month, billed annually)**:

| **Role** | **Price** |
|----------|-----------|
| **Viewer** | $15/user/month |
| **Explorer** | $42/user/month |
| **Creator** | $75/user/month |

---

### Importance and Real‑World Use Cases

- **Why it matters**: Tableau Cloud removes the operational burden of managing servers, allowing organisations to focus on analytics rather than infrastructure.

- **Use cases**:

  - A **startup** uses Tableau Cloud to quickly deploy analytics without hiring IT staff.

  - A **global enterprise** uses Tableau Cloud's multi‑tenant architecture to serve thousands of users across multiple sites.

  - A **consulting firm** uses Tableau Cloud to deliver dashboards to clients without managing servers.


---

### Step‑by‑Step Demonstration

**Accessing Tableau Cloud**:

1. Navigate to `https://online.tableau.com` (or your organisation's Tableau Cloud URL).

2. Sign in with your credentials.

3. The interface is similar to Tableau Server – explore Home, Explore, and Projects.


**Checking Your Edition**:

1. Click the **Settings** icon (gear) in the top right.

2. Select **Site Settings**.

3. Look for the edition information.


**Creating a Site** (for administrators):

1. In the Admin menu, select **Sites**.

2. Click **New Site**.

3. Enter a name and select the site's language and time zone.

4. Click **Create**.

---

### Practical Examples

- **Example 1**: A marketing agency uses Tableau Cloud to host client dashboards, with each client having its own site.

- **Example 2**: A retail company uses Tableau Cloud Enterprise Edition for advanced security features like single sign‑on and row‑level security.

---

### Hands‑on Exercises

1. If you have access to Tableau Cloud, log in and explore the interface.

2. Identify the site settings and edition.

3. Explore the projects and content.

4. If you don't have access, review the Tableau Cloud documentation.


---

### Mini Quiz

1. What is Tableau Cloud?

2. How does Tableau Cloud differ from Tableau Server?

3. What are the three editions of Tableau Cloud?

4. What are the three user roles and their prices?

5. Why is Tableau Cloud the default choice for most new deployments?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Assuming Tableau Cloud has the same performance as a tuned Server instance | Understand that Tableau Cloud is multi‑tenant; performance can vary |
| Not planning for extract refresh scheduling limits | Check the refresh limits for your edition |
| Ignoring data residency requirements | Verify that Tableau Cloud data centres meet your compliance needs |
| Not using sites for multi‑tenant deployments | Use separate sites for different business units or tenants |

---

### Interview Questions

1. **What is Tableau Cloud and how is it different from Tableau Server?**  

   *Answer*: Tableau Cloud is the SaaS version of Tableau Server, fully hosted and managed by Salesforce. It requires no infrastructure management, offers faster setup, and is multi‑tenant. Tableau Server is self‑hosted, providing full control over infrastructure.

2. **What are the licensing options for Tableau Cloud?**  

   *Answer*: Tableau Cloud has three editions: Standard, Enterprise, and Cloud+. User roles are Viewer ($15/month), Explorer ($42/month), and Creator ($75/month), billed annually.

3. **When would you choose Tableau Cloud over Tableau Server?**  

   *Answer*: When you want to avoid infrastructure management, need faster deployment, and don't have strict data sovereignty requirements.

---

### Assignment and Dashboard Projects

**Assignment 7.2** – Research Tableau Cloud and write a business case for adopting it in a hypothetical organisation. Include:

- Licensing costs.

- Deployment timeline.

- Benefits over Tableau Server.

- Potential challenges.


---

### Summary and Revision Notes

- Tableau Cloud is the SaaS version of Tableau Server.

- Fully hosted by Salesforce – no infrastructure management.

- Editions: Standard, Enterprise, Cloud+.

- User roles: Viewer ($15), Explorer ($42), Creator ($75).

- Recommended for most new deployments.

---

## Lesson 7.3 – Publishing Workbooks

### Concept Explanation

**Publishing** is the process of uploading a workbook from Tableau Desktop to Tableau Server or Tableau Cloud. When you publish, you make your visualisations available to others via the web or mobile apps.

**What gets published**:

- **Workbook** – all worksheets, dashboards, and stories.

- **Data source** – the underlying data connection (can be embedded or published separately).

- **Extract** – if using an extract, it is uploaded with the workbook.


**Publishing options**:
- **Embedded data source** – the data source is contained within the workbook.

- **Published data source** – the data source is published separately and can be reused by other workbooks.

- **Live or Extract** – choose whether to use a live connection or an extract.


**Publishing from Tableau Desktop**:

1. Open your workbook in Tableau Desktop.

2. Go to **Server** → **Publish Workbook**.

3. Select the destination project.

4. Choose whether to publish the data source separately.

5. Set the extract refresh schedule (if using an extract).

6. Click **Publish**.


**Publishing from the web**:

1. In Tableau Server/Cloud, navigate to the project.

2. Click **New** → **Workbook**.

3. Select the file to upload.

4. Configure the data source and refresh settings.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Publishing is how you share your work. Without publishing, your dashboards remain isolated on your machine.


- **Use cases**:

  - A **data analyst** publishes a monthly sales report so the sales team can access it every morning.
  
  - A **finance team** publishes a budget dashboard to a project where multiple analysts collaborate.
  
  - A **consultant** publishes a client dashboard to a Tableau Cloud site for the client to view.
  

---

### Step‑by‑Step Demonstration

**Publishing a Workbook**:

1. Open a workbook in Tableau Desktop (e.g., your dashboard from Phase 5).

2. Click **Server** → **Publish Workbook**.

3. In the **Publish Workbook to Tableau Server** dialog:

   - Select the **Project** where you want to publish.

   - Give the workbook a **Name**.

   - Choose to **Publish the data source separately** if you want to reuse it.

   - Set the **Extract Schedule** if using an extract.

   - Configure authentication and other options.

4. Click **Publish**.


**Publishing a Data Source Separately**:

1. In Tableau Desktop, go to the Data pane.

2. Click the dropdown menu for the data source.

3. Select **Save As Published Data Source**.

4. Enter the details and publish.


**Verifying the Published Workbook**:

1. In Tableau Server/Cloud, navigate to the project.

2. Open the workbook to verify it displays correctly.

3. Test interactivity (filters, parameters, actions).


---

### Practical Examples

- **Example 1**: A workbook with an embedded data source is published to a team project. The team can view and interact with the dashboard.

- **Example 2**: A data source is published separately so that multiple workbooks can use the same data, ensuring consistency.

---

### Hands‑on Exercises

1. Open any workbook you have created in Tableau Desktop.

2. Publish it to Tableau Server or Tableau Cloud (if you have access).

3. Choose a project and set a name.

4. If using an extract, select a refresh schedule.

5. Open the published workbook in the browser and verify it works.


---

### Mini Quiz

1. How do you publish a workbook from Tableau Desktop?

2. What is the difference between publishing a data source embedded vs separately?

3. What settings can you configure when publishing a workbook?

4. How do you publish a data source separately?

5. Where can you find a published workbook after publishing?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Publishing without testing – broken dashboards frustrate users | Test all interactivity in Desktop before publishing |
| Not setting extract refresh schedules – data becomes stale | Always configure refresh schedules for extracts |
| Publishing to the wrong project – users can't find it | Organise content into logical projects |
| Not publishing data sources separately – duplication of data | Publish data sources separately for reuse |

---

### Interview Questions

1. **How do you publish a workbook from Tableau Desktop to Tableau Server?**  


   *Answer*: Open the workbook, go to Server → Publish Workbook, select the destination project, configure the data source and refresh settings, and click Publish.

2. **What is the advantage of publishing a data source separately?**  


   *Answer*: It allows multiple workbooks to use the same data source, ensuring consistency and centralised data management.

3. **What extract refresh options are available when publishing?**  


   *Answer*: You can choose a schedule from the server, set it to refresh daily, weekly, or monthly, and select full or incremental refresh.

---

### Assignment and Dashboard Projects

**Assignment 7.3** – Publish a workbook to Tableau Server or Cloud:

- Choose any dashboard you have built.

- Publish it to a project.

- Configure the data source and refresh schedule.

- Open it in the browser and verify it works.

- Document the process.


---

### Summary and Revision Notes

- Publishing uploads workbooks to Tableau Server/Cloud.

- Data sources can be embedded or published separately.

- Extracts require a refresh schedule.

- Always test before publishing.

---

## Lesson 7.4 – Sharing Dashboards

### Concept Explanation

**Sharing** in Tableau Server/Cloud is how you give others access to your published content. You can share workbooks, views, dashboards, and data sources with users or groups.

**Sharing methods**:

1. **Project‑based sharing** – Users inherit permissions from the project.

2. **Direct sharing** – Share a specific workbook or view with individuals or groups.

3. **Link sharing** – Share a direct URL to a view or dashboard.

4. **Subscriptions** – Send scheduled email updates of dashboards.

5. **Collections** – Curated groups of content.


**Permission levels**:

- **Viewer** – Can view and interact with content.

- **Explorer** – Can view, interact, and save custom views.

- **Interactor** – Can interact with published dashboards (web editing).

- **Publisher** – Can publish content to projects.

**Sharing a view via link**:

1. Open the published workbook.

2. Navigate to the view or dashboard you want to share.

3. Copy the URL from the browser.

4. Send the link to recipients (they need appropriate permissions).


---

### Importance and Real‑World Use Cases

- **Why it matters**: Sharing is the ultimate goal of your work. It enables data‑driven decisions across the organisation.

- **Use cases**:

  - A **sales manager** shares a dashboard with the regional sales team.

  - An **executive** subscribes to a weekly email of the KPI dashboard.

  - A **data analyst** shares a view with a colleague for collaboration.


---

### Step‑by‑Step Demonstration

**Sharing a Workbook via Project Permissions**:

1. In Tableau Server/Cloud, navigate to the project containing the workbook.

2. Click **Share** on the project.

3. Add users or groups.

4. Set their permission level (Viewer, Explorer, etc.).

5. Click **Save**.


**Sharing a Specific View**:

1. Open the published workbook.

2. Navigate to the specific view or dashboard.

3. Copy the URL from the browser address bar.

4. Send the link to the recipient.


**Creating a Subscription**:

1. Open the published workbook.

2. Click the **Subscribe** button (envelope icon).

3. Choose the frequency (daily, weekly, monthly).

4. Select the time and format (PDF, image).

5. Click **Subscribe**.

---

### Practical Examples

- **Example 1**: A sales dashboard is shared with the entire sales team via project permissions. Each sales rep sees only their region (using row‑level security).

- **Example 2**: An executive subscribes to a daily email of the KPI dashboard, receiving a PDF every morning.

- **Example 3**: A data analyst shares a view link with a colleague for quick feedback.


---

### Hands‑on Exercises

1. Publish a workbook to Tableau Server/Cloud.

2. Share the project with a colleague (or test user) as a Viewer.

3. Share a specific view via a direct link.

4. Create a subscription to a dashboard.

5. Verify the recipient can access the content.


---

### Mini Quiz

1. What are the methods for sharing content in Tableau Server/Cloud?

2. What is a subscription?

3. How do you share a specific view via link?

4. What is the difference between Viewer and Explorer permissions?

5. What are Collections used for?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Sharing content without setting proper permissions – data exposure | Always review permissions before sharing |
| Using individual permissions instead of groups | Use groups for scalable permission management |
| Not using subscriptions – users manually check for updates | Encourage subscriptions for regular reports |
| Sharing without context – users don't know what they're looking at | Add a description to the workbook or view |

---

### Interview Questions

1. **How do you share a dashboard in Tableau Server?**  

   *Answer*: You can share via project permissions, direct sharing with users/groups, or by sending a direct link to a view. You can also set up subscriptions for scheduled email delivery.

2. **What is the difference between Viewer and Explorer permissions?**  

   *Answer*: Viewer can only view and interact with content. Explorer can also save custom views, create personal workbooks, and interact with data sources.

3. **How do you set up a subscription for a dashboard?**  

   *Answer*: Open the dashboard, click the Subscribe button, choose the frequency and format, and click Subscribe.

---

### Assignment and Dashboard Projects

**Assignment 7.4** – Share a dashboard with a colleague:

- Publish a workbook.

- Share the project or workbook with a colleague.

- Set up a subscription for yourself.

- Document the sharing process and any challenges.


---

### Summary and Revision Notes

- Sharing is done via project permissions, direct sharing, links, or subscriptions.

- Use groups for scalable permission management.

- Subscriptions send scheduled email updates.

- Always review permissions before sharing.


---

## Lesson 7.5 – User Roles and Permissions

### Concept Explanation

**User roles and permissions** in Tableau Server/Cloud determine what users can do – from viewing content to administering the entire server. Understanding this hierarchy is essential for secure and effective governance.

**Site Roles** (determine the maximum level of access):

| **Site Role** | **Capabilities** |
|---------------|------------------|
| **Server Administrator** | Full control over all sites and server settings. |
| **Site Administrator Creator** | Full admin control over a site, plus Creator capabilities. |
| **Site Administrator Explorer** | Full admin control over a site, plus Explorer capabilities. |
| **Creator** | Can publish workbooks and data sources, create extracts, and use Tableau Desktop and Prep. |
| **Explorer (Can Publish)** | Can publish workbooks and data sources. |
| **Explorer** | Can interact with published content, save custom views, but cannot publish. |
| **Viewer** | Can view and interact with content only. |
| **Unlicensed** | No access. |

**Content Permissions** (granular control over specific content):

- Permissions can be set at multiple levels: server, site, project, workbook, and view.

- Each level can have **Allow** or **Deny** rules.

- Permission capabilities include: View, Interact, Save, Download, Edit, Publish, Delete, Admin.

**Permission Hierarchy**:

- Server Administrator > Site Administrator > Project Leader > Workbook Owner > Viewer.

- Permissions are inherited from higher levels unless overridden.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Proper role and permission management ensures that users have exactly the access they need – no more, no less. This protects sensitive data and maintains governance.

- **Use cases**:

  - A **finance department** gives Viewers access to financial dashboards, Creators access to publish budget data.

  - A **data governance team** uses Site Administrators to manage sites for different business units.

  - A **project leader** manages permissions for their project, granting Interactor rights to team members.


---

### Step‑by‑Step Demonstration

**Assigning a Site Role to a User**:

1. In Tableau Server/Cloud, go to **Users**.

2. Find the user or add a new user.

3. In the **Site Role** dropdown, select the appropriate role.

4. Click **Save**.


**Setting Project Permissions**:

1. Navigate to the project.

2. Click **Share** or **Permissions**.

3. Add a user or group.

4. Set the permission level (Viewer, Explorer, Publisher, etc.).

5. Click **Save**.


**Setting Workbook‑Level Permissions**:

1. Open the workbook.

2. Click **Share**.

3. Add a user or group.

4. Set specific permissions (e.g., View only, no download).

---

### Practical Examples

- **Example 1**: A user with the **Creator** role publishes a new data source. A user with the **Explorer** role uses that data source to create a custom view. A **Viewer** only sees the final dashboard.

- **Example 2**: A project has a group of "Sales Managers" with Explorer permissions, and a group of "Sales Reps" with Viewer permissions. Reps can view dashboards; Managers can also save custom views.

---

### Hands‑on Exercises

1. In Tableau Server/Cloud, navigate to the Users section.

2. Identify the site roles of existing users.

3. Add a test user (or use an existing one) and assign a role.

4. Navigate to a project and set permissions for that user.

5. Verify the user's access.


---

### Mini Quiz

1. What are the site roles in Tableau Server/Cloud?

2. What is the difference between Creator and Explorer?

3. What is the difference between a Site Administrator and a Server Administrator?

4. How do you set permissions on a project?

5. What is the permission hierarchy in Tableau Server?


---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Giving everyone Creator or Admin permissions | Assign the minimum necessary role |
| Managing permissions per individual instead of groups | Use groups for scalable management |
| Not reviewing permissions regularly | Conduct regular permission audits |
| Denying permissions at lower levels without understanding inheritance | Understand that Deny overrides Allow |

---

### Interview Questions

1. **What are the site roles in Tableau Server?**  

   *Answer*: Server Administrator, Site Administrator Creator, Site Administrator Explorer, Creator, Explorer (Can Publish), Explorer, Viewer, and Unlicensed.

2. **What is the difference between Creator and Explorer roles?**  

   *Answer*: Creator can publish workbooks and data sources, create extracts, and use Tableau Desktop and Prep. Explorer can interact with published content and save custom views but cannot publish.

3. **How do you set permissions on a project?**  

   *Answer*: Navigate to the project, click Share or Permissions, add users or groups, and set their permission level.

---

### Assignment and Dashboard Projects

**Assignment 7.5** – Design a permission strategy for a hypothetical organisation:

- Define user roles (Creators, Explorers, Viewers).

- Define groups (e.g., Sales Team, Finance Team, HR Team).

- Map permissions to projects.

- Document the strategy.


---

### Summary and Revision Notes

- Site roles define the maximum level of access.

- Content permissions provide granular control.

- Use groups for scalable management.

- Permission hierarchy: Server Admin > Site Admin > Project > Workbook > View.


---

## Lesson 7.6 – Scheduling Extract Refreshes

### Concept Explanation

When you publish a workbook with an **extract** (a snapshot of data), the data can become stale. **Scheduled extract refreshes** automate the process of updating extracts with the latest data from the source.


**Refresh types**:

- **Full Refresh** – Reloads the entire extract.

- **Incremental Refresh** – Only loads new or changed data (faster and more efficient).


**Refresh frequency**:

- **Hourly, Daily, Weekly, Monthly**.

- Frequency limits depend on your licensing.

**Refresh options**:

- **Scheduled** – Runs automatically at set times.

- **Manual** – Triggered on‑demand.

- **Bridge Refresh** – For on‑premises data sources using Tableau Bridge.


**Setting up a schedule**:

1. After publishing, navigate to the data source or workbook.

2. Go to the **Refresh Schedules** tab.

3. Click **New Extract Refresh**.

4. Select the frequency and time.

5. Click **Create**.

---

### Importance and Real‑World Use Cases

- **Why it matters**: Without scheduled refreshes, dashboards show outdated data, eroding trust and reducing decision‑making effectiveness.

- **Use cases**:

  - A **daily sales dashboard** refreshes every morning at 6 AM.

  - A **monthly financial report** refreshes on the 1st of each month.

  - An **operational dashboard** refreshes every hour for near‑real‑time insights.


---

### Step‑by‑Step Demonstration

**Scheduling an Extract Refresh**:

1. In Tableau Server/Cloud, navigate to the published data source or workbook.

2. Click on the data source or workbook name.

3. Select the **Refresh Schedules** tab.

4. Click **New Extract Refresh**.

5. In the dialog:

   - Name the schedule.

   - Select the **Frequency** (Hourly, Daily, Weekly, Monthly).

   - Set the **Time** and **Days**.

   - Choose **Full** or **Incremental** refresh.

6. Click **Create**.


**Monitoring Refreshes**:

1. Navigate to the **Background Jobs** dashboard.

2. View the status of scheduled tasks.

3. Check for failures and resolve issues.

---

### Practical Examples

- **Example 1**: A sales dashboard uses an extract from a SQL Server database. A daily refresh at 6 AM ensures the sales team has fresh data each morning.

- **Example 2**: A financial dashboard uses an incremental refresh to load only new transactions, reducing refresh time from hours to minutes.

---

### Hands‑on Exercises

1. Publish a workbook with an extract.

2. Navigate to the published data source.

3. Create a new extract refresh schedule (daily at a specific time).

4. Verify the schedule is created.

5. Monitor the refresh (if possible).


---

### Mini Quiz

1. Why do you need to schedule extract refreshes?

2. What is the difference between a full and an incremental refresh?

3. How do you create a new extract refresh schedule?

4. What frequencies are available for extract refreshes?

5. Where can you monitor refresh performance?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not scheduling refreshes – data becomes stale | Always schedule refreshes for extracts |
| Scheduling too frequently – overloading the source | Match frequency to business needs |
| Not monitoring refreshes – failures go unnoticed | Regularly check the Background Jobs dashboard |
| Using full refreshes when incremental would be faster | Use incremental refreshes for large, growing datasets |

---

### Interview Questions

1. **How do you schedule an extract refresh in Tableau Server?**  

   *Answer*: Navigate to the data source or workbook, go to the Refresh Schedules tab, click New Extract Refresh, select the frequency and time, and create the schedule.

2. **What is the difference between a full and an incremental refresh?**  

   *Answer*: A full refresh reloads the entire extract. An incremental refresh only loads new or changed data, making it faster and more efficient.

3. **What is Tableau Bridge used for?**  

   *Answer*: Tableau Bridge enables extract refreshes for on‑premises data sources that cannot be accessed directly from Tableau Cloud.

---

### Assignment and Dashboard Projects

**Assignment 7.6** – Set up a scheduled extract refresh:

- Publish a workbook with an extract.

- Create a daily refresh schedule.

- Monitor the first refresh.

- Document the process.


---

### Summary and Revision Notes

- Scheduled refreshes keep extracts up‑to‑date.

- Full refresh vs Incremental refresh.

- Frequencies: hourly, daily, weekly, monthly.

- Monitor refreshes via the Background Jobs dashboard.

---

## Lesson 7.7 – Collaboration Features

### Concept Explanation

Tableau Server and Cloud provide a range of **collaboration features** that enable teams to work together, share insights, and communicate around data.

**Key collaboration features**:

1. **Comments** – Add comments to views, dashboards, or data sources for discussion.

2. **Subscriptions** – Schedule email delivery of dashboards and views.

3. **Alerts** – Get notified when data meets certain conditions.

4. **Favorites** – Bookmark important content for quick access.

5. **Collections** – Curate groups of related content.

6. **Sharing** – Share content with users or groups.

7. **Web Authoring** – Edit workbooks directly in the browser (Explorer and Creator roles).

8. **Tableau Agent** – Ask questions in plain language and get insights (AI‑powered).


**Using Comments**:


1. Open a published view or dashboard.

2. Click the **Comments** icon (speech bubble).

3. Type your comment and click **Post**.

4. Other users can reply and discuss.


**Setting Up Alerts**:

1. Open a published view.

2. Right‑click on a data point → **Create Alert**.

3. Set the condition (e.g., Sales > 1000).

4. Choose the frequency and recipients.

5. Click **Create**.


---

### Importance and Real‑World Use Cases

- **Why it matters**: Collaboration turns dashboards from static reports into dynamic conversations. Teams can ask questions, share insights, and make decisions together.

- **Use cases**:

  - A **sales team** uses comments to discuss weekly performance on the sales dashboard.
  
  - A **finance team** sets up alerts for budget overruns.
  
  - A **marketing team** uses collections to organise campaign dashboards.
  

---

### Step‑by‑Step Demonstration

**Adding a Comment**:

1. Open a published workbook.

2. Navigate to a view.

3. Click the **Comments** icon.

4. Type "Great insight on the West region performance!".

5. Click **Post**.


**Creating an Alert**:

1. Open a view with a data point.

2. Right‑click on a bar or data point.

3. Select **Create Alert**.

4. Set the condition: `SUM(Sales) > 10000`.

5. Set the frequency: **Once** or **On‑going**.

6. Click **Create**.


**Creating a Collection**:

1. In Tableau Server/Cloud, go to **Collections**.

2. Click **New Collection**.

3. Name it "Monthly Sales Reports".

4. Add content by searching or browsing.

5. Share the collection with others.

---

### Practical Examples

- **Example 1**: A data analyst posts a comment on a dashboard asking for clarification on a data point. The business user replies with context, resolving the question without a meeting.

- **Example 2**: A supply chain manager sets an alert for inventory levels dropping below a threshold. When triggered, they receive an email and can take action.

---

### Hands‑on Exercises

1. Publish a workbook.

2. Add a comment to a view.

3. Reply to your own comment.

4. Set up an alert on a data point.

5. Create a collection and add content to it.


---

### Mini Quiz

1. What collaboration features are available in Tableau Server/Cloud?

2. How do you add a comment to a view?

3. How do you create an alert?

4. What is a collection?

5. What is Tableau Agent used for?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Not using comments – missing out on discussion | Encourage teams to use comments for context |
| Setting too many alerts – notification overload | Set alerts only for critical thresholds |
| Not organising content with collections | Use collections to curate related content |
| Ignoring Tableau Agent capabilities | Leverage AI for self‑service insights |

---

### Interview Questions

1. **What collaboration features does Tableau Server offer?**  

   *Answer*: Comments, subscriptions, alerts, favorites, collections, sharing, web authoring, and Tableau Agent for AI‑powered insights.

2. **How do you set up an alert in Tableau Server?**  

   *Answer*: Open a view, right‑click on a data point, select Create Alert, set the condition and frequency, and click Create.

3. **What is a collection in Tableau Server?**  

   *Answer*: A collection is a curated group of related content (workbooks, views, data sources) that can be shared with others.

---

### Assignment and Dashboard Projects

**Assignment 7.7** – Demonstrate collaboration features:

- Publish a workbook.

- Add a comment to a view.

- Set up an alert.

- Create a collection.

- Document the process.


---

### Summary and Revision Notes

- Collaboration features: comments, subscriptions, alerts, favorites, collections.

- Comments enable discussion around data.

- Alerts notify users when conditions are met.

- Collections curate related content.

---

## Lesson 7.8 – Governance Best Practices

### Concept Explanation

**Governance** in Tableau is the framework of roles, policies, standards, and processes that ensure secure, consistent, scalable analytics across your organisation. Good governance balances control with agility.

**Key governance components**:

1. **User and Group Management** – Use groups for permission management, not individuals.

2. **Content Lifecycle** – Define processes for creating, reviewing, publishing, and retiring content.

3. **Data Governance** – Ensure data quality, lineage, and security (using Tableau Catalog).

4. **Security** – Implement row‑level security, site isolation for multi‑tenancy, and regular permission audits.

5. **Performance** – Monitor server performance and optimise queries.

6. **Training and Documentation** – Provide resources for users and administrators.


**Best Practices**:

| **Area** | **Best Practice** |
|----------|-------------------|
| **Permissions** | Use Active Directory (AD) groups for permissions, never individuals |
| **Projects** | Create a logical folder structure with clear naming conventions |
| **Data Sources** | Publish data sources separately for reuse and centralised management |
| **Refreshes** | Schedule refreshes during off‑peak hours; use incremental refreshes |
| **Monitoring** | Use the Background Jobs and Performance dashboards |
| **Lifecycle** | Regularly review and archive or delete unused content |
| **Security** | Implement row‑level security; restrict admin access |

---

### Importance and Real‑World Use Cases

- **Why it matters**: Without governance, Tableau environments devolve into chaos – data sprawl, security exposure, and untrusted insights. Governance ensures that analytics are reliable, secure, and scalable.

- **Use cases**:

  - A **large enterprise** establishes a Center of Excellence to govern Tableau usage.

  - A **financial services firm** uses Tableau Catalog for data lineage and compliance.

  - A **government agency** uses site isolation for multi‑tenant deployments.


---

### Step‑by‑Step Demonstration

**Setting Up a Governance Framework**:

1. **Define Roles** – Identify who will be Creators, Explorers, and Viewers.

2. **Create Groups** – Use Active Directory groups for permissions.

3. **Establish Projects** – Create projects for each department or business unit.

4. **Set Naming Conventions** – Define standards for projects, workbooks, and data sources.

5. **Implement Data Governance** – Use Tableau Catalog for lineage and certification.

6. **Monitor Usage** – Use the Admin dashboard to track usage and performance.


**Creating a Project Structure**:

1. In Tableau Server/Cloud, create a top‑level project for each department.

2. Within each department project, create sub‑projects for different functions.

3. Set permissions at the project level.


**Using Tableau Catalog**:
1. Enable Tableau Catalog (available with Data Management).

2. View data lineage for any data source.

3. Certify trusted data sources.

---

### Practical Examples

- **Example 1**: A company uses AD groups for permissions. The "Finance - Viewer" group has Viewer access to the Finance project. New finance employees are added to the AD group and automatically get access.

- **Example 2**: A data governance team uses Tableau Catalog to track data lineage. When a data source changes, they can see which dashboards will be affected.

---

### Hands‑on Exercises

1. Review the governance practices in your organisation (or a hypothetical one).

2. Define a project structure with at least three departments.

3. Create a naming convention for projects, workbooks, and data sources.

4. Document the governance framework.


---

### Mini Quiz

1. What is governance in the context of Tableau?

2. Why should you use groups instead of individuals for permissions?

3. What is Tableau Catalog used for?

4. What is the purpose of a naming convention?

5. Why is monitoring important for governance?

---

### Common Mistakes and Best Practices

| **Common Mistakes** | **Best Practices** |
|----------------------|---------------------|
| Managing permissions per individual – unmanageable at scale | Use Active Directory groups for permissions |
| No naming conventions – content is unsearchable | Establish clear naming conventions |
| No content lifecycle – outdated content proliferates | Define processes for creating, reviewing, and retiring content |
| Ignoring data lineage – trust is eroded | Use Tableau Catalog for data lineage |
| Not monitoring usage – blind to adoption issues | Regularly review usage and performance metrics |

---

### Interview Questions

1. **What are the key elements of a Tableau governance framework?**  

   *Answer*: User and group management, content lifecycle, data governance (lineage, quality), security, performance monitoring, and training.

2. **Why should you use Active Directory groups for permissions?**  

   *Answer*: Groups are scalable and manageable. When a user joins or leaves a team, they are added or removed from the group, automatically updating their access.

3. **What is Tableau Catalog and why is it important?**  

   *Answer*: Tableau Catalog provides data lineage and governance capabilities, helping organisations track data sources, understand dependencies, and certify trusted data.

---

### Assignment and Dashboard Projects

**Assignment 7.8** – Create a governance framework for a hypothetical organisation:

- Define roles and responsibilities.

- Create a project structure.

- Establish naming conventions.

- Define content lifecycle processes.

- Document the framework.


---

### Summary and Revision Notes

- Governance ensures secure, consistent, scalable analytics.

- Use groups for permissions, not individuals.

- Use Tableau Catalog for data lineage.

- Establish naming conventions and content lifecycle.

- Monitor usage and performance regularly.

---

## Final Phase 7 Assessment

Now that you have completed all lessons, test your overall understanding.

### Self‑Evaluation Checklist

-  I can explain the difference between Tableau Server and Tableau Cloud.

-  I understand the licensing and editions of Tableau Cloud.

-  I can publish workbooks and data sources.

-  I can share dashboards via project permissions, links, and subscriptions.

-  I understand user site roles and content permissions.

-  I can schedule extract refreshes.

-  I can use collaboration features (comments, alerts, collections).

-  I understand governance best practices.


If you have completed all assignments and feel confident, you have achieved **Expert** level in Tableau!

---

### Answers to Mini Quizzes

**Lesson 7.1**: 1. Self‑hosted enterprise analytics platform. 2. Server is self‑hosted; Desktop is authoring tool. 3. On‑premises or in the cloud (IaaS). 4. Data lineage and governance. 5. It has evolved into a data hub with AI capabilities.

**Lesson 7.2**: 1. SaaS version of Tableau Server. 2. Cloud is fully hosted; Server is self‑hosted. 3. Standard, Enterprise, Cloud+. 4. Viewer ($15), Explorer ($42), Creator ($75). 5. Faster setup, no infrastructure management.

**Lesson 7.3**: 1. Server → Publish Workbook. 2. Embedded = within workbook; Separate = reusable. 3. Project, name, data source, refresh schedule. 4. Data pane → Save As Published Data Source. 5. In the project.

**Lesson 7.4**: 1. Project permissions, direct sharing, links, subscriptions, collections. 2. Scheduled email delivery of dashboards. 3. Copy the URL from the browser. 4. Viewer = view only; Explorer = view + custom views. 5. Curating groups of content.

**Lesson 7.5**: 1. Server Admin, Site Admin Creator/Explorer, Creator, Explorer (Can Publish), Explorer, Viewer, Unlicensed. 2. Creator can publish; Explorer cannot. 3. Site Admin manages a site; Server Admin manages all sites. 4. Navigate to project → Share → add users/groups. 5. Server > Site > Project > Workbook > View.

**Lesson 7.6**: 1. To keep extracts up‑to‑date. 2. Full = reload all; Incremental = only new/changed data. 3. Navigate to data source → Refresh Schedules → New Extract Refresh. 4. Hourly, daily, weekly, monthly. 5. Background Jobs dashboard.

**Lesson 7.7**: 1. Comments, subscriptions, alerts, favorites, collections, sharing, web authoring, Tableau Agent. 2. Click Comments icon → type → Post. 3. Right‑click data point → Create Alert. 4. Curated group of content. 5. AI‑powered natural language queries.

**Lesson 7.8**: 1. Framework for secure, consistent analytics. 2. Groups are scalable; individuals are not. 3. Data lineage and governance. 4. To make content searchable and organised. 5. To ensure performance and identify issues.

---

**Congratulations!** You have completed all seven phases of this comprehensive Tableau curriculum. You are now a full‑stack Tableau professional, capable of:
- Connecting to and preparing any data source.
- Building sophisticated data models and calculations.
- Creating stunning, interactive visualisations.
- Designing professional, interactive dashboards.
- Deploying, sharing, and governing content on Tableau Server and Cloud.

Remember that Tableau is constantly evolving, so keep learning through the Tableau community, blogs, and official documentation. The best way to maintain your skills is to keep building dashboards and solving real‑world problems.

Good luck on your Tableau journey!


---











<br/><br/><br/>
<center> <b>Happy Learning! 😊</b> </center>