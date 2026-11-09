# emerging-market-capital-flow-prediction
Overview

Emerging market economies are periodically exposed to sharp reversals in non-resident portfolio investment, often with consequences for exchange rates, credit conditions, and economic output.

This project examines whether these reversals can be predicted ahead of time using global ("push") and country-specific ("pull") factors.

Using quarterly data from 23 emerging market economies from 2000Q1 onward, I compare two approaches: Logistic Regression, a conventional choice in the early-warning literature, and Random Forest, a more flexible machine learning alternative.

The main focus is on out-of-sample prediction rather than in-sample model fit.

Methodology

Portfolio investment reversals are identified using an expanding-window 10th-percentile threshold based on each country's historical observations.

Both models use macroeconomic and financial indicators observed with a one-quarter lag relative to the outcome.

To evaluate their predictive performance, I use a time-based train/test split and a forward-chaining approach, where models are trained only on information available before the period being predicted.

Results

Both models capture modest predictive signals, with walk-forward AUROC values only slightly above 0.5.

Random Forest performs better at identifying actual reversal events than the primary unbalanced Logistic Regression model, while Logistic Regression achieves higher overall accuracy.

A balanced Logistic Regression specification improves recall and F1-score further, but at a substantial cost to accuracy.

Both models identify global factors, particularly US monetary policy and oil prices, as important predictors of reversal risk. Foreign exchange reserves relative to GDP also emerge as influential, although the direction of the Logistic Regression coefficient is not consistent with theoretical expectations.

Conclusion

The results suggest that Logistic Regression and Random Forest offer limited but non-trivial value as early-warning tools for portfolio investment reversals.

Neither model provides strong predictive performance, and the results are affected by data availability, class imbalance, and model specification.

An important finding is the difference between the single train/test split and the forward-chaining evaluation, highlighting why evaluation design matters as much as model choice when predicting rare financial events.
