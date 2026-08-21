# HMDA 2024 Responsible ML Audit - Portfolio Summary

## Executive finding

The source team selected a Gradient Boosting model for conditional deployment review, not because it dominated every predictive metric, but because the project considered predictive performance together with calibration, subgroup errors, explainability, robustness, ML security, and governance controls.

Random Forest achieved the highest saved test AUC (0.8426) and lowest saved Brier score (0.1209). Gradient Boosting remained competitive (AUC 0.8377; Brier 0.1224) and became the central audit model in the source project.

## Major audit findings

- **Fairness:** Black-vs-White approval AIR is above 0.80 in the saved GBT run, but Black FPR remains higher than White FPR.
- **Age:** the GBT age audit flags 65-74 and >74 groups below the 0.80 AIR screening level relative to 45-54.
- **Intersectionality:** the source audit finds more concentrated disparities for certain age-by-sex and age-by-race groups.
- **Explainability:** DTI is repeatedly important in LIME / SHAP analyses; the project also examines proxy-risk variables.
- **Robustness:** train-test gaps are small in the source experiment; key train/test PSI checks are 0.0.
- **Security:** label-flip poisoning can shift subgroup behavior while barely changing overall AUC, demonstrating the need for subgroup monitoring.
- **Privacy:** the confidence-based membership inference experiment reports AUC around 0.50.

## Deployment stance

The source project recommends **conditional deployment with active monitoring**, including unresolved fairness review, data provenance / access controls, threshold validation, and defined alert triggers.

This is an academic audit result, not a production lending recommendation or legal conclusion.
