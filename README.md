# A Macro-Driven Approach to Regime-Aware Trading in Finance

A two-stage machine learning framework combining cross-sectional return prediction with macro-driven gating to improve trading decisions under weak and noisy financial signals.

## Overview
This project studies whether improving *decision rules around predictions* can be more effective than improving prediction accuracy itself.

In empirical asset pricing, return signals are typically weak, unstable, and regime-dependent. We introduce a gating mechanism that conditions trading exposure on macroeconomic state variables, aiming to selectively act on predictions only when signals are more reliable.

## Framework
The model is structured as a two-stage system:

- **Stage 1 (Signal Model):**  
  A multi-tower neural network learns cross-sectional return signals and ranks assets for a long–short portfolio.

- **Stage 2 (Gating Model):**  
  A logistic regression classifier estimates the probability that signals are reliable, using macroeconomic features and signal diagnostics.  
  Exposure is controlled via a threshold-based decision rule.

This separates the problem into:
- *What to trade* (signal generation)  
- *Whether to trade* (decision under uncertainty)

## Experimental Design
We evaluate the framework through a series of controlled experiments:

- Training scheme: fixed vs rolling  
- Exposure control: binary vs soft gating  
- Feature selection: macro vs model diagnostics  
- Threshold sensitivity: τ ∈ [0.50, 0.65]  

Evaluation is conducted using time-series rolling validation and out-of-sample long–short portfolio backtesting.

## Key Findings
- Fixed training produces more stable and consistent performance, while rolling retraining amplifies noise  
- Binary gating outperforms soft exposure scaling by preserving signal strength  
- Macro features dominate gating performance; diagnostics introduce noise and degrade decisions  
- Performance exhibits a non-linear relationship with τ, with an optimum around τ ≈ 0.58  

## Result
Despite imperfect regime classification, gating improves outcomes by asymmetrically reducing exposure during adverse conditions.  
Avoiding large drawdowns contributes more to long-term performance than capturing all upside.

## Limitations
- Weak regime separation leads to noisy gating decisions  
- Conservative thresholding results in missed upside during strong bull periods  
- Performance is sensitive to threshold selection  
- Macro signals introduce lag in adapting to regime shifts  

## Files
- `Machine_Learning_Final_Project.ipynb` – Full implementation and experimental analysis  
- `Regime-Aware Deep Learning.pdf` – Project presentation  
