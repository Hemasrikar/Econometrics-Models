# Financial-Econ-Models


### 5-Minute Returns: Jump Detection

- Intraday return construction from 5-min IBM price data (CSV input)
- Diurnal (time-of-day) variation estimation
- Bipower variation (BV) as a jump-robust volatility measure
- Jump detection via a local threshold
- Jump vs. diffusive returns and their densities

### 5-Minute High-Frequency Volatility Analysis

- Diurnal (time-of-day) variation
- Bipower Variation (BV)
- Jump-robust Truncated Variation (TV)
- Theoretical and Bootstrap 95% confidence intervals
- Annualised daily volatility plots

### GMM Estimation for MA(1) and AR(1) Models

- Time series parameter estimation via Generalised Method of Moments
- Matches three moment conditions: mean, second moment, and first-order autocovariance
- MA(1) model: mean, variance, and lag-1 autocovariance moments
- AR(1) model: unconditional moments derived from stationarity conditions
- Stationarity constraints enforced (|θ| < 1, |φ| < 1) via trust-region optimisation
- Identity weighting matrix (first-step GMM)
- Side-by-side summary of both sets of estimates

# Asset Pricing Factor Analysis
 
Two Jupyter notebooks implementing and comparing factor models for cross-sectional asset pricing using the **Fama-Macbeth regression** framework on 25 Fama-French size/BEME portfolios.
 
## Notebooks
 
**`principal_component_analysis.ipynb`** - Factor construction
- Computes excess returns (25 portfolios minus RF)
- Builds **in-sample PCA factors**: eigendecomposition of the full-sample covariance matrix, top 3 PCs
- Builds **out-of-sample PCA factors**: eigenvectors estimated on odd months, applied to even months (and vice versa)
- Visualises covariance matrices and cross-factor correlation heatmap
 
**`asset_pricing_tests.ipynb`** - Model testing & comparison
- Runs Fama-Macbeth two-pass regressions for four factor sets:
  - Fama-French 3 factors (Mkt-RF, SMB, HML)
  - Macroeconomic factors (Div growth, DEF, TERM)
  - In-sample PC factors
  - Out-of-sample PC factors
- Compares models on time-series R², cross-sectional R², and pricing errors (α)
- Checks multicollinearity via VIF
- Exports betas, gammas, and R² tables to `asset_pricing_results/`
 
## Data
 
Place `Data_FE.xlsx` in a `data/` folder. Required sheets:
- `25 Size and BEME portfolios`
- `Fama-French factors`
- `Macroeconomic factors`