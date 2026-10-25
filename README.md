# Heart-Disease-EDA
Exploratory Data Analysis of Heart Disease Data using Python , Pandas , Matplotlib and Seaborn .

# ❤️ Heart Disease Exploratory Data Analysis (EDA)

## 📌 Project Overview

This project presents an exploratory data analysis (EDA) of a heart disease dataset containing 303 observations and 13 clinical features.

The main objective is to understand the dataset's structure and quality, investigate feature distributions, explore relationships between clinical variables, and identify patterns associated with heart disease.

The analysis uses statistical summaries and data visualization to examine demographic characteristics, clinical measurements, potential outliers, correlations, and differences between subgroups.

This project focuses on data analysis and interpretation rather than developing machine learning models.

## 🎯 Project Objectives

- Inspect the dataset's structure, dimensions, and data types.
- Assess data quality by checking for missing values and duplicate records.
- Explore numerical and categorical feature distributions.
- Analyze central tendency, variability, and skewness.
- Identify potential outliers using the Interquartile Range (IQR) method.
- Investigate relationships between age and clinical measurements.
- Explore correlations between features and heart disease status.
- Compare clinical characteristics across sexes and age groups.
- Examine differences between individuals with and without heart disease.
- Summarize key findings and limitations of the analysis.

## 📊 Dataset Description

The dataset contains 303 observations, 13 input features, and one target variable.

| Property | Description |
|---|---|
| Total observations | 303 |
| Input features | 13 |
| Target variable | `target` |
| Missing values | None detected |
| Exact duplicate rows | 1 detected |
| Analysis type | Exploratory Data Analysis |

The dataset includes demographic information, clinical measurements, and categorical indicators related to heart disease.

### Feature Description

| Feature | Description | Type |
|---|---|---|
| `age` | Age of the individual | Numerical |
| `sex` | Sex of the individual | Binary categorical |
| `cp` | Chest pain type | Categorical |
| `trestbps` | Resting blood pressure (mm Hg) | Numerical |
| `chol` | Serum cholesterol (mg/dL) | Numerical |
| `fbs` | Fasting blood sugar indicator | Binary categorical |
| `restecg` | Resting electrocardiographic results | Categorical |
| `thalach` | Maximum heart rate achieved | Numerical |
| `exang` | Exercise-induced angina | Binary categorical |
| `oldpeak` | ST depression induced by exercise relative to rest | Numerical |
| `slope` | Slope of the peak exercise ST segment | Categorical |
| `ca` | Number of major vessels colored by fluoroscopy | Categorical |
| `thal` | Thalassemia-related test result | Categorical |
| `target` | Heart disease status | Binary categorical |

### Categorical Encoding

The following encodings are used in this analysis.

**Sex (`sex`)**
- `0`: Male
- `1`: Female

**Target (`target`)**
- `0`: No heart disease
- `1`: Heart disease present

**Chest Pain Type (`cp`)**
- `0`: Typical angina
- `1`: Atypical angina
- `2`: Non-anginal pain
- `3`: Asymptomatic

**Fasting Blood Sugar (`fbs`)**
- `0`: Fasting blood sugar at or below the dataset's threshold
- `1`: Fasting blood sugar above the dataset's threshold

**Resting ECG (`restecg`)**
- `0`: Normal
- `1`: ST-T wave abnormality
- `2`: Probable or definite left ventricular hypertrophy

**Exercise-Induced Angina (`exang`)**
- `0`: No
- `1`: Yes

**Slope (`slope`)**
- `0`: Upsloping
- `1`: Flat
- `2`: Downsloping

The categorical codes for `ca` and `thal` should be interpreted according to the dataset's original documentation.

## 🛠️ Tools and Technologies

The project uses the following Python libraries and tools:

- **Python** — General-purpose programming and data analysis.
- **Pandas** — Data manipulation, grouping, and statistical summaries.
- **NumPy** — Numerical operations and array manipulation.
- **Matplotlib** — Plotting and data visualization.
- **Seaborn** — Statistical visualization.
- **Jupyter Notebook** — Interactive analysis and documentation.

## 🔍 Analysis Workflow

### 1. Data Inspection and Quality Assessment

The initial analysis examines the dataset's structure and reliability.

Tasks include:
- Inspecting the first observations and column names.
- Examining data types and descriptive statistics.
- Checking unique values in individual features.
- Identifying missing values.
- Detecting exact duplicate rows.

The dataset contains no missing values. However, one exact duplicate row was detected and should be investigated before any data-cleaning decision is made.

### 2. Univariate Analysis

Univariate analysis explores individual features independently.

The analysis includes:
- Examining numerical feature distributions.
- Analyzing categorical feature frequencies.
- Calculating descriptive statistics.
- Investigating the age distribution.
- Examining the distribution of sex and heart disease status.
- Exploring the distributions of chest pain type, fasting blood sugar, exercise-induced angina, and other categorical features.

