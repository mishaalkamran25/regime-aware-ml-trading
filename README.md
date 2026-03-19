# A Macro-Driven Approach to Regime-Aware Trading in Finance

A two-stage ML framework combining return prediction and macro-driven gating to improve trading decisions under noisy financial signals.

## Overview
This project investigates whether trading performance can be improved by learning when to act on model predictions, rather than only improving prediction accuracy.

Financial return signals are weak and unstable across market regimes. This work introduces a gating mechanism that controls exposure based on macroeconomic conditions.

## Methodology
- Multi-tower neural network for cross-sectional return prediction  
- Logistic regression gating model using macro features and signal diagnostics  
- Time-series rolling validation to simulate real-world deployment  
- Long–short portfolio construction (top vs bottom decile)

## Key Experiments
- Fixed vs rolling training  
- Binary vs soft gating  
- Macro vs diagnostic feature sets  
- Threshold sensitivity (τ)

## Key Findings
- Fixed training provides more stable performance than rolling retraining  
- Binary gating preserves signal strength better than soft exposure scaling  
- Macro features outperform model diagnostics for gating decisions  
- Optimal threshold (τ ≈ 0.58) balances filtering noisy signals and retaining opportunities  

## Result
Even imperfect regime signals improved outcomes by avoiding large drawdowns, highlighting the importance of selective exposure in weak-signal environments.

## Files
- `Machine_Learning_Final_Project.ipynb` – Full implementation and experiments  
- `Regime-Aware Deep Learning.pdf` – Project presentation  
