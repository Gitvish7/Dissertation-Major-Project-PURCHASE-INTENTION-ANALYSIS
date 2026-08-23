# Consumer Purchase Intention in E-Commerce: The Role of Online Reviews

A quantitative, survey-based analysis of whether consumers' perceptions of online product reviews predict their purchase intention.

**Module:** BUSI 1783 – Business Analytics Project
**Programme:** MSc Business Analytics, University of Greenwich
**Student:** Vishwakumari Patel (001486172)
**Supervisor:** Dr Azar MahmoumGonbadi
**Project type:** Traditional Research Project

## About this project

This repository contains the full analytical pipeline for a primary survey study of consumer perceptions of online product reviews and their reported purchase intention in e-commerce settings. The questionnaire captured three multi-item attitudinal constructs measured on five-point Likert scales, a single-item measure of review-driven purchase intention, and a set of behavioural and demographic variables.

The analysis is entirely quantitative and proceeds through:

1. Data cleaning and preparation (consent screening, duplicate removal, recoding, missing-value treatment, careless-responding checks)
2. Descriptive statistics and sample profiling
3. Reliability analysis of the multi-item constructs (Cronbach's alpha)
4. Construction and distributional testing of composite scores
5. Correlation analysis (Pearson and Spearman)
6. Simple linear regression
7. Hierarchical multiple linear regression with purchase intention as the dependent variable
8. Full testing of the classical linear regression assumptions
9. Robustness and sensitivity analyses (ordinal logistic regression, bootstrapped confidence intervals, careless-responder exclusion)
10. Supplementary non-parametric group comparisons (Mann-Whitney U, Kruskal-Wallis H)
11. Post-hoc statistical power assessment

## Key findings

- **The measurement instrument is reliable.** All three constructs achieve good internal consistency: Cronbach's alpha of .897 (perceived review quality), .831 (trust in verified-purchase reviews) and .888 (perceived review influence).
- **Consumers value reviews strongly**, but **none of the three attitudinal constructs significantly predicts purchase intention** (all r < .13, p > .35). The full model explains only 10.0% of variance and is not statistically significant, F(3, 50) = 1.86, p = .149. **H1, H2 and H3 are not supported.**
- The apparent negative regression coefficient for perceived review quality is a **suppression artefact** driven by high inter-construct correlation (r = .67–.83), not a genuine effect — confirmed by bootstrap, ordinal logistic, and sensitivity checks.
- The only significant correlate of purchase intention is **behavioural**: habitual review reliance (Spearman's rho = .307, p = .023), not attitudinal belief.
- Achieved statistical power is below the conventional .80 threshold, so null results should be read as inconclusive rather than as evidence of no effect.

Full findings, business recommendations, and limitations are documented in Section 14 of the notebook.

## Repository contents

| File / folder | Description |
|---|---|
| `Purchase_Intention_Analysis.ipynb` | Main analysis notebook (this project) |
| `cleaned_survey_data.csv` | Cleaned analytical dataset |
| `variable_codebook.csv` | Mapping of variable codes to questionnaire wording |
| `table_01`–`table_20` (`.csv`) | Numbered results tables referenced in the dissertation |
| `figures/` | All figures used in the report and poster, exported at 300 dpi |
| `README.md` | This file |

## Reproducing the analysis

1. Clone the repository and open `Purchase_Intention_Analysis.ipynb` in Jupyter.
2. Install dependencies (the notebook also installs `statsmodels` at the top):
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels scipy
   ```
3. Run all cells in order. Each cell writes its corresponding table (`table_01`…`table_20`) and figure to disk, so the full chain of evidence from raw responses to reported conclusion is reproducible end to end.

## Methodology notes

- Likert-scale items are treated as interval-level data for composite scoring and regression, consistent with standard practice in consumer-behaviour research; non-parametric methods are reported alongside as a robustness check given their ordinal origin.
- Missing data is handled via person-mean substitution at the construct level (rather than listwise deletion) given the small sample size.
- Careless/insufficient-effort responding is screened using the longstring index and addressed through transparent flagging plus sensitivity analysis, not silent deletion.

## Limitations

The analysis rests on a small, non-probability convenience sample (n = 55) concentrated among 18–34 year olds resident in India, which limits generalisability. The cross-sectional design precludes causal inference, and the dependent variable is a single self-reported item collected in the same instrument as the predictors, raising the possibility of common method variance.

## License

Add a license of your choice (e.g. MIT) if you intend this repository to be reused by others.
