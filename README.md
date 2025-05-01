# CoffeeSalesExcel

## Dashboard Overview
| Component | Description | Key Metrics |
|-----------|-------------|-------------|
| **Product Analysis** | Coffee product pricing and profitability | 48 SKUs across 4 types |
| **Sales Performance** | Monthly and geographic sales trends | 3 years of sales data |
| **Customer Insights** | Top customers and purchasing patterns | 32 customer profiles |
| **Recommendations** | Actionable business strategies | 5 key initiatives |

## Data Preparation
### Data Sources
| Data Type | Records | Fields |
|-----------|---------|--------|
| Products | 48 | Type, Roast, Size, Price |
| Sales | 1,200+ | Date, ProductID, Qty, Revenue |
| Customers | 32 | ID, Name, Country, Loyalty |

### Data Processing
```python
# Standardized product IDs
df['product_id'] = df['type'].str[0] + '-' + df['roast'].str[0] + '-' + df['size'].astype(str)

# Calculated metrics
df['price_per_100g'] = round(df['price'] / (df['size'] * 10), 2)
df['profit'] = round(df['price'] * 0.09, 2)  # 9% margin

# Product Analysis

## Price Comparison (USD)

| Size   | Arabica-Light | Arabica-Medium | Arabica-Dark |
|--------|--------------|---------------|-------------|
| 0.2kg  | 3.89         | 3.38          | 2.99        |
| 0.5kg  | 7.77         | 6.75          | 5.97        |
| 1.0kg  | 12.95        | 11.25         | 9.95        |
| 2.5kg  | 29.79        | 25.88         | 22.89       |

## Profit Margins

| Coffee Type | Avg Margin | Top Product | Profit |
|------------|-----------|-------------|--------|
| Arabica    | 9.0%      | A-L-2.5     | 2.68   |
| Robusta    | 6.0%      | R-L-2.5     | 1.65   |
| Liberica   | 13.1%     | L-L-2.5     | 4.74   |
| Excelsa    | 8.5%      | E-L-2.5     | 3.35   |

# Sales Performance

## Monthly Sales (2019-2021)

| Year | Jan   | Feb   | Mar   | Apr    |
|------|-------|-------|-------|--------|
| 2019 | 1,102 | 987   | 1,346 | 1,681  |
| 2020 | 1,287 | 1,745 | 1,429 | 2,114  |
| 2021 | 1,345 | 1,532 | 1,758 | 1,882  |

## Country Breakdown

| Country        | Total Sales | % Revenue |
|----------------|------------|----------|
| United States  | 35,639     | 83%      |
| Ireland        | 6,697      | 16%      |
| United Kingdom | 2,799      | 1%       |

# Customer Insights

## Top 5 Customers

| CustomerID    | Name        | Total Spend | Orders |
|---------------|------------|------------|--------|
| 17670-51384   | A. Allner   | 317        | 5      |
| 73342-18763   | P. Bote     | 307        | 6      |
| 21125-22134   | J. Redholes | 289        | 4      |
| 72153-00052   | D. Azema    | 282        | 3      |
| 23806-46781   | C. O'Shea   | 278        | 5      |

# Recommendations

## Product Strategy

| Action            | Target        | Expected Impact |
|-------------------|--------------|----------------|
| Liberica expansion | Add 2 SKUs   | +15% margin     |
| Bulk discounts    | 2.5kg+ sizes | +20% volume     |

## Marketing Focus

| Market       | Priority  | Tactic         |
|--------------|----------|---------------|
| Ireland      | High     | Local blends   |
| UK           | Medium   | Free shipping  |
| US Loyalty   | Critical | Bonus points   |
