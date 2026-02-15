# AI Audit Appendix (Assignment 04)

## Tool(s) Used
- github chatbot

## Task(s) Where AI Was Used
- on the regression and report

## Prompt(s)
- Create fig, ax with plt.subplots(figsize=(10, 6))
- Filter to rows with valid x_var and ret
- Create a scatter plot
- Overlay regression line (use model.params['Intercept'] and model.params[x_var])
- Where is my scatter plot?
- I dont see it in my results folder. what do i do
- Yes, finish the remaining TODOs in that function (axis limits, title/labels/legend, and plt.savefig(...))
- What does this mean: Bad Unicode escape in JSON at position 887 (line 1 column 888)
- Can you fix it
- Yes run it
- Print intercept (β₀), slope (β₁), standard errors, t-stats, p-values
- TODO: Print R², Adj R², N
- Yes finish the last TODO about slope sign and 5% significance?
- For each model, summarize the key results in the sections below.
- Yes, fill these directly into your report file
- Dividend Yield (div12m_me) interpretation prompt
- Prime Loan Rate (prime_rate) interpretation prompt
- FFO to Assets (ffo_at_reit) interpretation prompt
- Yes (answer strongest statistical evidence question)
- Yes (fill model fit/R² paragraph)
- Yes (draft omitted variables section)
- Yes (draft summary/next steps)
- Update the reproducibility checklist

## Output Summary
- Completed plotting code (scatter, regression line, axis limits, titles, savefig).
- Added regression result printing (coefficients, SEs, t-stats, p-values, R^2, significance).
- Filled report sections with regression outputs, interpretations, model fit, omitted variables, and summary.
- Updated reproducibility checklist items.

## Verification & Modifications (Disclose • Verify • Critique)
- **Verify:** Ran assignment04_regression.py and reviewed saved results and plots.
- **Critique:** Initial plotting TODOs were incomplete, so plots were not saved until fixed.
- **Modify:** Updated report text for clarity and consistency after checking outputs.

## If No AI Tools Used
Write: "No AI tools were used for this assignment."
