# Retail Sales & Margin Analysis — Python

Exploratory analysis of a retail product catalog and order history: category-level sales
distribution, promo penetration, margin analysis, and ABC-classification of SKUs by revenue and
volume contribution.

## Objective

Given a product catalog and an order history for a grocery retailer, answer a set of business
questions: which categories sell best, how promo activity affects one category in depth, how margin
varies by category, and which subcategories deserve the most inventory/promotional attention.

## Data

- `products.xlsx` — product catalog: category (`level1`), subcategory (`level2`), product name
- `orders.xlsx` — order-level transactions: quantity, regular price, actual price, cost price, order
  timestamp

Joined on `product_id`. *Sample data files are not included in this repository.*

## Approach

1. Merge products and orders into a single transaction-level table
2. Rank categories and subcategories by units sold
3. Answer an ad-hoc question (average order value on a specific date) directly from the merged data
4. Measure promo penetration within a single category as a template for a category-by-category check
5. Calculate margin (absolute and %) per category
6. Run an ABC-analysis: rank subcategories by cumulative contribution to revenue and to volume, and
   classify into tiers A (top ~80% of cumulative contribution), B (next ~15%), C (the long tail)

## Key findings

- Sales are concentrated in a handful of categories — non-alcoholic beverages, dairy, fresh
  vegetables, ready meals and dry goods/groceries account for the largest share of units sold; at the
  subcategory level, beverages, ready meals and bread dominate volume.
- Promo penetration is material in the Cheeses category: roughly **32%** of items sold there moved on
  a promotional price during the analyzed period.
- Margins vary widely by category — from ~23% (Poultry) up to ~50%+ (Coffee & cocoa, Specialty
  nutrition), with staples like Cheeses (~37%) and Beverages (~44%) in between.
- ABC-analysis highlights a small set of subcategories responsible for the bulk of revenue and
  volume — the natural priority list for inventory attention and promotional focus, versus a long
  C-tier of low-impact subcategories.

## Tools

Python · Pandas · Seaborn · Matplotlib

## Note

Chart images embedded in the notebook are from the original analysis run and may still show a couple
of Russian-language axis labels; the code itself has been updated to produce English labels the next
time it's executed against the source files.
