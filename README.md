# Data Analysis Excel BI: Power Query, DAX, and Coffee Shop Dashboard

https://github.com/moosatae123/Data-Analysis-Excel-Power-Query-DAX-Power-Pivot-Coffee-Shop/releases

[![Releases](https://img.shields.io/badge/releases-downloads-blue?logo=github&logoColor=white)](https://github.com/moosatae123/Data-Analysis-Excel-Power-Query-DAX-Power-Pivot-Coffee-Shop/releases)

![Coffee Dashboard Hero](https://images.unsplash.com/photo-1526312426766-12c1a5f2b5be?auto=format&fit=crop&w=1350&q=80)

Welcome to a practical, end-to-end business intelligence project built in Excel. This repository demonstrates how to combine Power Query, Power Pivot (DAX), and Excel dashboarding to create a dynamic sales performance view for a multi-store coffee chain. The workflow starts with raw data from an ERP system and ends with an interactive, visually compelling dashboard that supports decision-making across stores, products, and time periods. The project is designed to be approachable for analysts who want to level up their Excel BI skills while keeping a tightly scoped, reproducible workflow.

Key topics covered in this project include advanced data shaping with Power Query, data modeling with Power Pivot, DAX measures for financial analysis, and dashboarding best practices in Excel. The deliverable is a fully documented workbook plus a reproducible data model and references that show how to extend the solution to other retail chains or product lines.

Overview at a glance
- Domain: retail analytics for a coffee shop chain with multiple stores
- Core tools: Power Query, Power Pivot (DAX), and Excel dashboards
- Data sources: ERP exports, POS feeds, and periodic forecasting inputs
- Output: an interactive dashboard that surfaces sales, margins, performance by store, product category, and time
- Target users: BI analysts, store managers, regional leaders, and financial analysts who rely on Excel for reporting

Why this project exists
- The goal is practical learning through a real-world scenario. You can reproduce the data flow from raw ERP exports to a polished Excel-based dashboard.
- The design emphasizes transparency and reproducibility. Each step—data ingestion, transformation, modeling, and visualization—has clear documentation.
- You gain a template for similar BI tasks. The patterns used here apply to other product lines, channels, or geographic regions with minimal adaptation.

Repo structure and what you’ll find
- Data ingestion: Power Query queries that clean and shape ERP exports into a consistent data model
- Data modeling: a star schema-like structure with fact tables (sales) and dimension tables (store, product, time)
- Calculations: DAX measures for key metrics such as sales, margin, and velocity
- Dashboards: Excel-based visuals, slicers, and interactive charts designed for quick analysis
- Documentation: inline notes inside the workbook and this README with setup steps, design decisions, and extension ideas

Getting started: what you need
- An installed copy of Microsoft Excel that supports Power Query and Power Pivot features (Excel 2016 and newer, or Office 365 ProPlus/Business editions typically work well)
- Access to the release package from the repository Releases page
- A willingness to adapt the model to your own ERP data schema, store structure, and product catalog

Key features you’ll learn
- End-to-end data workflow: from raw ERP-like exports to a clean data model
- Data shaping with Power Query: filtering, merging, pivoting, and enriching datasets
- Data modeling in Excel: creating relationships between stores, products, time, and sales facts
- DAX basics and best practices: efficient measures for recurring analytic needs
- Interactive dashboards: slicers, drill-downs, and responsive visuals in Excel
- Documentation discipline: how to capture decisions, data quality checks, and validation steps

Topics and terminology you’ll encounter
- Advanced Excel and BI concepts
- Data modeling and DAX language
- Power Query transformations and M language
- Excel dashboards and visualization design
- Financial analysis patterns like margins, gross profit, and velocity
- Multi-store retail analytics and store-level performance

Releases and how to obtain the workbook
- The repository host provides a Releases page where you can download the release package. This page is the source of the ready-to-run workbook and any supporting assets.
- From the Releases page, download the release package and execute the included workbook to reproduce the dashboard locally.
- If you encounter issues with the link or the page, check the Releases section for alternative download options or updated artifacts.

Releases link for quick access
- Primary access: https://github.com/moosatae123/Data-Analysis-Excel-Power-Query-DAX-Power-Pivot-Coffee-Shop/releases
- Quick navigation tip: the Releases page hosts the bundled workbook and any related data schemas. The file you need to download will be part of a packaged release.

Note: This repository uses the Releases page to host downloadable artifacts. If the link changes or the page does not load, search the repository for the latest release notes and download the package from the Releases section.

How to use this repository effectively
- Step 1: Inspect the workbook structure
  - Open the Excel file and inspect the workbook tabs. You’ll see a data model section, a set of Power Query queries in the Queries pane, and a dashboard sheet with interactive visuals.
  - Review the data model relationships to understand how the stores, products, time, and sales facts connect.
- Step 2: Review the data sources
  - Confirm the ERP export formats that are supported. The Power Query queries assume a typical ERP export with fields such as StoreID, StoreName, ProductID, ProductName, SaleDate, Quantity, UnitPrice, and Cost.
  - Validate that date fields are consistently formatted and that numeric fields are properly typed.
- Step 3: Run and validate the ETL
  - Refresh all Power Query queries to pull in the latest data (or load the provided sample data from the release package).
  - Check the resulting data model for any discrepancies in relationships or missing values.
  - Validate key aggregates by spot-checking totals against source data or a known benchmark.
- Step 4: Explore the dashboard
  - Use slicers to filter by store, product category, and time period.
  - Drill down from a store to individual product performance by category and month.
  - Compare periods using predefined measures like year-over-year or month-over-month changes.
- Step 5: Extend for your environment
  - Map your own ERP fields to the existing data model. Adjust the Power Query steps to align with your data schema.
  - Add new measures as needed for your business questions, such as promotional impact or channel mix.

Data model design decisions
- Star-like structure: The data model follows a star schema approach where a central fact table (Sales) relates to dimension tables (Store, Product, Time). This design makes it easier to write clean DAX measures and supports efficient filtering across multiple dimensions.
- Time dimension granularity: The Time dimension supports Year, Quarter, Month, Week, and Day granularity. This enables robust trend analysis and flexible period comparisons.
- Store dimension normalization: Stores are captured with StoreID, StoreName, Region, and Store Type. Normalization reduces duplication and improves filtering precision.
- Product dimension details: The Product dimension includes ProductID, ProductName, Category, Subcategory, and Price tier. This enables insights across product families and pricing strategies.
- Data quality and validation: The ETL includes checks for missing values, inconsistent dates, and negative quantities. Validation steps are documented to help you reproduce checks on your own data.

Data quality and validation practices
- Data completeness: Ensure all stores and products present in the ERP exports are represented in the model. If a new product appears, the ETL should create corresponding dimension records automatically if possible, or raise a warning if manual intervention is needed.
- Data accuracy: Validate totals against source data. Reconcile revenue by summing unit price times quantity and compare with the ERP’s revenue column.
- Date integrity: Confirm that all dates are valid calendar dates and map to the Time dimension consistently. Handle any out-of-range dates with a clear error flag.
- Anomaly detection: Introduce simple checks to flag negative quantities, zero sales days for stores that should be active, or unusual price spikes. These flags can drive additional investigation.

Power Query: transformation patterns you’ll see
- Data ingestion: The initial step pulls raw ERP exports into a staging area. This keeps the original data intact while transformations are applied.
- Cleaning and shaping: Normalize column names, convert data types, and handle missing values. This step ensures downstream steps operate on clean data.
- Merging and enriching: Merge with reference tables (stores, products) to enrich the dataset with descriptive attributes.
- Date handling: Create a robust date table from the SaleDate field and relate it to the Time dimension.
- Filtering: Apply business rules to exclude test data, internal transfers, or other non-sale rows if required.
- Output: Produce a fact table ready for modeling, along with dimension tables that can be related to the fact.

Sample DAX measures you’ll find or can create
- Total Sales: SUM(Sales[Amount])
- Total Cost: SUM(Sales[Cost])
- Gross Margin: [Total Sales] - [Total Cost]
- Margin Percentage: DIVIDE([Gross Margin], [Total Sales], 0)
- Average Order Value: DIVIDE([Total Sales], DISTINCTCOUNT(Sales[OrderID]), 0)
- Sales by Store: CALCULATE([Total Sales], ALLEXCEPT(Stores, Stores[StoreID]))
- Sales by Product Category: CALCULATE([Total Sales], ALL(Products[Category]))
- Year-over-Year Growth: CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Time[Date]))
- Rolling 12 Months Sales: CALCULATE([Total Sales], DATESINPERIOD(Time[Date], MAX(Time[Date]), -12, MONTH))
- Customer-level metrics (if you track customers): DISTINCTCOUNT(Sales[CustomerID]), Average Purchase Frequency, etc.

Guiding principles for the dashboard design
- Clarity first: Visuals should convey the message quickly. Use simple color schemes, legible fonts, and consistent iconography.
- Interactivity that adds value: Slicers should enable natural exploration without overwhelming the user. Default views should present an informative baseline.
- Performance awareness: Large datasets can slow Excel dashboards. Favor efficient measures, avoid heavy cross-filtering when unnecessary, and use data model relationships to minimize calculation overhead.
- Accessibility: Ensure color contrast for readers with visual impairment. Provide alternative text for images and use descriptive axis titles and labels.
- Extensibility: Design with future needs in mind. The model should allow new stores, products, or metrics to be added with minimal disruption.

File and folder structure (example)
- Workbook
  - DataModel.xlsx (the main workbook containing queries, data model, and dashboard)
  - ReadmeNotes.txt (brief notes on decisions and validation steps)
- Data
  - ERP_export_sample.csv (example input data or sample dataset included in the release)
  - Stores.csv (dimension data for stores)
  - Products.csv (dimension data for products)
  - TimeReference.csv (if you maintain a separate calendar)
- Documentation
  - Architecture.md (detailed data flow and model explanation)
  - DAX_Calculations.md (list of measures with descriptions)
  - ETL_Process.md (Power Query steps and rationale)
- Lib
  - HelperFunctions.pq (Power Query reusable steps)
- Assets
  - DashboardImages/ (optional images for visuals)
  - CoffeeIcons/ (icons or small images for visuals)

Design decisions you can adapt
- Data granularity: The model uses daily sales granularity to support weekly, monthly, and quarterly analysis. If your ERP provides only daily or weekly data, you can adjust the Time dimension accordingly.
- Currency handling: The workbook assumes a single currency. If you operate across currencies, you can introduce a currency conversion table and a measure to convert all amounts to a base currency.
- Price normalization: If there are price promotions, you can track them in a separate dimension (Promotion) and incorporate it into relevant measures for net revenue analysis.

Security and governance considerations
- Local data only: The workbook is designed for local use. It does not fetch data from external sources on demand. If you plan to distribute the workbook, consider masking sensitive fields or using sample data.
- Access control: In a shared environment, ensure that only authorized users can refresh the data and modify the data model. Use standard Office 365 or local file permissions to manage access.
- Versioning: Keep releases under version control. Document changes in a changelog so users can trace updates to the data model, measures, or visuals.

Extending the model to other scenarios
- Retail verticals: Adapt the product and time dimensions to fit other retail segments like groceries, fashion, or electronics. The same approach applies: a fact table with sales and related dimension tables.
- Online channels: If you have online sales, add a Channel dimension and a related fact table, or extend the existing Sales fact with a channel attribute.
- Promotions and campaigns: Add a Promotion dimension to analyze lift during specific campaigns. Create measures for incremental revenue and promotional margins.

Implementation tips for a smooth experience
- Start with a clean data mapping: Map ERP fields to the model fields first, then adjust Power Query steps to reflect your data reality.
- Validate early and often: Run refreshes after each major change. Use spot checks to confirm totals align with source data.
- Keep calculations transparent: Document each DAX measure with a short description in a dedicated section of the workbook. This helps future users understand intent and logic.
- Use named ranges and structured tables: In Excel, structured tables improve reliability when referencing ranges in Power Query and DAX.
- Optimize performance: Minimize cross-filtering in DAX where possible. Prefer measures that rely on well-defined relationships rather than broad CALCULATE contexts.

Common troubleshooting patterns
- Data not refreshing: Check that the data connections are valid and that the source files exist in the expected paths. Ensure that regional settings for dates and numbers match the input data.
- M code errors: If a Power Query step fails, review the step’s applied steps in the Query Editor. Look for typos in column names or type mismatches after a merge.
- Missing dimension relationships: If a dimension key does not match any fact key, you’ll see nulls in visuals. Ensure key integrity across the data model and handle missing dimension rows gracefully.
- Performance lags: Large datasets can slow the workbook. Consider aggregating data in Power Query before loading to the model, or filter to a subset for exploratory work.

Testing and validation checklist
- Data integrity tests: Verify row counts, key uniqueness for dimension keys, and foreign key relationships.
- Calculation checks: Compare a handful of DAX results against a trusted calculation done in Excel or in a sample dataset.
- Dashboard usability: Confirm that filters behave intuitively and that drill-down paths are coherent.
- Cross-period comparisons: Validate that time-based measures correctly reflect YoY and MoM deltas under various edge cases (year boundaries, missing months, etc.).

Changelog and documentation practices
- Maintain a simple changelog at Releases or in Documentation/Changelog.md to capture major updates, fixes, and feature additions.
- Inline documentation: Include comments within Power Query steps and DAX measures to explain intent and assumptions.
- User-facing notes: Add a short “How to use” section in the workbook’s Intro tab that guides new users through a first-run procedure.

Contributing and collaboration
- This project welcomes contributions that improve clarity, reliability, and functionality.
- Before contributing, review the ETL process and architecture sections to ensure changes align with the model's design.
- Propose changes via pull requests with clear descriptions of what was changed and why.

Sample data and reproducibility
- The release package includes sample data to help you reproduce the dashboard and test the workflow.
- When you replace sample data with your ERP exports, keep the field mappings consistent and validate that the data model remains coherent.

Performance considerations for large datasets
- In practice, Excel dashboards perform best when the data loaded into the model is summarized to a reasonable level of detail.
- Use incremental refresh-like techniques where possible by staging data in Power Query and loading only the necessary aggregates.
- If performance becomes a bottleneck, consider migrating some calculations to pre-aggregation steps, or using an external data model (Power BI) for heavy analysis and only bringing results into Excel for dissemination.

Shipping and licensing
- The release package typically includes the workbook and any supporting assets under an appropriate license. Review the license terms in the release notes to ensure compliant use in your environment.
- If you plan to reuse this project in a corporate setting, ensure you have the rights to distribute the workbook and any data you extract from ERP systems.

Tips for documentation discipline
- Keep a living document of decisions. Capture why you chose a particular data transformation approach, such as handling missing values or choosing a specific time granularity.
- Document data lineage: where the data comes from, how it is transformed, and how it ends up in the dashboard. This helps with audits and onboarding new team members.
- Create a glossary of terms specific to your organization that users can reference when reading the workbook and this README.

Appendix: glossary of terms
- Power Query: a data connection technology that enables you to discover, connect, combine, and refine data across a wide variety of sources.
- Power Pivot: a data modeling technology in Excel that lets you create relationships between tables and build measures with DAX.
- DAX: Data Analysis Expressions, a formula language for calculations in Power Pivot, Power BI, and Analysis Services.
- ETL: Extract, Transform, Load; a process to move data from source systems into a target data model.
- Fact table: a central table in a star schema that contains quantitative metrics for analysis.
- Dimension table: a related table in a star schema that provides descriptive attributes for filtering and grouping.
- Slicer: a UI control in Excel that filters data across multiple visuals.
- YoY: Year over Year, a measure of how a value changes compared to the same period in the previous year.

References and learning resources
- Microsoft Learn: Power Query and Power Pivot basics
- DAX guides and common patterns for financial metrics
- Best practices in Excel dashboard design
- Retail analytics case studies that demonstrate similar data modeling approaches

Acknowledgments
- This project draws on common industry patterns for retail analytics and the collective knowledge of the Excel BI community. It blends Power Query, Power Pivot, and dashboard design into a cohesive workflow that’s approachable for practitioners who rely on Excel.

Releases and download reminder
- For the latest release artifacts, visit the Releases page at the link provided at the top. The release package is the recommended way to reproduce the workbook locally.
- If you need to verify the artifacts or access an updated version, re-check the Releases section for the newest package. You can find the same link again here to navigate to the page: https://github.com/moosatae123/Data-Analysis-Excel-Power-Query-DAX-Power-Pivot-Coffee-Shop/releases

Additional notes
- This README aims to be actionable and precise. It’s written to be easy to skim but detailed enough to guide a full end-to-end workflow from ERP data to the Excel dashboard.
- If you have questions or want to extend the model to your own data environment, you can start by mapping your ERP export fields to the model’s schema and iterating on the Power Query transformations and DAX calculations accordingly.

Data-modeling reference snippet (conceptual)
- FactSales: fields include SaleID, SaleDateKey, StoreID, ProductID, Quantity, UnitPrice, Cost, Discount
- DimStore: StoreID, StoreName, Region, StoreType
- DimProduct: ProductID, ProductName, Category, SubCategory, ListPrice
- DimTime: DateKey, Date, Month, Quarter, Year, WeekOfYear
- Relationships: FactSales[StoreID] -> DimStore[StoreID], FactSales[ProductID] -> DimProduct[ProductID], FactSales[DateKey] -> DimTime[DateKey]

Usage notes for reviewers
- The project demonstrates how to structure a practical Excel BI solution that remains accessible to analysts who may not use Power BI as their primary tool.
- The approach emphasizes transparency, reproducibility, and extensibility, making it suitable for teams that want a replicable pattern for other retail analytics challenges.

End of content
