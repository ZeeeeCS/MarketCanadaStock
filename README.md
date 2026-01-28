## Canada Government Segment Market Analysis

This project performs an exploratory financial analysis of a sample sales dataset and visualizes the flow from products to final net profit using a Sankey diagram. The focus is on the **Government** segment in **Canada**, with product-level sales and profit breakdowns.

### Data

- **Input file**: `Financials.csv`
- **Filters applied**:
  - `Segment == "Government"`
  - `Country == "Canada"`
- **Key columns used**:
  - Product-level metrics: ` Product `, ` Units Sold `
  - Financials: ` Gross Sales `, ` Discounts `, `  Sales `, ` COGS `, ` Profit `
  - Time: `Date`, `Month Number`, ` Month Name `, `Year`

Monetary columns are cleaned from strings (e.g. `"$1,234.56"`) to numeric types before aggregation.

### Analysis & Features

- **Data cleaning**
  - String-to-float conversion for `  Sales `, ` Profit `, ` Gross Sales `, ` Discounts `, ` COGS `
  - Handling of negative and missing-like discount values.
- **Aggregations**
  - Sales by product (`sales_by_product`)
  - Yearly profit (`Profit`)
  - Yearly gross sales (`gross_profit`)
  - Yearly discounts (`services`)
  - Cost of goods sold and derived **product cost** and **revenue**
- **Profit structure**
  - Simple assumptions for:
    - R&D expenses
    - SG&A expenses
    - Taxes
  - Computation of **operating expenses**, **operating profit**, and **net profit**.
- **Visualization**
  - **Sankey diagram** (Plotly) connecting:
    - Individual products → aggregated products
    - Products → revenue, cost of revenue, services cost, product cost
    - Gross profit → operating expenses (R&D, SG&A) → taxes → operating profit → net profit
  - Rendered with Plotly in the browser with the title **"Canada Stock"**.

### Requirements

- Python 3.10+
- Packages:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `plotly`
  - `nbformat` (for notebook support)

Install dependencies (minimal set):

pip install pandas numpy matplotlib seaborn plotly nbformat
