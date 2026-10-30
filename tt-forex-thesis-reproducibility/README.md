# Multi-Currency Telegraphic Transfer Rate Forecasting in Sri Lanka

**Research reproducibility companion** for the thesis *An AI-Based Framework for Forecasting Multi-Currency Telegraphic Transfer Rates and Supporting Micro-Forex Decisions in Sri Lanka* (KDU, 2026). This repository archives **research code and selected saved outputs**. It is not a live foreign-exchange trading system.

## Research scope

- TT midpoint exchange rates: USD/LKR, GBP/LKR, EUR/LKR, JPY/LKR.
- Horizons: 1, 3 and 7 subsequent weekday observations (not necessarily official bank business days).
- Development comparisons: 2019–2023, including Sri Lanka's 2022 crisis.
- Locked point-forecast holdout: 2024–2025, kept separate from tuning.
- Principal benchmarks: Naive Random Walk for point forecasts and EWMA for conditional-volatility forecasts.

## Repository structure

| Folder | Purpose |
|---|---|
| `notebooks/` | Selected, deduplicated notebook source cells; saved displays stripped for Git readability |
| `results/development/` | Benchmark, statistical and feature-selection CSV outputs |
| `results/audit/` | Selected corrected volatility, coverage, provenance and limitation records |
| `docs/source_notebook_manifest.csv` | Original notebook filename and SHA-256 for provenance |
| `docs/research_integrity_checks.md` | Items to verify before public publication |
| `docs/thesis_appendix_text.md` | Suggested thesis appendix citation |

## Suggested notebook reading order

1. `01_data_preparation`, `02_targets_and_features`, `03_eda_diagnostics`.
2. `04_random_walk`, `05_statistical_models`, `06_machine_learning`.
3. `07_selective_rw_hybrid`, `08_adaptive_ensemble`, `09_online_hybrid_original`, `09b_online_hybrid_fs_safe`.
4. `10_h3_hybrid`, `10b_h3_feature_selection`, `11_lstm_gru_rw_correction`, `11b_regime_gated_dl`.
5. `12_garch_volatility`, `12b_regime_robust_volatility`, `12c_corrected_volatility_validation`, `13_legacy_volatility_sensitivity`.
6. `14_development_model_selection` and finally `15_locked_holdout` (the frozen final test).

**Important:** These are experimental notebooks, not yet a verified one-click runnable pipeline. Code assumes local files and may refer to unprovided source data, utilities, or paths. Do not execute all notebooks blindly or re-tune models using 2024–2025 holdout results.

## Installing a working environment

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m jupyter lab
```

Some deep-learning notebooks may need additional packages after checking the original imports. Requirements are suggested, not a frozen, tested environment.

## Research evidence and interpretation

- Forecast skill must be calculated on **identical target dates** relative to Random Walk.
- Development-stage model selection and the separate locked holdout are not interchangeable model evaluations.
- Volatility QLIKE improvements refer to the matched, eligible observations; compare coverage as well as loss.
- Numerical improvements alone do not establish statistically reliable superiority.
- `09b_online_hybrid_fs_safe` is a separate feature-selection experiment; it must not be described as the original online-hybrid model.
- `13_legacy_volatility_sensitivity` is not interchangeable with corrected `12c_corrected_volatility_validation`.

## Raw data and privacy

The original source datasets, bank quotations, project reports, supervisor correspondence and dashboard with potential local metadata **are intentionally excluded**. Before making this repository public, check data redistribution rights and inspect every notebook for secrets or identifying information.

## Academic citation

Cite the repository URL and a fixed tagged release or commit hash in the thesis Appendix. Replace this sentence with the actual link after publishing.

**Status:** Curated archival starter. Research code has not been re-executed end to end as part of this package.
