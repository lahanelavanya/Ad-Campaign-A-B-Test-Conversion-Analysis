# Marketing A/B Testing: Ad vs PSA Conversion Analysis

A statistical analysis of a marketing A/B test comparing **advertisement (Ad)** exposure with **public-service announcement (PSA)** exposure using user conversion as the primary outcome.

The project applies exploratory data analysis, hypothesis testing, effect-size estimation, confidence intervals, power analysis, and exposure-based segmentation to evaluate the experiment and identify areas for future experimentation.

## Project Overview

The main question addressed in this project is:

> Does exposure to the advertisement produce a different conversion rate compared with exposure to the PSA?

The analysis focuses on two experimental groups:

* **Ad** — users exposed to the advertisement
* **PSA** — users exposed to the public-service announcement

The primary outcome variable is **conversion**.

## Hypotheses

The primary statistical test evaluates whether the conversion rate differs between the two experimental groups.

The null hypothesis is:

$$
H_0: p_{Ad} = p_{PSA}
$$

The alternative hypothesis is:

$$
H_1: p_{Ad} > p_{PSA}
$$

where:

* \(p_{Ad}\) = conversion rate for the Ad group
* \(p_{PSA}\) = conversion rate for the PSA group

The analysis uses a significance level of:

$$
\alpha = 0.05
$$

and a target statistical power of:

$$
Power = 0.80
$$

## Analysis Workflow

```text
Raw Data
   │
   ▼
Data Quality Checks
   │
   ▼
Exploratory Data Analysis
   │
   ▼
Ad vs PSA Conversion Analysis
   │
   ├── Conversion Rates
   ├── Hypothesis Test
   ├── P-Value
   ├── Effect Size
   ├── Confidence Intervals
   └── Odds Ratio
   │
   ▼
Power / Sample Size Analysis
   │
   ▼
Exposure Analysis
   │
   ├── Exposure Day
   ├── Exposure Time
   └── Total Ad Exposure
   │
   ▼
Interpretation & Future Experiments
```

## Statistical Methods

### Conversion Rate

Conversion rate is calculated as:

$$
Conversion\ Rate =
\frac{Number\ of\ Conversions}{Number\ of\ Users}
$$

Conversion rates are calculated separately for the Ad and PSA groups.

### Two-Sample Proportion Test

A one-sided two-sample z-test for proportions is used to evaluate whether the Ad group has a higher conversion rate than the PSA group.

The analysis reports:

* Z-statistic
* P-value
* Statistical decision at \(\alpha=0.05\)

### Effect Size

The analysis goes beyond statistical significance by estimating the magnitude of the observed difference.

The following measures are considered:

* Absolute conversion-rate difference
* Relative conversion-rate lift
* Odds ratio
* 95% confidence intervals

Absolute difference:

$$
\Delta p = p_{Ad} - p_{PSA}
$$

Relative lift:

$$
Relative\ Lift =
\frac{p_{Ad}-p_{PSA}}{p_{PSA}}
$$

### Power and Sample Size

A power analysis is performed to estimate the sample size required for a future experiment.

The analysis uses:

* 5% significance level
* 80% statistical power
* Equal allocation between groups
* Baseline conversion rate from the PSA group
* Observed conversion rate from the Ad group as the target effect

This calculation is intended for **future experiment planning** rather than as a substitute for prospective power analysis.

## Exposure Analysis

The project also investigates whether conversion behavior varies according to advertising exposure.

### Exposure Day

Users are grouped according to their most frequent ad-exposure day.

For each day, the analysis examines:

* Number of users
* Number of conversions
* Conversion rate

A chi-square test of independence is used to examine the relationship between exposure day and conversion.

Cramér's V is also calculated to quantify the strength of association.

These analyses are exploratory and should not automatically be interpreted as causal effects.

### Exposure Time

Ad exposure hours are grouped into broader time periods:

* Morning
* Afternoon
* Evening
* Night

Conversion rates are then compared across these time periods.

A chi-square test is used to examine the association between exposure time and conversion.

### Total Ad Exposure

The project also compares observed advertising exposure between converted and non-converted users.

The analysis examines:

* Number of observations
* Mean ad exposure
* Median ad exposure
* Standard deviation

The distribution is visualized to identify potential relationships between exposure volume and conversion.

Because exposure is an observed behavioral variable, this analysis should be interpreted as descriptive rather than causal.

## Data Validation

Before statistical analysis, the notebook performs data-quality checks including:

* Dataset dimensions
* Column structure
* Missing values
* Duplicate user IDs
* Valid experimental groups
* Valid conversion values

Assertions are used where appropriate to ensure the dataset satisfies the expected structure.

## Project Structure

```text
marketing-ab-testing-ad-vs-psa/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── ab_test_ad_campaign.ipynb
│
├── data/
│   └── marketing_AB.csv
│
└── figures/
    └── ...
```

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/marketing-ab-testing-ad-vs-psa.git
cd marketing-ab-testing-ad-vs-psa
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it.

### Windows

```bash
.venv\Scripts\activate
```

### macOS / Linux

```bash
source .venv/bin/activate
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
notebooks/ab_test_ad_campaign.ipynb
```

## Dependencies

The project uses:

* Python
* Pandas
* NumPy
* SciPy
* Statsmodels
* Matplotlib
* Seaborn
* Jupyter Notebook

See `requirements.txt` for the complete dependency list.

## Interpretation

The primary analysis evaluates the observed difference between the Ad and PSA experimental groups.

The exposure-day and exposure-time analyses are secondary observational analyses. They are useful for identifying patterns and generating hypotheses for future experiments, but they should not by themselves be interpreted as evidence that changing exposure timing will cause conversion to change.

Similarly, a statistically significant result does not necessarily imply that the effect is large enough to be commercially meaningful.

## Limitations

Several limitations should be considered:

* Secondary exposure analyses are observational.
* Observed advertising exposure may be related to user engagement or other behavioral characteristics.
* Multiple exploratory comparisons can increase the probability of false-positive findings.
* Retrospective power calculations are not a replacement for prospective experiment planning.
* Statistical significance and practical/business significance are different concepts.
* The analysis focuses primarily on conversion rather than downstream outcomes such as revenue, retention, or customer lifetime value.

## Future Experiments

Potential follow-up experiments could investigate:

* Optimal advertising exposure timing
* Exposure frequency
* Different advertising creatives
* Interaction between exposure frequency and timing
* User-level engagement segments
* Alternative campaign designs

A future experiment should ideally pre-specify:

1. Primary metric
2. Null and alternative hypotheses
3. Minimum detectable effect
4. Sample size
5. Statistical power
6. Treatment allocation
7. Experiment duration
8. Significance threshold
9. Analysis methodology

## Technologies

```text
Python
Pandas
NumPy
SciPy
Statsmodels
Matplotlib
Seaborn
Jupyter Notebook
```

## Author

**Lavanya Yogedra Lahane**

2023epb1271@iitrpr.ac.in

Indian Institute of Technology Ropar

---
