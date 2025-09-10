# BankDataAnalysis

This project demonstrates how to extract, clean, and analyze market capitalization data using Apache Spark, plot using pandas or prepare it for visualization in Tableau.

## Key Concepts
1. Market Capitalization

Definition:

Market Cap = Share Price × Outstanding Shares
Represents the total value of a company in the stock market.
Used to classify companies as large-cap, mid-cap, or small-cap.

2. Concentration Ratios (CR3 / CR5)

CRk = Sum of market shares of the top k firms.
CR3 → Top 3 firms’ combined share.
CR5 → Top 5 firms’ combined share.

Example: If top 3 firms have 30%, 25%, and 20% share:

CR3=30+25+20=75%

This means the top 3 firms control 75% of the market.

3. Herfindahl–Hirschman Index (HHI)
   
A refined measure of market concentration, scaled between 0 and 1.
0 -> Perfect competition (many equal players).
1 -> Pure monopoly.

Rule of Thumb:
HHI < 0.15 → Competitive
0.15–0.25 → Moderately concentrated
0.25 → Highly concentrated

4. Quartile Analysis

Quartile analysis groups into four buckets based on their market capitalization or market share.
Q1 (Top 25%) → Largest firms (industry leaders).
Q2 (25–50%) → Upper mid-tier firms.
Q3 (50–75%) → Lower mid-tier firms.
Q4 (Bottom 25%) → Smallest firms (niche or emerging players).

## Tools & Implementation

PySpark / Pandas → Data processing.
Matplotlib / Seaborn / Tableau → Visualization.

## Metrics calculated:

CR3, CR5.
HHI for market concentration.
