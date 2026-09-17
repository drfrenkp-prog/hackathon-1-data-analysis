# Superstore Sales & Profitability Analysis: The Hidden Cost of Discounting

## Description
An analysis of the US Superstore dataset (9,994 orders) investigating whether excessive discounting is causing unprofitability in specific regions, states, and product categories — despite those segments generating solid sales. Solo project for Hackathon #1 of the AI-Powered Data Analytics Bootcamp.

## Problem Statement
- Do high-sales regions/states/categories actually translate into high profit, or is discounting eroding those gains in specific segments?
- Hypothesis: some high-revenue segments are unprofitable due to excessive discounting, not low sales volume.

## Data Source
- Primary dataset: Sample - Superstore (9,994 orders, 21 columns), loaded directly from a GitHub-hosted CSV
- External source: live USD→EUR exchange rate via the free Frankfurter API (api.frankfurter.dev, no API key required), used to express Sales and Profit in EUR alongside USD

## Tech Stack
- Python, Pandas, NumPy
- Matplotlib / Seaborn
- Requests (for the currency API call)
- Jupyter Notebook (via VS Code + WSL2/Ubuntu)

## How to Run
1. Clone the repo: `git clone https://github.com/drfrenkp-prog/hackathon-1-data-analysis.git`
2. Create a virtual environment and install dependencies: `pip install -r requirements.txt`
3. Open `notebooks/hackathon1.ipynb` in Jupyter or VS Code and run top to bottom
4. No API key needed — the currency conversion step uses Frankfurter's free, key-less API

## Main Features
- Data cleaning: missing-value/duplicate checks, datetime conversion for Order Date and Ship Date
- Live currency conversion (USD → EUR) as the required external data source
- Multi-level exploratory analysis: Region → State → Category → Sub-Category
- Hypothesis testing via Pearson correlation (Discount vs. Profit)

## Findings / Insights
- Discount and Profit show a moderate negative correlation (r ≈ -0.22) across all orders
- 10 states are net unprofitable, led by Texas (-$25.7K), Ohio (-$17.0K), and Pennsylvania (-$15.6K) — each with average discounts roughly double the dataset-wide average
- At the sub-category level, only Tables (-$17,725), Bookcases (-$3,473), and Supplies (-$1,189) are unprofitable — high discounting alone doesn't explain this, since Binders (highest discount in the dataset, 37.2%) remains highly profitable
- Recommendation: cap or reduce discounts specifically on Tables and Bookcases, rather than applying a blanket discounting policy change — these are already thin-margin, high-shipping-cost items where discounting tips them into loss

## Author
Mattia Coletto (solo)
