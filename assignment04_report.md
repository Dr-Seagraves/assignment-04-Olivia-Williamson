# Assignment 04 Interpretation Memo

**Student Name:** [olivia williamson]
**Date:** [feb15]
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors:

| Model | Y Variable | X Variable | Interpretation Focus |
|-------|------------|------------|----------------------|
| 1 | ret (annual) | div12m_me | Dividend yield |
| 2 | ret (annual) | prime_rate | Interest rate sensitivity |
| 3 | ret (annual) | ffo_at_reit | FFO to assets (fundamental performance) |

For each model, summarize the key results in the sections below.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): 0.1082 (SE: 0.0060, p-value: < 0.001)
- Slope (β₁): -0.0687 (SE: 0.0320, p-value: 0.035)
- R²: 0.002 | N: 2527

**Model 2: ret ~ prime_rate**
- Intercept (β₀): 0.1998 (SE: 0.0160, p-value: < 0.001)
- Slope (β₁): -0.0194 (SE: 0.0030, p-value: < 0.001)
- R²: 0.016 | N: 2527

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): 0.0973 (SE: 0.0090, p-value: < 0.001)
- Slope (β₁): 0.5770 (SE: 0.5670, p-value: 0.309)
- R²: 0.000 | N: 2518

*Note: Model 3 may have fewer observations if ffo_at_reit has missing values; statsmodels drops those rows.*

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- A 1 percentage point increase in dividend yield (12-month dividends / market equity) is associated with a -0.000687 change in annual return.
- Higher dividend yield is associated with lower returns; this may reflect mature or distressed REITs with fewer growth opportunities.

**Prime Loan Rate (prime_rate):**
- A 1 percentage point increase in the year-end prime rate is associated with a -0.0194 change in annual return.
- The evidence suggests REIT returns are negatively sensitive to interest rates; higher rates are linked to lower returns.

**FFO to Assets (ffo_at_reit):**
- A 1 unit increase in FFO/Assets (fundamental performance) is associated with a 0.5770 change in annual return.
- More profitable REITs appear to have higher returns in this simple model, but the relationship is not statistically significant.

---

## 4. Statistical Significance

For each slope, at the 5% significance level:
- **div12m_me:** Significant — Negative slope; higher dividend yield is associated with lower annual returns.
- **prime_rate:** Significant — Negative slope; higher prime rates are associated with lower annual returns.
- **ffo_at_reit:** Not significant — Slope is positive but not statistically different from zero.

**Which predictor has the strongest statistical evidence of a relationship with annual returns?** The prime rate, based on the smallest p-value and highest R² among the three.

---

## 5. Model Fit (R-squared)

Compare R² across the three models:
- The prime_rate model has the highest R² (0.016), but all three R² values are very low. This suggests that single predictors explain little of the variation in annual REIT returns and other factors likely drive performance.

---

## 6. Omitted Variables

By using only one predictor at a time, we might be omitting:
- REIT size (market cap): larger firms may have more stable returns and different dividend yields.
- Leverage (debt ratio): higher leverage can amplify returns and is often related to interest-rate sensitivity.
- Property type or sector mix: returns differ across sectors and may correlate with payout policies or profitability.

**Potential bias:** If these factors correlate with the X variable and returns, slope estimates may be biased. For example, higher dividend yield could be correlated with lower growth opportunities, biasing the dividend-yield slope downward.

---

## 7. Summary and Next Steps

**Key Takeaway:**
The prime rate shows the strongest statistical relationship with REIT annual returns, with a negative and significant slope, which aligns with higher borrowing costs weighing on REIT performance. Dividend yield also has a small negative relationship, while FFO/Assets is not statistically significant in this simple model. Overall, the evidence suggests interest rates matter most among the three predictors, though explanatory power is low.

**What we would do next:**
- Extend to multiple regression (include two or more predictors)
- Test for heteroskedasticity and other OLS assumption violations
- Examine whether relationships vary by time period or REIT sector

---

## Reproducibility Checklist
- [x] Script runs end-to-end without errors
- [x] Regression output saved to `Results/regression_div12m_me.txt`, `regression_prime_rate.txt`, `regression_ffo_at_reit.txt`
- [x] Scatter plots saved to `Results/scatter_div12m_me.png`, `scatter_prime_rate.png`, `scatter_ffo_at_reit.png`
- [x] Report accurately reflects regression results
- [x] All interpretations are in economic units (not just statistical jargon)
