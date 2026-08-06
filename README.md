### Healthcare ETL Data Pipeline & Clinical Risk Visualizer

### Project Overview
Engineered an automated Python-based healthcare data pipeline that ingests, audits, and transforms patient examination records into structured clinical risk features. The architecture implements strict data quality validation rules, percentile outlier filtering, and normalized feature engineering to serve downstream epidemiological analytics and exploratory health visualizations.

### Applied Data Engineering & Analytical Principles

#### Data Ingestion & Schema Quality Auditing
* **Pre-Processing & Validation:** Built automated ingestion routines using `pandas` with explicit line-parsing error controls to enforce schema integrity and handle malformed input records upon ingestion.
* **Domain Data Quality Rules:** Applied clinical business rules to filter impossible measurement anomalies (e.g., stripping records where diastolic blood pressure exceeds systolic blood pressure).

#### ETL Transformation & Feature Engineering
* **Healthcare Metric Normalization:** Implemented vectorized transformation routines to derive Body Mass Index ($\text{BMI}$) metrics and encode clinical risk thresholds into standardized binary indicators (`overweight`).
* **Scale Standardization:** Re-mapped ordinal clinical scales (`cholesterol`, `glucose`) into unified binary representations ($0$ for normal, $1$ for elevated) to streamline downstream statistical transformations.
* **Statistical Anomaly Trimming:** Applied percentile-based filtering ($2.5\text{th}$ to $97.5\text{th}$ percentiles) across body measurements (`height`, `weight`) to remove extreme physical outliers before model ingestion.

#### Exploratory Data Analytics & Storytelling
* **Multivariate Categorical Slicing:** Transformed wide relational datasets into long-format structures using `pd.melt()` to build categorical comparisons (`seaborn.catplot`) of binary risk factors across cardiovascular disease cohorts.
* **Correlation Diagnostics:** Calculated masked upper-triangle correlation matrices (`seaborn.heatmap`) to evaluate multi-metric co-occurrence and identify potential feature redundancy across patient demographics.
