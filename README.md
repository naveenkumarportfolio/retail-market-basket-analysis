# Retail Purchase Patterns & Cross-Selling Analytics

### Market Basket Analysis using Microsoft Excel

A retail analytics project focused on identifying product associations, understanding customer purchase patterns, and discovering potential cross-selling opportunities using transaction data.

---

## 📌 Project Overview

The objective of this project is to analyse retail transactions and identify products that customers frequently purchase together.

Using Market Basket Analysis, the project applies **Support, Confidence, and Lift** to discover product relationships and translate analytical findings into practical business recommendations.

**Business Question:** Which products are purchased together, and how can retailers use these patterns to improve cross-selling and merchandising decisions?

## 🎯 Project Objectives

- Analyse customer purchase patterns.
- Identify frequently purchased product combinations.
- Calculate Support, Confidence, and Lift.
- Discover meaningful product associations.
- Develop data-driven cross-selling recommendations.
- Present findings through an Excel dashboard.

## 📊 Dataset Overview

| Metric | Details |
|---|---:|
| Product-line records | 57,881 |
| Total transactions | 10,000 |
| Unique customers | 3,291 |
| Unique products | 55 |
| Product categories | 10 |
| Analysis period | 1 January – 7 October 2026 |
| Currency | INR |

*Dataset figures should be verified against the final workbook before publication.*

## 🛠️ Tools & Technologies

- **Microsoft Excel** — data analysis, formulas, calculations, and dashboard development.
- **Google Sheets** — online viewing and sharing, where applicable.
- **Python/pandas** — independent validation, where performed.

## 🔍 Methodology

Each `Transaction_ID` is treated as one shopping basket. A product is considered present in a basket if it appears at least once in that transaction.

### 1. Support

Measures the percentage of all transactions containing a particular product or product combination.

**Formula:**

Support(A, B) = Transactions containing both A and B / Total transactions

### 2. Confidence

Measures how frequently product B appears in transactions containing product A.

**Formula:**

Confidence(A → B) = Transactions containing both A and B / Transactions containing A

Confidence is directional, meaning A → B can have a different value from B → A.

### 3. Lift

Measures the strength of an association between two products compared with what would be expected if their purchases were independent.

**Formula:**

Lift(A, B) = Support(A, B) / [Support(A) × Support(B)]

- **Lift > 1:** Positive association.
- **Lift = 1:** No association beyond independence.
- **Lift < 1:** Negative association.

The analysis evaluates **1,485 unique unordered product pairs** from 55 products, using a minimum co-occurrence threshold of 100 transactions to highlight stronger associations.

## 📈 Key Findings

### Bread + Butter
- Transactions containing both: 1,611
- Support: 16.11%
- Confidence (Bread → Butter): 57.1%
- Confidence (Butter → Bread): 79.6%
- Lift: approximately 2.82

This is the most frequently occurring product pair in the reported analysis.

### Detergent + Dishwash
- Transactions containing both: 710
- Support: 7.10%
- Confidence (Detergent → Dishwash): 66.0%
- Confidence (Dishwash → Detergent): 57.9%
- Lift: approximately 5.38

This pair has the highest reported Lift among pairs meeting the 100-transaction threshold.

### Toothbrush + Toothpaste
- Transactions containing both: 878
- Support: 8.78%
- Confidence (Toothbrush → Toothpaste): 62.4%
- Confidence (Toothpaste → Toothbrush): 74.9%
- Lift: approximately 5.33

The association suggests a potential opportunity for complementary product placement.

### Pasta + Tomato Sauce
- Transactions containing both: 678
- Support: 6.78%
- Confidence (Pasta → Tomato Sauce): 78.9%
- Confidence (Tomato Sauce → Pasta): 44.9%
- Lift: approximately 5.23

This pair may be suitable for testing cross-selling prompts or bundle offers.

*These figures are reported project findings and should be checked against the final workbook before publication. Associations do not prove causation or increased profitability.*

## 📁 Workbook Structure

The Excel workbook contains the following sheets:

| Sheet | Purpose |
|---|---|
| Start_Here | Project introduction and workbook navigation |
| README | Workbook instructions |
| Raw_Data | Transaction-level product data |
| Data_Quality | Data-quality checks and sales reconciliation |
| Product_Analysis | Product-level performance and transaction frequency |
| Pair_Analysis | Product-pair counts, Support, Confidence, and Lift |
| Transaction_Analysis | Transaction-level analysis |
| Dashboard | Summary metrics and visual insights |
| Methodology | Metric definitions and analytical assumptions |
| Recommendations | Business recommendations |
| Basket_Lookup | Transaction-level basket exploration |
| Error_Register | Recorded validation issues, if any |

## 💡 Business Recommendations

1. **Cross-selling:** Test complementary product recommendations for pairs with strong associations.
2. **Product placement:** Evaluate placing related products near each other.
3. **Bundle experiments:** Test selected product combinations and compare results with a control group.
4. **Inventory planning:** Use frequent product combinations as supporting information for replenishment decisions.
5. **Performance measurement:** Track conversion rate, average basket value, sales, and gross margin before expanding any initiative.

These recommendations are hypotheses to test, not guaranteed business outcomes.

## ⚠️ Limitations

- Findings apply to the supplied dataset and analysis period.
- Product association does not establish causation.
- Product cost and gross-margin data are not available for profitability analysis.
- Seasonal effects and statistical significance have not been established.
- Low-frequency product pairs may produce unstable Lift values.

## 🚀 How to Explore the Project

1. Open the Excel workbook: `Market_Basket_Analysis_Project.xlsx`.
2. Start with the **Dashboard** sheet.
3. Review **Data_Quality** to understand the checks performed.
4. Explore **Product_Analysis** to compare individual products.
5. Use **Pair_Analysis** to investigate product combinations and association metrics.
6. Review **Recommendations** for potential business applications.

## 👨‍💻 About Me

**Naveen**  
BBA — Finance & Marketing Analytics  
CHRIST (Deemed to be University), Delhi NCR

This project reflects my interest in business analytics, retail strategy, marketing analytics, and data-driven decision-making.

## 📌 Disclaimer

This is an educational portfolio project. Recommendations are exploratory and should be validated through further analysis or controlled business experiments. Confirm dataset ownership and sharing permissions before publishing the workbook publicly.

---

**If you find this project useful, feel free to explore the workbook and share feedback.**
