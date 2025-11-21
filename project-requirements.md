### **Project 1 (Challenging): Excel Dynamic Sales Dashboard**

**The Scenario:** You are the sole analyst for KicksHub. The sales director does not
want a static report. She wants a **dynamic, interactive dashboard** on a single sheet
where she can select a Sales Rep from a dropdown menu and instantly see all of their
key performance metrics and a commission breakdown for a specific month.
This project will force you to nest functions, build dynamic named ranges, use
advanced lookup techniques, and structure a spreadsheet like an application.

**The Mock Datasets (On a "Data" Sheet):**
*The structure is intentionally more complex.*
**Table 1: Raw Sales Data**
| Transaction ID | Date | Sales Rep ID | Product ID | Units Sold |
| :--- | :--- | :--- | :--- | :--- |
| 1001 | 1-Oct-24 | E102 | SNK-01 | 5 |
| 1002 | 1-Oct-24 | E101 | ACC-03 | 2 |
| ... | ... | ... | ... | ... |
*(Populate this with at least 50 rows of data, spanning 3 months (Oct, Nov, Dec), with 4
different sales reps (E101, E102, E103, E104) and all the product IDs from the next
table).*
**Table 2: Product Master**
| Product ID | Product Name | Category | Unit Price | Commission Rate |
| :--- | :--- | :--- | :--- | :--- |
| SNK-01 | Air Runner | Sneakers | 120 | 15% |
| ... | ... | ... | ... | ... |*(Use the same product details as the previous project)*
**Table 3: Sales Rep Master**
| Sales Rep ID | Rep Name |
| :--- | :--- |
| E101 | Ana |
| E102 | Ben |
| E103 | Chloe |
| E104 | David |

**Your Tasks (On a "Dashboard" Sheet):**

1. **Enrich the Raw Data (The Foundation):**
* On your "Data" sheet, use **`XLOOKUP`** to pull `Unit Price` from the `Product
Master` into your `Sales Transactions` table.
* Calculate `Total Revenue` for each transaction.
* Use **nested `IF` statements or `IFS`** to create a "Commission Tier" column.
The rule: If `Total Revenue` > $1000, the tier is "High". If `Total Revenue` is between
$500 and $1000, the tier is "Medium". Otherwise, it's "Low".

2. **Build the Interactive Dashboard Controls:**
* On your "Dashboard" sheet, create a dropdown list for **Sales Rep Name**.
*(Requires Google Search: "excel data validation dropdown list").*
* Create a second dropdown for **Month** (Oct, Nov, Dec).
* The user will select a Rep and a Month, and all the data below should update
automatically.

3. **Dynamic Calculations (The Core Challenge):**
* Below the dropdowns, create a summary section. Your goal is to calculate the
following metrics *based on the dropdown selections*. You will need to use**`SUMIFS`** and **`COUNTIFS`** (the multi-criteria versions of
`SUMIF`/`COUNTIF`).
* Total Revenue for the selected rep in the selected month.
* Total Transactions.
* Average Revenue per Transaction.
* Total number of sales in the "High" commission tier.
* 
4. **Create a Dynamic Commission Report Table:**
* This is the most advanced part. Create a small table on your dashboard that
**automatically lists all the individual transactions** for the selected rep and month.
* This is too complex for a simple lookup. You will need to use a more advanced
"dynamic array" formula. *(Requires Google Search: "excel FILTER function multiple
criteria").*
* Your table should show the `Product Name`, `Total Revenue`, and a calculated
`Commission Amount` for each of those filtered sales.

5. **Final Touches:**
* Add a chart to your dashboard that visually represents the breakdown of the
selected rep's sales by `Commission Tier` ("High", "Medium", "Low"). This chart must
also update automatically when the dropdowns change. *(Hint: A Pie Chart or Bar Chart
based on your `COUNTIFS` results would work well).*
