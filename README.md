# Regression Analysis: Household Food Spending and Podcast Listens

Two applied regression studies in R that test not just *what* drives an outcome but whether that effect **changes across groups**, using interaction terms and nested-model comparison.

**Context:** MSc Business Analytics, Warwick Business School (Business Statistics) · solo project · R

📄 The full knitted report with code, outputs and plots is in [`regression_analysis.html`](regression_analysis.html). Download it and open it in a browser.

## Part 1: What drives household food spending?

**Data:** a household expenditure survey with weekly spend on food, housing, alcohol and debt repayments, plus household size, children, vehicles, sex and income band.

**Models:**
- Multiple linear regression of weekly food spend on all household characteristics.
- An interaction model (`Alcohol × Debt level`) to test whether debt changes the alcohol–food relationship.
- `anova()` to compare the nested models.

**Findings:**
- Food spend rises with housing and alcohol spend, so households that spend more on essentials and lifestyle also spend more on food.
- Household size, children, sex and income band add little once spending is controlled for.
- The interaction adds nothing: the alcohol–food relationship holds equally for low-, medium- and high-debt households.
- The model explains about 15% of variance (adj. R² = 0.15), so most of what drives food spend isn't in the data.

## Part 2: What drives daily podcast listens?

**Data:** podcast-level data with daily listens, subscribers, total reviews, average rating and genre. Invalid ratings and subscriber counts were removed.

**Models:**
- Multiple linear regression of daily listens on popularity and quality measures.
- An interaction model (`Subscribers × Genre`) to test whether subscriber growth pays off equally across genres.
- `anova()` to compare the nested models.

**Findings:**
- Subscribers and total reviews are the strongest drivers of listens (adj. R² = 0.69).
- Average rating matters much less once popularity is accounted for.
- **The genre interaction is the key result:** Comedy converts each new subscriber into more listens than Documentary does, so growth strategies shouldn't assume equal returns across genres.

## Run it

Open `regression_analysis.Rmd` in RStudio with `HouseholdExpenditure.csv` and `podcast_listens.csv` in the same folder, then knit. Requires `tidyverse`, `emmeans` and `kableExtra`.

*The datasets were provided for the module and aren't included here.*

## Tech stack

R · tidyverse · linear regression · interaction effects · ANOVA model comparison
