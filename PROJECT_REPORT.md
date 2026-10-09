
# Project Report: Retail Purchase Patterns & Cross-Selling Analytics

**Project Type:** Retail Data Analytics  
**Primary Tool:** Microsoft Excel  
**Analysis Technique:** Market Basket Analysis  
**Author:** Naveen  
**Programme:** BBA — Finance & Marketing Analytics  
**University:** CHRIST (Deemed to be University), Delhi NCR  
**Reporting Period:** 1 January – 7 October 2026

---

## 1. Executive Summary

This project applies Market Basket Analysis to retail transaction data to identify products that customers frequently purchase together.

The analysis uses Microsoft Excel to examine transaction-level data, evaluate product combinations, calculate Support, Confidence, and Lift, and present findings through product analysis, pair analysis, and a dashboard.

The dataset is reported to contain 57,881 product-line records, 10,000 transactions, 3,291 unique customers, 55 unique products, and 10 product categories.

The analysis highlights product combinations with high transaction frequency and strong associations. These findings can help retailers develop hypotheses for cross-selling, product placement, promotional bundles, and merchandising experiments.

The primary objective is to demonstrate how quantitative analysis can be translated into practical business insights.

## 2. Introduction

Retail businesses generate large amounts of transaction data through customer purchases. Analysing this data can reveal purchasing patterns that are not immediately visible from individual product sales.

Market Basket Analysis is a technique used to identify relationships between products purchased in the same transaction.

For example, if customers frequently purchase bread and butter together, a retailer may consider testing complementary product placement or a cross-selling recommendation.

However, frequent co-purchases do not automatically prove that a promotion will increase sales or profitability. Business recommendations must be evaluated through further testing.

This project applies Market Basket Analysis to explore retail purchasing behaviour and identify potential opportunities for data-driven decision-making.

## 3. Problem Statement

Retailers need to understand which products customers tend to purchase together to improve product discovery, merchandising, and cross-selling strategies.

Looking only at individual product sales does not fully explain the relationships between products within a shopping basket.

This project addresses the following business question:

**Which products are purchased together, and how can retailers use these associations to explore cross-selling and merchandising opportunities?**

## 4. Project Objectives

The main objectives are:

1. Analyse retail transaction data and understand customer basket patterns.
2. Identify frequently purchased products and product combinations.
3. Calculate Support, Confidence, and Lift for product pairs.
4. Distinguish frequently occurring pairs from pairs with stronger associations.
5. Develop practical, data-driven business recommendations.
6. Present the analysis through a structured Excel workbook and dashboard.

## 5. Dataset Overview

The dataset is reported to contain the following information.

| Metric | Value |
|---|---:|
| Product-line records | 57,881 |
| Total transactions | 10,000 |
| Unique customers | 3,291 |
| Unique products | 55 |
| Product categories | 10 |
| Analysis period | 1 January – 7 October 2026 |
| Currency | INR |

### Data structure

The workbook's transaction-level data includes fields such as:

- Transaction ID
- Transaction date
- Customer ID
- Product name
- Product category
- Quantity
- Unit price
- Discount percentage
- Sales value

A transaction can contain multiple product-line records. Therefore, the analysis treats each unique Transaction_ID as one shopping basket.

A product is considered present in a basket if it appears at least once in that transaction.

*Note: Dataset figures and field names should be confirmed against the final workbook before publication.*

## 6. Tools and Technologies

### Microsoft Excel

Excel is the primary analytical tool used to organise transaction data, perform calculations, analyse products and product pairs, and present findings through a dashboard.

### Google Sheets

Google Sheets can be used to share and view the workbook online, subject to compatibility and formatting differences.

### Python/pandas

Python and pandas may be used for independent validation of calculations where the corresponding checks have actually been performed.

## 7. Methodology

The analysis follows a transaction-based approach.

### Step 1: Data preparation

The transaction data is reviewed for missing values, duplicate records, invalid dates, non-positive quantities or prices, inconsistent product naming, and sales-value reconciliation.

The workbook includes a Data_Quality sheet to document the relevant checks.

### Step 2: Basket identification

Each unique Transaction_ID is treated as one basket.

If a product appears more than once within the same transaction, it is counted as present in that basket for product-pair calculations.

### Step 3: Product analysis

Individual products are evaluated using transaction frequency, basket penetration, quantities, and sales-related measures available in the workbook.

This identifies products that are common across transactions and provides context for interpreting product-pair results.

### Step 4: Product-pair analysis

All unique unordered product pairs are evaluated.

With 55 unique products, the total number of possible unordered pairs is:

55 × 54 ÷ 2 = 1,485 pairs.

The analysis uses co-occurrence counts and association metrics to compare these pairs.

### Step 5: Dashboard and interpretation

