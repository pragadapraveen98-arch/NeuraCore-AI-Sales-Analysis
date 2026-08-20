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

### Sheet5 — Total revenue and units sold by product, and by product category *(new)*
**Answer:** Top product is **Vision QC Inspector** ($95,260 / 77 units), followed by Fraud Detection Shield ($61,085) and Chatbot Suite Pro ($59,550). By category, **Conversational AI** leads with $111,275 across 174 units, ahead of Computer Vision ($95,260) and Sales AI ($76,100).

### Sheet6 — Support ticket volume, average resolution time, and satisfaction score by issue type; ticket count by status *(new)*
**Answer:** **Data Sync Error** is the most common issue (17 tickets), followed by Feature Request and Billing Query (14 each). Fastest average resolution is **API Error (12.9 hrs)**; slowest is **Integration Help (47.0 hrs)**, which also has the highest satisfaction score (4.5/5). Onboarding Help has the lowest satisfaction (1.75/5). By status: 24 Closed, 21 Pending, 19 Escalated, 19 Open, 9 In Progress. 14 tickets had a negative resolution time (data-entry error) and were excluded from the average.

## Files

- `NeuraCore_AIsales.xlsx` — full workbook (5 data tables + 6 analysis sheets)
