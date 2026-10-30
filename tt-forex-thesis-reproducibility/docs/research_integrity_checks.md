# Required checks before public release

1. Review every notebook cell for passwords, API keys, usernames, local paths, personal emails, student identifiers, proprietary code or institution-restricted data. This package has not been manually verified safe for public release.
2. Check the original CBSL, IMF, World Bank, FRED, and other data-provider terms before distributing source data. The original integrated Excel datasets are deliberately excluded.
3. Verify licenses for all copied code, data and figures; do not imply permission from source attribution alone.
4. Retain the true original outputs and provenance; this package has source code cells with output displays stripped, not independently re-executed experiments.
5. Record versions, seeds and machine environment; ensure actual source notebooks do not depend on uncommitted `utils.py` or hard-coded Windows paths.
6. Verify published scripts use target-date alignment, point-in-time inputs and training-only model selection; do not claim the code is independently audited or fully reproducible until tested.
7. Keep the 2024–2025 holdout frozen, and distinguish its chosen RW/ML hybrid from earlier development hybrids.
8. Do not describe numerical performance gains as statistically proven. Keep complete statistical test outputs available for supervisor examination even if the main thesis omits them.
9. Keep the 12C corrected volatility matched-origin results distinct from earlier notebook 13 outputs, including coverage limitations.
10. If repository visibility changes from private to public, perform a second full review.