The results are organised into an Excel dashboard and supporting worksheets.

The analysis distinguishes between pairs that occur frequently and pairs whose association is stronger relative to their individual product frequencies.

A minimum co-occurrence threshold of 100 transactions is used in the reported strong-association analysis.

## 8. Key Analytical Metrics

### 8.1 Support

Support measures the proportion of all transactions containing a particular product or product combination.

**Formula:**

Support(A, B) = Transactions containing both A and B / Total transactions

For example, if a product pair occurs in 1,611 out of 10,000 transactions:

Support = 1,611 / 10,000 = 16.11%.

Higher Support indicates that the pair appears in a larger proportion of all baskets.

### 8.2 Confidence

Confidence measures how frequently one product appears in transactions that contain another product.

**Formula:**

Confidence(A → B) = Transactions containing both A and B / Transactions containing A

Confidence is directional.

For example, Confidence(Bread → Butter) measures the proportion of bread-containing baskets that also contain butter.

Confidence(Butter → Bread) measures the proportion of butter-containing baskets that also contain bread.

These two values can differ because the products may have different individual transaction frequencies.

### 8.3 Lift

Lift measures the strength of a product association relative to the association expected if purchases were independent.

**Formula:**

Lift(A, B) = Support(A, B) / [Support(A) × Support(B)]

Interpretation:

- **Lift greater than 1:** The products occur together more often than expected under independence.
- **Lift equal to 1:** The observed association is consistent with independence.
- **Lift below 1:** The products occur together less often than expected under independence.

Lift should be interpreted alongside transaction counts and Support. A high Lift based on very few transactions may be unstable.

## 9. Key Findings

The following findings are reported from the project analysis and should be checked against the final workbook before publication.

### 9.1 Bread + Butter

| Metric | Reported Result |
|---|---:|
| Co-occurring transactions | 1,611 |
| Support | 16.11% |
| Confidence (Bread → Butter) | 57.1% |
| Confidence (Butter → Bread) | 79.6% |
| Lift | 2.82 |

Bread and Butter is the most frequently occurring product pair in the reported analysis.

The relatively high Support indicates that the combination appears in a meaningful proportion of all baskets.

**Potential business application:** Test complementary product placement or cross-selling prompts while monitoring conversion and basket value.

### 9.2 Detergent + Dishwash

| Metric | Reported Result |
|---|---:|
| Co-occurring transactions | 710 |
| Support | 7.10% |
| Confidence (Detergent → Dishwash) | 66.0% |
| Confidence (Dishwash → Detergent) | 57.9% |
| Lift | 5.38 |

This pair has the highest reported Lift among pairs meeting the minimum threshold of 100 co-occurring transactions.

Its Lift indicates a strong association relative to the products' individual transaction frequencies.

**Potential business application:** Test complementary placement or recommendation prompts within relevant household-cleaning product sections.

### 9.3 Toothbrush + Toothpaste

| Metric | Reported Result |
|---|---:|
| Co-occurring transactions | 878 |
| Support | 8.78% |
| Confidence (Toothbrush → Toothpaste) | 62.4% |
| Confidence (Toothpaste → Toothbrush) | 74.9% |
| Lift | 5.33 |

The pair demonstrates a strong reported association and appears in 878 transactions.

**Potential business application:** Evaluate a cross-selling recommendation or a combined offer, then compare performance with a control group.

### 9.4 Pasta + Tomato Sauce

| Metric | Reported Result |
|---|---:|
| Co-occurring transactions | 678 |
| Support | 6.78% |
| Confidence (Pasta → Tomato Sauce) | 78.9% |
| Confidence (Tomato Sauce → Pasta) | 44.9% |
| Lift | 5.23 |

The directional Confidence values differ, indicating that the proportion of pasta baskets containing tomato sauce is different from the proportion of tomato-sauce baskets containing pasta.

**Potential business application:** Test product recommendations or coordinated placement in the relevant food category.

### 9.5 Interpretation of the findings

These examples illustrate why multiple metrics are useful:

- Support identifies how common a product pair is across all transactions.
- Confidence indicates the directional likelihood of finding one product in baskets containing another.
- Lift measures the strength of the association relative to the products' individual frequencies.

The most frequent pair is not necessarily the pair with the highest Lift. Retailers should consider both transaction frequency and association strength when prioritising experiments.

## 10. Business Recommendations

### Recommendation 1: Test complementary product placement

Evaluate whether placing strongly associated products closer together improves product discovery or purchasing behaviour.

### Recommendation 2: Experiment with cross-selling prompts

Use selected product associations to generate product recommendations on digital platforms or at the point of sale.

### Recommendation 3: Test product bundles

