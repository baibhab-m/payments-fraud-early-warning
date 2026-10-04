# Digital Payments Fraud Detection & Early-Warning Dashboard

Maps to: Fraud Risk Strategy intern role — detection, monitoring, early warning signals, dashboards, digital financial services.

## Dataset
- **IEEE-CIS Fraud Detection** (Kaggle) — e-commerce, device/email info.
- **PaySim** (Kaggle) — synthetic mobile money, closest to UPI-style flows.
- Fallback: credit card fraud (European cardholders, heavily imbalanced).

## Scope
- **EDA + typology analysis** — fraud patterns by transaction type, amount, time of day, new-account behavior, device/email-domain mismatches.
- **Rule-based controls** — velocity rules (>N txns in X min), account drained to zero, first-time beneficiary + high amount. Track **precision, recall, false-positive rate** per rule.
- **ML layer** — Isolation Forest (anomaly detection) + supervised classifier (XGBoost). Class imbalance via class weights / SMOTE. Evaluate with **PR-AUC**, not accuracy.
- **Early-warning dashboard** (Tableau) — daily fraud rate, rule hit rates, alert volume vs. capacity, trend-break alerts.
- **Investigation case notes** on 2–3 flagged accounts.
- **Fraud-lifecycle mapping** — prevent → detect → monitor → investigate → report.

## Structure
```
data/raw/              # IEEE-CIS or PaySim (gitignored)
notebooks/             # 01_eda_typology.ipynb, 02_velocity_rules.ipynb, 03_isoforest_anomaly.ipynb, 04_xgb_supervised.ipynb, 05_case_investigations.ipynb
rules/                 # velocity_rules.yaml — threshold, owner, expected FP rate
tableau/               # fraud_early_warning_dashboard.twbx
docs/                  # fraud_lifecycle_map.md, rbi_digital_fraud_alignment.md
README.md              # this file
```

## Status
Scaffold only — content coming overnight. See commits for progress.

## Resume bullet
> Digital Payments Fraud Detection and Early-Warning System | GitHub, Python, Tableau | 2025
> Engineered velocity/behavioral rules and Isolation Forest + XGBoost models on PaySim/IEEE-CIS data (PR-AUC focus, imbalance handling); built Tableau early-warning dashboard tracking rule hit rates, fraud trends and alert-capacity trade-offs.