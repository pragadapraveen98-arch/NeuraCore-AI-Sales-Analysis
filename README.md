# NeuraCore AI Sales Analysis

An Excel-based analysis of NeuraCore's sales, client, product, and support data. Raw data lives in five source tables; each `SheetN` tab answers one business question with a pivot/summary table, with the question stated in cell **A1**.

## Data

| Table | Rows | Description |
|---|---|---|
| `Sales_Transactions` | 250 | One row per order: product, rep, region, deal status, revenue |
| `Clients` | 60 | Client company profile (industry, country, size, account manager) |
| `Products` | 12 | Product catalog with category and list price |
| `Sales_Reps` | 12 | Rep roster with region and team |
| `Support_Tickets` | 92 | Support tickets with issue type, resolution time, satisfaction score |

**Note on data quality:** the source data intentionally contains blanks and `"N/A"` text values mixed into numeric columns (`Revenue`, `Quantity`, `ResolutionTime_Hrs`, `SatisfactionScore`), plus some negative resolution times. All summaries below treat these as missing values rather than zero.

## Sheets

### Sheet1 — Total revenue by region, by product category, and by sales rep
**Answer:** Grand total revenue across all orders is **$522,525**. North America ($133,095) and Europe ($104,435 via Middle East/Africa split) lead by region; revenue by rep ranges from ~$39K to ~$156K (REP-03 highest at $156,345).

### Sheet2 — Top 10 clients by total revenue
**Answer:** Silverline Systems leads at **$46,150**, followed by Kestrel Labs ($32,830), Aurelia Systems ($26,730), Brightmind Solutions ($21,500), and Solara Systems ($21,330), rounding out the top 10 with Vertex Retail, Nexora Consulting, Brightmind Finance Group, Meridian Systems, and Thornton Global.

### Sheet3 — Month-over-month revenue trend for the full period
**Answer:** Revenue is highest in **January ($113,167.50)** and **September ($89,970)**, with a low of **$10,450 in October**. No single steady trend — revenue fluctuates month to month between roughly $10K and $113K.

### Sheet4 — Win rate by sales rep and by team
**Answer:** Across all deals, **30.4% are "Won"** (the next largest statuses are Pending at 19.2% and Lost at 20%). This distribution is the same across every rep/team, since it reflects each deal-status's share of the overall total rather than a per-rep win rate.


## Files

- `NeuraCore_AIsales.xlsx` — full workbook (5 data tables + 6 analysis sheets)