Experiment with combinations such as Bread + Butter or Pasta + Tomato Sauce. Compare bundle performance against a suitable control group before expanding the promotion.

### Recommendation 4: Use transaction frequency as supporting information

Frequent product pairs may provide useful context for stock availability and replenishment planning. However, inventory decisions should also consider demand forecasts, lead times, stock levels, and seasonality.

### Recommendation 5: Measure business impact

Evaluate experiments using relevant measures, including:

- Product attach rate
- Conversion rate
- Average basket value
- Incremental sales
- Gross margin
- Promotion cost

A strong association does not guarantee that a bundle or promotion will be profitable.

## 11. Workbook Structure

The Excel workbook contains the following sheets.

| Sheet | Purpose |
|---|---|
| Start_Here | Workbook orientation |
| README | Instructions and overview |
| Raw_Data | Transaction-level product data |
| Data_Quality | Data-quality checks and sales reconciliation |
| Product_Analysis | Product-level metrics |
| Pair_Analysis | Product-pair counts and association metrics |
| Transaction_Analysis | Transaction-level analysis |
| Dashboard | Summary metrics and visual insights |
| Methodology | Definitions and analytical assumptions |
| Recommendations | Potential business applications |
| Basket_Lookup | Transaction-level basket exploration |
| Error_Register | Recorded validation issues, if any |

The Dashboard provides a summary of the analysis, while the supporting worksheets allow users to explore individual products, product combinations, data quality, and recommendations.

## 12. Data Quality and Validation

The workbook's Data_Quality sheet is designed to assess the integrity of the transaction data.

Checks include:

- Missing values
- Duplicate records
- Date validity
- Quantity and price validity
- Product naming consistency
- Sales-value reconciliation

The reported project validation states that all 1,485 pair counts were independently recomputed and that no mismatches were found. It also reports that formulas were recalculated using LibreOffice with no formula errors.

These validation claims should only be included in a published report if the corresponding checks were actually completed on the final workbook.

Formula behaviour and visual formatting may differ across Microsoft Excel, LibreOffice, and Google Sheets. The workbook should be reviewed in the application used by its intended audience.

## 13. Limitations

The project has several limitations.

### Descriptive analysis

The results describe observed purchasing patterns. They do not prove that buying one product causes customers to buy another.

### Dataset coverage

The findings apply to the supplied dataset and analysis period. They may not generalise to other retailers, locations, or periods.

### Profitability

Product cost and gross-margin information is not available for the reported analysis. Therefore, the project cannot establish the profitability of specific product bundles or cross-selling strategies.

### Statistical significance

The analysis does not establish statistical significance or causal impact. Strong associations should be treated as candidates for further testing.

### Low-frequency pairs

Lift can be unstable for product pairs with few co-occurrences. The minimum transaction threshold helps filter low-frequency pairs but does not eliminate all uncertainty.

### Seasonality

The project does not establish seasonal purchasing patterns or prove that observed associations remain stable over time.

## 14. Future Improvements

Potential next steps include:

1. Add transaction-level trend analysis across weeks or months.
2. Compare product associations across customer segments.
3. Incorporate product costs and margins to evaluate commercial value.
4. Conduct controlled experiments to measure incremental sales.
5. Develop automated reporting using Python.
6. Explore additional association-rule metrics and more advanced basket analysis.

These improvements could extend the project from descriptive analytics towards more detailed retail decision support.

## 15. Conclusion

This project demonstrates how Market Basket Analysis can be used to examine retail purchasing patterns and identify product associations.

By combining Support, Confidence, and Lift with product-level analysis and an Excel dashboard, the project turns transaction data into interpretable findings and practical business hypotheses.

The analysis provides a foundation for further experimentation in cross-selling, product placement, and merchandising while recognising that actual commercial impact must be validated using additional data and controlled testing.

The project also demonstrates practical skills in spreadsheet analysis, quantitative interpretation, data presentation, and business recommendation development.

## 16. Project Files

- `Market_Basket_Analysis_Project.xlsx` — Excel workbook containing the analysis and dashboard.
- `README.md` — Project overview, methodology, and key findings.
- `PROJECT_REPORT.md` — Detailed written project report.
- `images/` — Dashboard and analysis screenshots, if included.

## 17. Author

**Naveen**  
BBA — Finance & Marketing Analytics  
CHRIST (Deemed to be University), Delhi NCR

**Areas of interest:** Business Analytics, Retail Analytics, Marketing Analytics, Financial Analysis, and Data-Driven Decision-Making.

---

### Disclaimer

This report describes an educational portfolio project. Reported figures should be verified against the final workbook before publication. Business recommendations are hypotheses for further investigation, not guarantees of increased sales or profitability. Dataset ownership and permission for public sharing should be confirmed before publishing the workbook or screenshots.
