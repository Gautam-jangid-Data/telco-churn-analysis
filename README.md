# Superstore Sales Dashboard (2011–2014)

An interactive Power BI dashboard that analyzes 51,290 orders from a global retail store to find where the business makes money, where it loses money, and how discounts affect profit.

![Dashboard](dashboard.png)

## Business Questions
1. Which region earns the most profit?
2. Which products are losing money?
3. How do sales change month by month?
4. Does a higher discount hurt profit?

## Tools Used
- **Excel / Python (pandas):** data cleaning
- **Power BI Desktop:** dashboard, DAX measure, slicers
- **GitHub:** project documentation

## Data Cleaning
- Converted `sales` from text to numbers (values like `1,648` contained commas)
- Standardized dates: the file mixed `d/m/yyyy` and `d-m-yyyy` formats; all dates are now `yyyy-mm-dd`
- Checked for blanks, duplicates, and that ship date is never before order date (all passed)
- Added `year_month` and `profit_margin` columns
- Fixed one order with zero sales that caused a divide-by-zero in `profit_margin`

## Dashboard Features
- KPI cards: Total Sales, Total Profit, Profit Margin % (DAX measure: `DIVIDE(SUM(profit), SUM(sales))`)
- Profit by Region and by Sub-Category
- Monthly Sales Trend
- Average Profit by Discount Level
- Year and Region slicers for interactive filtering

## Key Insights
| Metric | Result |
|---|---|
| Total sales / profit | $12.64M sales, $1.47M profit, 11.6% margin |
| Top region | **Central**: $311K profit, the highest of 13 regions |
| Top sub-category | **Copiers**: $259K profit |
| Loss-making sub-category | **Tables**: -$64K, the only sub-category with a net loss |
| Sales growth | Sales grew from $2.26M (2011) to $4.30M (2014), about **+90%** |
| Discounts | Orders with **more than 30% discount** (10,361 orders) lost about **$794K** combined, while orders with 30% or less discount earned about **$2.26M** |

## Recommendations
1. **Cap discounts at around 30%.** Above that level, orders consistently lose money. The average order with 40%+ discount loses about $76, while an order with up to 20% discount earns about $57.
2. **Review the Tables sub-category.** It is the only net loss-maker, and its heaviest losses come from 60%–70% discount orders.
3. **Grow in Central and North**, the strongest regions, and review pricing in low-profit regions such as Canada and Southeast Asia.

## Files
- `Superstore_Dashboard.pbix`: Power BI dashboard
- `Superstore_Clean.csv`: cleaned dataset
- `dashboard.png`: dashboard screenshot
