# Power BI Exam PL-300 (Microsoft Power BI Data Analyst) - Study Guide

## Intro:
This guide includes the exam topics and each section with links to refer further from Microsoft documentation. In addition, I included my notes for each topic as quick reference wherever required. The original content is from [Awesome Power BI](https://github.com/NajiElKotob/Awesome-Power-BI) and thanks to the team. 

- **Updated By** : 03/03/2024 by [Akbarsait](https://github.com/Akbarsait)

## [Skills at a glance](https://learn.microsoft.com/en-ca/credentials/certifications/resources/study-guides/pl-300)
- [Prepare the data (25–30%)](#prepare-the-data-25-30)
- [Model the data (25–30%)](#model-the-data-25-30)
- [Visualize and analyze the data (25–30%)](#visualize-the-data-25-30)
- [Deploy and maintain items (15–20%)](#deploy-and-maintain-deliverables-10-15)

## Prepare the data (25-30%)

##### Get data from different data sources
* Identify and connect to a data source
  * [Connect to data sources in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-connect-to-data)
  * [SharePoint Folder](https://docs.microsoft.com/en-us/power-query/connectors/sharepointfolder)
* Change data source settings
  * [Manage data sources](https://docs.microsoft.com/en-us/power-bi/connect-data/service-gateway-data-sources)
* Select a shared dataset or create a local dataset
  * [Connect to datasets in the Power BI service from Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-report-lifecycle-datasets) 
* [Select a storage mode](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-storage-mode)
  * **Import** : Source data is stored locally in PowerBI memory (otherwise known as cache)
  * **DirectQuery** : Data stays at source, such as the SQL databases, and is queried when needed. 
  * **Dual** : Dual mode essentially operates as a combination of Import and DirectQuery
  * From Model View > Select the Table or data > Properties > Advance > Storage Mode
* Choose an appropriate query type
  * [Perform common query tasks in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-common-query-tasks)
* Identify query performance issues
  * [Troubleshoot report performance in Power BI](https://docs.microsoft.com/en-us/power-bi/guidance/report-performance-troubleshoot)
* [Use Microsoft Dataverse](https://docs.microsoft.com/en-us/powerapps/maker/data-platform/data-platform-powerbi-connector) - Create a Power BI report using data from Dataverse
  * Common Data Service has been renamed to Microsoft Dataverse
* [Use parameters](https://docs.microsoft.com/en-us/power-query/power-query-query-parameters)
* Use or create a PBIDS file
  * [Using PBIDS files to get data](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-data-sources#using-pbids-files-to-get-data)
* [Use or create a data flow](https://docs.microsoft.com/en-us/power-bi/transform-model/dataflows/dataflows-create)
* Connect to a dataset using the XMLA endpoint
  * [Dataset connectivity with the XMLA endpoint](https://docs.microsoft.com/en-us/power-bi/admin/service-premium-connect-tools) 

##### Profile the data
* Identify data anomalies
  * [Column profile](https://docs.microsoft.com/en-us/power-query/data-profiling-tools#column-profile) 
* Examine data structures
  * [Data types in Power Query](https://docs.microsoft.com/en-us/power-query/data-types) 
  * [Column distribution](https://docs.microsoft.com/en-us/power-query/data-profiling-tools#column-distribution) 
* Interrogate column properties
  * [Column quality](https://docs.microsoft.com/en-us/power-query/data-profiling-tools#column-quality) 
* Interrogate data statistics
  * [Column profile](https://docs.microsoft.com/en-us/power-query/data-profiling-tools#column-profile) 
  * [Create a Profiling Report in Power BI: Give the End User Information about the Data](https://radacad.com/create-a-profiling-report-in-power-bi-give-the-end-user-information-about-the-data) - radacad.com


##### Clean, transform, and load the data
* Resolve inconsistencies, unexpected or null values, and data quality issues
  * [Profile data in Power BI](https://docs.microsoft.com/en-us/learn/modules/clean-data-power-bi/6-profile-data) 
    * Helps identify data issues & anomolies. 
    * Detection based on first 1000 rows by default. 
    * Three Profiling Options: 
      * Column Distribution - Column distribution shows, on the top, the distinct and duplicate values for each column.
      * Column Quality - Column quality focuses on the valid, null, and error values for each column.
      * Column Profile(represents a large area at the bottom): Although the Column profile does show unique and distinct values, it does so at the bottom of the page and occupies a larger portion of the screen.
    * The M Language 
      * Mash-up language for ETL, often one step/line, immediate result set, Easy language to develop. M allows you to return to a previous step and compare how the data looked before the transformation.
    * Loading the Data
      * Data Source to Power Query
      * Power Query to Power BI
      * Query: A Query is a set of all steps used to extract, transform, and load data into Power BI.
  * Data Transformation
    * Remove rows or Remove other rows can be done by multiple ways
    * Replace a error value with a corrected value using replace value in a coloumn. 
    * Remove blank values allows to remove all the blank values in a column. 
    * Date/time can be splitted into two columns from a single column using Split column fuctionality. Also allows you to specify how to split it by delims. 
    * Change date type using Date in Transform tab. 
    * Add a custom column with calculated values using two other columns in the table. 
    * Trim removes blank spaces on values, therefore working on a cell level.
    * Demote headers : Although Promoting headers is a far more common operation, in this case, demoting the headers will make sure you're not losing the data from the first record.
  * Manupulating Queries & Tables on Power Query
    * Append Queries: Append two or more queries into one. Append as New or Append Query
    * Merge Queries: Using Home > Merge or Merge New Query options. Allows to join two tables and build result. 
    * Duplicate Queries & Aggreate Results: Right click and Duplicate. Apply Group by/Count with new query. 
    * Apply Pivot for one row mulitple columns queries and using data types to proper values. 
    * What's the best data modeling technique for reporting? 
      * When creating reports, a star schema is almost always the best compromise between normalization and denormalization.
    * You have three queries performing the exact same steps. You want to minimize the amount of transformations processed by Power BI for these queries. What's the best option?
      * Create a dataflow: will allow Power BI to consolidate the transformations into one batch. You can then create three different queries from the same dataflow and add additional transformations to them independently if needed.
 
* Apply user-friendly value replacements
  * [Simplify the data structure](https://docs.microsoft.com/en-us/learn/modules/clean-data-power-bi/3-data-structure)
* Identify and create appropriate keys for joins
  * [Seven Types of Table Joins](https://www.powerbi-pro.com/en/power-bi-seven-types-of-table-joins/) - powerbi-pro.com
* Evaluate and transform column data types
  * [Data types in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-data-types) 
  * [Evaluate and change column data types](https://docs.microsoft.com/en-us/learn/modules/clean-data-power-bi/4-column-data-types)
* Apply data shape transformations to table structures
  * [Combine multiple tables into a single table](https://docs.microsoft.com/en-us/learn/modules/clean-data-power-bi/5-combine-tables) 
  * [Shape and combine data in Power BI Desktop (Tutorial)](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-shape-and-combine-data)
* Combine queries
  * [Combine queries](https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-shape-and-combine-data#combine-queries) - Tutorial: Shape and combine data in Power BI Desktop
* Apply user-friendly naming conventions to columns and queries
* Leverage Advanced Editor to modify Power Query M code
* Configure data loading
* Resolve data import errors
  * [Viewing Error Messages For All Rows In Power Query](https://blog.crossjoin.co.uk/2014/12/22/viewing-error-messages-for-all-rows-in-power-query/) - Chris Webb's BI Blog

## Model the data (25-30%)

#### Design a data model
* Define the tables
* Configure table and column properties
  * In the Model view by clicking properties, we can define a Key column to a table. 
  * Disable load: Keeps the data in Power Query but not load into Power BI. 
  * Hiding by enabling Is Hidden from Properties: Loads into Power BI but will be unavailable for reporting. The data/table will be available in the Model but not on the Report view. 
  * Data Category: In the table view, using the Column tools, we can define Data category of a column depend on it's type.  
* Define quick measures
  * [Use quick measures for common calculations](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-quick-measures) 
* Flatten out a parent-child hierarchy
* Define role-playing dimensions
  *  [Understand star schema and the importance for Power BI](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema#role-playing-dimensions)
  *  Star Schema uses Fact and Dimension tables. 
  *  Fact Tables: 
     *  What happened, Many sides of relationship, Quantitative date (numbers), Aggregate facts, vertical focus
  * Dimension Tables:
    * Details of what happened, One side of relationship, Qualitative date, Filter by dimensions, horizontal focus. 
* Define a relationship's cardinality and cross-filter direction
  * [Model relationships in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-relationships-understand) 
* Design the data model to meet performance requirements
  * [Best practice rules to improve your model’s performance](https://powerbi.microsoft.com/en-us/blog/best-practice-rules-to-improve-your-models-performance/) 
* Resolve many-to-many relationships
* Create a common date table
  * [Create date tables in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/guidance/model-date-tables) 
* Define the appropriate level of data granularity
* Apply or change sensitivity labels
  * [Enable sensitivity labels in Power BI](https://docs.microsoft.com/en-us/power-bi/admin/service-security-enable-data-sensitivity-labels)

* Quick Questions:
  *  What happen to  model size and performance when we increase the granularity of your report from monthly to daily. 
     *  IT will increase on model size, and a decrease in performance. All things being equal, it's likely that this will increase your model size, and potentially impact performance.
  * You are creating an analytical reporting solution on Power BI. The Product dimension will be frequently updated, and you want to minimize the size and maintain impact for it. How should you design this model?
    * Create a star schema for most dimensions, but further normalize the Product dimension. Although the recommended approach for Power BI is a star schema, on some situations your business needs might require some flexibility.
  * What kind of model is a popular way to import data, frequently used on formats such as TXT or CSV?
    * Flat Models: Flat files might not be the best format for reporting, but are a quite popular way to import and export data.
  * How to make a column exists on the data model, but unavailable on the report view. Which option should you use?
    * Is Hidden: Is hidden allows a column to be loaded on the data model, but hidden on the report view.
  * You are creating a report based on a database, which stores dates on a datetime format. You want to report based on the day of the month. What's the best option to treat the date fields, if you want to balance performance, model size, and granularity?
    * Change the data type to date only: If you never report based on time, you can safely remove the time portion, which might considerably improve the storage of dates.
 
#### Develop a data model
* Apply cross-filter direction and security filtering
  * [Cross filter direction](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-relationships-understand#cross-filter-direction)
* Create calculated tables
  * [Create calculated tables in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-calculated-tables) 
* Create hierarchies
* Create calculated columns
  * [Create calculated columns in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-calculated-columns) 
* Implement row-level security roles
  * [Row-level security (RLS) with Power BI](https://docs.microsoft.com/en-us/power-bi/admin/service-admin-rls) 
* Implement object-level security
* Set up the Q&A feature

#### Create measures by using DAX
* Use DAX to build complex measures
  * [Data Analysis Expressions (DAX) Reference](https://docs.microsoft.com/en-us/dax/) 
* Use CALCULATE to manipulate filters
  * [CALCULATE](https://docs.microsoft.com/en-us/dax/calculate-function-dax) 
  * [How CALCULATE works in DAX](https://www.sqlbi.com/blog/marco/2010/01/03/how-calculate-works-in-dax/) - sqlbi.com
  * [CALCULATE](https://dax.guide/calculate/) - dax.guide
* Implement Time Intelligence using DAX
  * [DATEADD](https://dax.guide/dateadd/) - dax.guide
  * [DATEQTD](https://dax.guide/datesqtd/) - dax.guide
  * [LASTDATE](https://dax.guide/lastdate/) - dax.guide
  * [SAMEPERIODLASTYEAR](https://dax.guide/sameperiodlastyear/) - dax.guide
* Replace numeric columns with measures
  * [Calculated Columns and Measures in DAX](https://www.sqlbi.com/articles/calculated-columns-and-measures-in-dax/) - sqlbi.com
* Use basic statistical functions to enhance data
  * [MEDIAN](https://dax.guide/median/) - dax.guide
  * [RANKX](https://dax.guide/rankx/) - dax.guide
  * [TOPN](https://dax.guide/topn/) - dax.guide 
* Create semi-additive measures
  * [Semi-Additive Measures in DAX](https://www.sqlbi.com/articles/semi-additive-measures-in-dax/) - sqlbi.com

#### Optimize model performance
* Remove unnecessary rows and columns
  * [Choose or remove columns](https://docs.microsoft.com/en-us/power-query/choose-remove-columns)
    * Horizontal Cleaning : Can remove duplicate rows by right click on the row > Remove duplicate rows in the Power Query. 
    * Vertical Cleaning : Select the column to remove and click remove by right clicking it. 
  
* Identify poorly performing measures, relationships, and visuals
  * [Use Performance Analyzer to examine report element performance](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-performance-analyzer) 
* Improve cardinality levels by changing data types
  * [Data types in Power Query](https://docs.microsoft.com/en-us/power-query/data-types) 
* Improve cardinality levels through summarization
* Create and manage aggregations
  * [Grouping or summarizing rows](https://docs.microsoft.com/en-us/power-query/group-by) 
* Use Query Diagnostics


## Visualize the data (25-30%)

#### Create Report
* Add visualization items to reports
* Choose an appropriate visualization type
* Format and configure visualizations
* Import a custom visual
* Configure conditional formatting
* Configure small multiples
* Apply slicing and filtering
  * [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-interactions) * Add an R or Python visual
* Add an R or Python visual
* Add a Smart Narrative visual
* Configure the report page
* Design and configure for accessibility
  * [Design Power BI reports for accessibility](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-accessibility-creating-reports) 
* Configure automatic page refresh
* Create a paginated report
  * [What are paginated reports in Power BI Premium?](https://docs.microsoft.com/en-us/power-bi/paginated-reports/paginated-reports-report-builder-power-bi)
* Create a PivotTable from a Power BI dataset in Excel

#### Create dashboards
* Set mobile view
  * [Optimize Power BI reports for the mobile app](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-create-phone-report) 
* Manage tiles on a dashboard
  * [Intro to dashboard tiles for Power BI designers](https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-tiles)
  * [Pin a tile to a Power BI dashboard from a report](https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-pin-tile-from-report)
  * [Pin a tile from one dashboard to another dashboard](https://docs.microsoft.com/en-us/power-bi/create-reports/service-pin-tile-to-another-dashboard)
  * [Add images, videos, and more to your dashboard](https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-add-widget)
* Configure data alerts
  * [Data alerts in the Power BI service](https://docs.microsoft.com/en-us/power-bi/create-reports/service-set-data-alerts) 
* Use the Q&A feature
  * [Tips for asking questions in Power BI Q&A](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-q-and-a-tips)  
* Add a dashboard theme
  * [Use dashboard themes in the Power BI service](https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-themes) 
* Pin a live report page to a dashboard
  * [Pin an entire report page, as a live tile, to a Power BI dashboard](https://docs.microsoft.com/en-us/power-bi/create-reports/service-dashboard-pin-live-tile-from-report) 


#### Enrich reports for usability
* Configure bookmarks
* Create custom tooltips
* Edit and configure interactions between visuals
* Configure navigation for a report
* Apply sorting
* Configure Sync Slicers
* Use the selection pane
* Use drillthrough and cross filter
* Drilldown into data using interactive visuals
* Export report data
* Design reports for mobile devices


## Analyze the data (15-20%)

#### Enhance reports to expose insights
* Apply conditional formatting
* Apply slicers and filters
* Perform top N analysis
  * [How to Create Power BI TOP N Report (Variable TOP N Filter)](https://www.youtube.com/watch?v=wKfPS1yZfE0) - Avi Singh
* Explore statistical summary
  * [Explore statistical summary](https://docs.microsoft.com/en-us/learn/modules/perform-analytics-power-bi/2-statistical-summary) 
  * [Create a Profiling Report in Power BI](https://radacad.com/create-a-profiling-report-in-power-bi-give-the-end-user-information-about-the-data) - radacad.com
* Use the Q&A visual
  * [Create a Q&A visual in Power BI](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-q-and-a) 
* Add a Quick Insights result to a report
  * [Generate data insights on your dataset automatically with Power BI](https://docs.microsoft.com/en-us/power-bi/create-reports/service-insights) 
* Create reference lines by using Analytics pane
  * [Use the Analytics pane in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-analytics-pane) 
* Use the Play Axis feature of a visualization
  * [Scatter charts, bubble charts, and dot plot charts in Power BI](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-scatter) 
* Personalize visuals
  * [Let users personalize visuals in a report](https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-personalize-visuals) 

#### Perform advanced analysis
* Identify outliers
  * [Detecting & Showcasing Outlier Results In Power BI](https://blog.enterprisedna.co/outlier-detection-and-visualization-in-power-bi-advanced-dax/) - enterprisedna.co
* Conduct Time Series analysis
  * [How Forecasting in Power BI Works](https://spreadsheeto.com/power-bi-forecasting/) - spreadsheeto.com
* Use anomaly detection
  * [Anomaly detection](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-anomaly-detection) 
* Use groupings and binnings
  * [Use grouping and binning in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-grouping-and-binning) 
* Use the Key Influencers to explore dimensional variances
  * [Create key influencers visualizations](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers) 
* Use the decomposition tree visual to break down a measure
  * [Create and view decomposition tree visuals in Power BI](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-decomposition-tree) 
* Apply AI Insights
  * [Use AI Insights in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-ai-insights) 

## Deploy and maintain deliverables (10-15%)

#### Manage datasets
* Configure a dataset scheduled refresh
  * [Data refresh in Power BI](https://docs.microsoft.com/en-us/power-bi/connect-data/refresh-data) 
* Configure row-level security group membership
  * [Row-level security (RLS) with Power BI](https://docs.microsoft.com/en-us/power-bi/admin/service-admin-rls) 
* Provide access to datasets
* Configure incremental refresh settings
  * [Incremental refresh for datasets](https://docs.microsoft.com/en-us/power-bi/connect-data/incremental-refresh-overview) 
* Promote or certify Power BI datasets
  * [Endorse your content](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-endorse-content) 
* Identify downstream dataset dependencies
  * [Identifying shared datasets](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-dataset-impact-analysis#identifying-shared-datasets) 
* Configure large dataset format


#### Create and manage workspaces
* Create and configure a workspace
  * [Create the new workspaces in Power BI](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-create-the-new-workspaces) 
* Recommend a development lifecycle strategy
* Assign workspace roles
  * [Roles in the new workspaces](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-new-workspaces#roles-in-the-new-workspaces) 
  * [Organize work in the new workspaces in Power BI](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-new-workspaces)
* Configure and update a workspace app
  * [Publish an app in Power BI](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-create-distribute-apps) 
* Publish, import, or update assets in a workspace
* Apply sensitivity labels to workspace content
  * [How to apply sensitivity labels in Power BI](https://docs.microsoft.com/en-us/power-bi/admin/service-security-apply-data-sensitivity-labels) 
* Use deployment pipelines
  * [Get started with deployment pipelines](https://docs.microsoft.com/en-us/power-bi/create-reports/deployment-pipelines-get-started?tabs=datasets) 
* Configure subscriptions
  *  [Subscribe others to your reports and dashboards in the Power BI service](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-report-subscribe)
* Promote or certify Power BI content
  * [Endorsement - Promoting and certifying Power BI content](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-endorsement-overview)

-----