🎯 Project Overview
- Business Problem: Reviewing order-level information and sales
  performance can be difficult when data is spread across multiple
  tables.
- Objective: Bring order details and sales targets into a Power BI
  report so users can explore performance and compare results with
  targets.
- Target Audience: Sales teams, business analysts, and managers.
- Tool: Microsoft Power BI Desktop.
🗃️ Data Sources & Architecture
The PBIX project is intended for analysis of order and sales
information. The project context references tables such as:
- List of Orders
- Order Details
- Sales Target
- Order Data
Note: The original source files, exact row counts, reporting period,
and storage mode have not been confirmed from the PBIX metadata. Update
this section with the verified source details before publishing the
repository.
High-level flow
Source data → Power Query transformations → Data model → Measures → Report visuals
⚙️ Data Transformation (ETL)
Tool: Power Query Editor.

Typical preparation steps for this type of report include:
- Confirming column data types, especially dates, quantities, and
  numeric sales fields.
- Checking for missing values and inconsistent labels.
- Removing duplicate records only where duplicates are not valid
  business transactions.
- Standardizing column names and formats.
- Checking join keys before merging or relating tables.
These are recommended documentation points, not a verified list of
transformations performed in this PBIX. Replace them with the exact
applied Power Query steps and any custom M functions after checking
Transform data → Applied Steps.
🧠 Data Model & DAX
Modeling logic
The model should connect order-level information, order details, and
sales targets using verified common keys. Relationships should use
compatible data types and appropriate cardinality, and filter direction
should be kept as simple as possible to avoid ambiguous filtering.

A star schema is often a good choice for sales reporting, but the actual
schema and relationships in this file should be verified in Model
view before describing the model as a star schema.
Example measures
The following are illustrative DAX measures. Adapt the table and column
names to the actual model before using them.
Total Sales =
SUM ( 'Order Details'[Sales] )
Total Quantity =
SUM ( 'Order Details'[Quantity] )
Target Achievement % =
DIVIDE ( [Total Sales], [Sales Target], 0 )
The measures above assume the named columns and a compatible target
measure exist; they are examples, not confirmed measures from the
supplied PBIX.
🖥️ Dashboard Features
The supplied PBIX metadata indicates one report page. Document the
actual visuals and interactions here after opening the report in Power
BI Desktop.

Potential features for this type of report include:
- KPI cards for sales, quantity, and target achievement.
- Charts showing sales trends and comparisons.
- Tables or matrices for detailed order analysis.
- Slicers and cross-filtering for interactive exploration.
Design theme: The report metadata references a Microsoft Fluent
theme. Confirm the visible styling and visual layout in Power BI
Desktop.
💡 Key Insights
Add findings only after reviewing the report visuals and underlying
data. Suggested areas to investigate:
- Which periods or categories contribute most to sales?
- Where are actual sales above or below target?
- Which products, regions, or customer groups may need attention?
Recommendation: Use verified results from the report to identify
specific actions. No numerical findings are stated here because the
underlying data and visuals have not been independently validated.
🚀 How to Use
1. Install Microsoft Power BI Desktop.
2. Clone or download this repository and open the .pbix file.
3. If prompted, update data-source paths or credentials through Home
   → Transform data → Data source settings.
4. Review the queries in Power Query Editor and the relationships in
   Model view.
5. Refresh the data, resolve any source or credential errors, and
   inspect the report pages.
6. Save a copy before changing queries, relationships, or measures.
