# Portfolio Notes and Source Reconciliation

This file documents changes made while converting the Group capstone project into a public-facing portfolio repository.

## 1. Model comparison wording corrected

The source presentation described Gradient Boosting as having the "highest AUC" in one place. The saved notebook outputs show:

- Logistic Regression test AUC: 0.7812
- Random Forest test AUC: 0.8426
- Gradient Boosting test AUC: 0.8377

Therefore the portfolio does **not** state that GBT has the highest AUC. It describes GBT as the **source-team selected governance tradeoff model**.

## 2. Age metrics reconciled to the saved GBT notebook

The public portfolio uses the executed GBT notebook outputs as the primary numerical source:

- 65-74 AIR vs 45-54: 0.754386
- >74 AIR vs 45-54: 0.648053
- >74 Female AIR vs 45-54 Male: 0.623058
- >74 American Indian / Alaska Native AIR vs 45-54 White (Non-Hispanic): 0.490 (source summary)

Where the source slide deck contains different age figures, those are treated as stale / differently referenced presentation values and are not used as the headline portfolio metrics.

## 3. Cross-model subgroup comparisons are approximate

All three saved notebooks use a stratified 80/20 split with `random_state=42`, but the saved race-group counts differ slightly across model runs. The likely reason is that each notebook independently re-queries / reconstructs the dataset before splitting, so row ordering is not guaranteed to be identical.

As a result, subgroup FPR/FNR comparisons across the three models are useful but should not be presented as a perfectly controlled same-row holdout experiment.

## 4. Sensitive attributes are audit fields, not model inputs

The code drops `race`, `sex`, `applicant_age`, and `state_code` from the predictive feature matrix. They remain available in `df_model` for subgroup and governance analysis.

## 5. Legal / compliance wording softened

The portfolio describes proxy, age, and disparate-impact findings as **audit risks or review flags**. It does not make a legal determination of discrimination or compliance.

## 6. Team attribution preserved

This was completed as a capstone project for DNSC 6330. Public packaging does not attribute every analysis component to a single individual.
