<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Viz-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly">
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="MIT License">
</p>

<h1 align="center">The Proper EDA</h1>

<p align="center">
  <strong>A 107-cell deep exploratory analysis of 2.26 million Lending Club loans. Distribution fitting, missing data forensics, temporal drift analysis, multivariate structure, credit risk feature screening (WoE/IV/PSI), and portfolio-level analytics - all in one notebook.</strong>
</p>

<p align="center">
  <em>This is what EDA looks like when you treat it as the product, not a checkbox before modeling.</em>
</p>

---

## What This Covers

| Section | What It Does |
|---------|-------------|
| **1. Data Audit** | Schema inspection, dtype conflicts, cardinality analysis, memory profiling, duplicate detection, column taxonomy across 151 features |
| **2. Missing Data Analysis** | Missingness rates by tier, temporal missingness heatmap (schema evolution), co-missingness clustering, missingness-as-signal (does missing predict default?) |
| **3a. Univariate - Continuous** | Distribution fitting (normal, lognormal + KS tests), QQ plots, robust statistics (trimmed mean, MAD, IQR), outlier quantification, violin plots by outcome |
| **3b. Univariate - Categorical** | Frequency analysis, HHI concentration, rare category detection, default rate by category for every key dimension |
| **3c/4. Temporal Analysis** | Origination volume trends, feature drift ridge plots, grade composition over time, vintage default rates, vintage x grade heatmaps, interest rate evolution |
| **5. Bivariate & Conditional** | Spearman correlations, point-biserial associations, conditional distributions, chi-squared tests, grade x purpose interaction heatmap, geographic choropleth |
| **6. Multivariate Structure** | PCA with loading interpretation, KMeans clustering with elbow/silhouette, cluster profiling and grade composition |
| **7. Information Value & WoE** | WoE binning, IV scores for all features, IV classification, WoE monotonicity, Population Stability Index (PSI) across vintages |
| **8. Portfolio Analytics** | Composition by grade/term/purpose, loss severity distributions, PD x LGD x EAD expected loss framework, gross vs net yield analysis, transition matrices, vintage cohort radar charts |

---

## Quick Start

### 1. Clone and install

```bash
git clone https://github.com/lenamonj/proper-eda-analysis.git
cd proper-eda-analysis
pip install -r requirements.txt
```

### 2. Get the data

Download from [Kaggle](https://www.kaggle.com/datasets/wordsforthewise/lending-club) and place the gzipped CSV in `data/`:

```
data/accepted_2007_to_2018Q4.csv.gz
```

### 3. Run

```bash
jupyter notebook proper_eda_analysis.ipynb
```

---

## Dataset

[Lending Club Loan Data](https://www.kaggle.com/datasets/wordsforthewise/lending-club)

- 2.26 million accepted loans, 2007-2018
- 151 features per loan (borrower demographics, credit history, loan terms, payment behavior, hardship/settlement)
- Binary outcome: Fully Paid vs. Charged Off/Default
- CC0 Public Domain license

---

## Dependencies

| Package | Purpose |
|---------|---------|
| `pandas` | Data manipulation |
| `numpy` | Numerical computing |
| `matplotlib` | Static visualizations |
| `seaborn` | Statistical plots and heatmaps |
| `plotly` | Interactive choropleth maps |
| `scipy` | Distribution fitting, statistical tests, clustering |
| `scikit-learn` | PCA, KMeans, preprocessing |
| `kaleido` | Plotly static image export |

---

## Project Structure

```
.
├── proper_eda_analysis.ipynb    # The notebook (107 cells, 8 sections)
├── data/                        # Lending Club data (not tracked in git)
├── requirements.txt             # Python dependencies
├── LICENSE                      # MIT License
└── README.md                    # You are here
```

---

## Design Philosophy

- **No matplotlib defaults.** Custom color palette, consistent typography, styled axes throughout.
- **Every chart has a punchline.** Titles are analytical statements, not labels. Subtitles carry the insight.
- **Missingness is data.** Co-missingness matrices and temporal heatmaps reveal schema evolution, not just cleanup needs.
- **Temporal honesty.** Seasoning bias is called out explicitly. Recent vintages are not compared to seasoned ones without context.
- **Credit-native framing.** WoE/IV/PSI are standard credit risk tools, not generic ML feature selection. The portfolio analytics section uses PD x LGD x EAD, not just accuracy metrics.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

<p align="center">
  <sub>Built with Python and public data. No proprietary tools required.</sub>
</p>