Histograms and frequency plots are used to identify common values, distribution shapes, and imbalances between categories.

### 3. Outlier Detection

Potential outliers are investigated in selected numerical features using the Interquartile Range (IQR) method.

The analysis considers:
- Resting blood pressure (`trestbps`)
- Serum cholesterol (`chol`)
- Maximum heart rate (`thalach`)
- ST depression (`oldpeak`)

The IQR method identifies observations outside the interval:

- Lower fence: Q1 − 1.5 × IQR
- Upper fence: Q3 + 1.5 × IQR

The following numbers of potential outliers were identified in the notebook:

| Feature | Potential outliers |
|---|---:|
| `trestbps` | 9 |
| `chol` | 5 |
| `thalach` | 1 |
| `oldpeak` | 5 |

These observations are flagged for further investigation rather than automatically classified as errors.

Box plots and individual data points are used to examine the distributions and visualize potential outliers.

### 4. Age-Based Analysis

Age is examined in relation to several demographic and clinical characteristics.

The analysis includes:
- Investigating the distribution of age.
- Examining age frequencies.
- Exploring age distributions across sexes.
- Comparing clinical measurements across age groups.
- Investigating relationships between age and resting blood pressure, cholesterol, maximum heart rate, and ST depression.

Age groups are defined as follows:

- 29–38
- 39–48
- 49–58
- 59–68
- 69–78

The analysis uses bar charts, scatter plots, histograms, and hexbin plots to investigate patterns and concentrations in the data.

### 5. Categorical Feature Analysis

Several categorical variables are explored in relation to age and demographic characteristics.

These include:
- Chest pain type (`cp`)
- Fasting blood sugar (`fbs`)
- Exercise-induced angina (`exang`)
- Thalassemia-related results (`thal`)

Grouped bar charts are used to compare category frequencies across ages and sexes.

The analysis also examines how the distribution of heart disease status varies across demographic subgroups.

### 6. Relationship Between Age and Clinical Measurements

Scatter plots, hexbin plots, and regression plots are used to explore relationships between age and selected numerical features.

The variables examined include:
- `trestbps`
- `chol`
- `thalach`
- `oldpeak`

Pearson correlation coefficients are calculated to quantify linear associations.

The analysis also compares these relationships between:
- Male and female individuals.
- Individuals with and without heart disease.

### 7. Correlation Analysis

A correlation matrix and heatmap are used to investigate relationships among numerical and encoded categorical variables.

The analysis examines:
- Correlations between individual features and the target.
- Relationships between clinical measurements.
- Potentially strong associations between selected variables.

Because some categorical variables are represented by numerical codes, their Pearson correlations require cautious interpretation. A correlation between encoded categories does not necessarily represent a meaningful linear relationship.

### 8. Heart Disease Status Analysis

The dataset is divided according to the target variable:

- `target = 0`: No heart disease
- `target = 1`: Heart disease present

The analysis compares selected clinical measurements across the two groups.

Features examined include:
- Age
- Resting blood pressure
- Cholesterol
- Maximum heart rate
- ST depression

Box plots, scatter plots, histograms, and subgroup comparisons are used to explore differences in feature distributions.

### 9. Sex-Specific Analysis

The analysis compares selected features between male and female individuals.

The following encoding is used consistently:

- `sex = 0`: Male
- `sex = 1`: Female

The analysis investigates:
- Differences in demographic distributions.
- Variation in clinical measurements.
- Relationships between age and numerical features.
- Differences in feature distributions by heart disease status.
- Patterns within age groups.

These comparisons help identify subgroup differences within the dataset, while accounting for the unequal numbers of male and female observations.

### 10. Distribution Shape and Skewness

Skewness is calculated for selected numerical variables to investigate departures from symmetry.

The notebook examines:
- `age`
- `trestbps`
- `chol`
- `thalach`
- `oldpeak`

Histograms and density curves are used to visualize distribution shapes and investigate skewness.

## 📈 Key Findings

The following findings summarize the numerical results and patterns investigated in the notebook.

### 1. Dataset Quality

- The dataset contains 303 observations.
- No missing values were detected.
- One exact duplicate row was identified.
- The duplicate should be investigated before deciding whether to remove it.

### 2. Age Distribution

- Age ranges from approximately 29 to 77 years.
- The mean age is approximately 54.4 years.
- The median age is approximately 55 years.
- The age distribution is relatively concentrated around middle age, with a slight negative skewness of approximately −0.20.

### 3. Sex Distribution

The dataset contains an unequal number of male and female observations.

| Sex | Number of individuals | Percentage |
|---|---:|---:|
| Male | 96 | 31.7% |
| Female | 207 | 68.3% |

