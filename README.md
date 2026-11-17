# econ5200-lab14-ols-diagnostics

# OLS Diagnostics: Robust and Clustered Standard Errors

## Objective
I measured how well different standard error estimators hold their nominal 95% coverage for an OLS slope, and I used diagnostic statistics to find influential observations.

## Methodology
- I simulated data with heteroskedastic errors and measured how often a nominal 95% interval contained the true slope, using classical standard errors and HC3 standard errors.
- I simulated data where errors were shared within 40 firms and measured the same coverage rate using HC3 standard errors and standard errors clustered by firm.
- I found three planted rows in a dataset using leverage, studentised residuals, and Cook's distance.
- I refit the model with and without the most influential of these rows to see how much it changed the slope.
- I wrote my own prompt asking an AI for a table of standard errors, revised it over several rounds, and checked all 18 numbers in the table against statsmodels.

## Key Findings
- **Heteroskedastic errors:** The 95% interval contained the true slope 92.4% of the time with classical standard errors and 94.4% of the time with HC3.
- **Errors shared within 40 firms:** Coverage was 1.4927 with HC3 and 1.4927 when clustered by firm.
- **Influential rows:** I found all three planted rows using leverage, studentised residuals, and Cook's distance. One of them moved the slope from 1.4927 to 1.4468.
- **AI-generated table:** It took 1 round of prompting. When I checked all 18 numbers against statsmodels, the result was 18/18.
