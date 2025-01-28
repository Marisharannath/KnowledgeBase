## What is Query Folding?

Query folding is the process where Power Query transforms are translated into SQL queries and executed on the source database (in this case, Snowflake). This allows operations to leverage the performance and scalability of the database instead of processing data locally.

## Does Snowflake Support Query Folding?

**Native Connector:**
When using the Snowflake Connector in Power BI, query folding is supported for most transformations that can be translated into SQL.
Common transformations like filtering, grouping, sorting, joins, and column selections typically fold into the Snowflake query.

**Custom SQL Queries:**
If your connection uses custom SQL, query folding is disabled because the SQL query is treated as a fixed output. No additional transformations are pushed back to Snowflake.

**Advanced Transformations:**
Complex or unsupported transformations in Power Query (e.g., M-specific functions or steps that cannot be translated into SQL) break query folding. After this point, subsequent transformations are performed locally in Power BI.

## How to Check Query Folding for Snowflake

**Enable Query Diagnostics:**
In Power Query, right-click on a step and select "View Native Query".
If the option is available, the query folds, and you can view the SQL query sent to Snowflake.

**Monitor in Snowflake:**
Check the Query History in the Snowflake console to see the SQL queries executed by Power BI.

**Power Query Get Metadata Option**

```bash
# Example of a code snippet
git init
git add .
git commit -m "Initial commit"
git push -u origin main