Females represent approximately two-thirds of the observations. This imbalance should be considered when interpreting sex-specific comparisons.

### 4. Heart Disease Distribution

The target distribution is:

| Heart disease status | Target value | Number of individuals | Percentage |
|---|---:|---:|---:|
| No heart disease | 0 | 138 | 45.5% |
| Heart disease present | 1 | 165 | 54.5% |

The two target groups are relatively similar in size, although they are not perfectly balanced.

### 5. Outlier Analysis

The IQR method identified potential outliers in all four numerical features examined.

| Feature | Number of potential outliers |
|---|---:|
| Resting blood pressure (`trestbps`) | 9 |
| Cholesterol (`chol`) | 5 |
| Maximum heart rate (`thalach`) | 1 |
| ST depression (`oldpeak`) | 5 |

The findings highlight the importance of investigating unusual observations in clinical measurements before drawing conclusions from the distributions.

### 6. Correlation with Heart Disease Status

The notebook reports the following Pearson correlations with the target variable:

| Feature | Correlation with `target` |
|---|---:|
| `exang` | −0.44 |
| `cp` | +0.43 |
| `oldpeak` | −0.43 |
| `thalach` | +0.42 |
| `ca` | −0.39 |
| `slope` | +0.35 |
| `thal` | −0.34 |
| `sex` | −0.28 |
| `age` | −0.23 |
| `trestbps` | −0.14 |
| `chol` | −0.09 |
| `fbs` | −0.03 |

These values describe associations with the encoded target variable. The direction and magnitude of correlations involving categorical features depend on their numerical encoding and should not automatically be interpreted as clinical effects.

The correlations are exploratory and do not establish causation or prove that a feature is clinically useful for diagnosis.

### 7. Relationships Between Features

The notebook also identifies several correlations between features:

| Feature pair | Reported correlation |
|---|---:|
| `slope` and `oldpeak` | −0.58 |
| `age` and `thalach` | −0.40 |
| `exang` and `cp` | −0.39 |
| `thalach` and `slope` | +0.39 |
| `thalach` and `exang` | −0.38 |
| `oldpeak` and `thalach` | −0.34 |

These associations provide a basis for further investigation into relationships among the dataset's clinical variables.

### 8. Age and Cholesterol

The Pearson correlation between age and cholesterol is approximately +0.214.

This indicates a weak positive linear association in the analyzed dataset.

The scatter plot also reveals considerable variation in cholesterol values at similar ages, along with an extreme high value that warrants investigation.

### 9. Sex-Specific Patterns

The notebook explores differences between male and female individuals across several numerical features.

The analysis includes resting blood pressure, cholesterol, maximum heart rate, and ST depression.

Because the numbers of male and female observations differ substantially, subgroup distributions should be interpreted with caution. Differences observed in the sample do not necessarily imply that the same patterns apply to the wider population.

## ⚠️ Limitations

- The dataset contains only 303 observations.
- The dataset has a substantial imbalance in the number of male and female observations.
- One exact duplicate row was detected and requires investigation.
- Potential outliers may represent valid observations and should not automatically be removed.
- Correlation does not imply causation.
- Pearson correlation may be misleading when applied to numerically encoded categorical variables.
- Observed differences between groups may be influenced by sample composition and unequal group sizes.
- Findings from this dataset should not automatically be generalized to other populations.
- Exploratory patterns do not establish the diagnostic value of individual features.

## 📁 Repository Structure

The repository can be organized as follows:

```text
Heart-Disease-EDA/
├── README.md
├── heart_EDA_without_ML.ipynb
├── heart.csv
└── heart-rate-1.jpg
```

**File descriptions:**

- `README.md` — Project overview, methodology, findings, and limitations.
- `heart_EDA_without_ML.ipynb` — The complete exploratory data analysis.
- `heart.csv` — The dataset used in the notebook.
- `heart-rate-1.jpg` — An image referenced in the notebook.

Include `heart.csv` only if you are permitted to redistribute the dataset. Include the image only if it is required by the notebook.

## 🚀 How to Run the Project

### Requirements

- Python 3
- Jupyter Notebook or JupyterLab

### Install Dependencies

Install the main libraries using:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the Notebook

1. Clone or download the repository.
2. Install the required dependencies.
3. Ensure that `heart.csv` and any required image files are available at the paths referenced in the notebook.
4. Open `heart_EDA_without_ML.ipynb` in Jupyter Notebook or JupyterLab.
5. Run the cells in order to reproduce the analysis.

## ⚕️ Disclaimer

This project is intended for educational and analytical purposes only. The results describe patterns observed in the dataset and should not be used for medical diagnosis or clinical decision-making.

## 👤 Author

**[Your GitHub Username]**
