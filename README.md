# Special programming languages

Topic: "Visualization of statistical tests"
Bulatova Viktoriia, Popp Sofia, SA-32

## RR_PROJECT_BULATOVA_POPP

A Python statistical test visualization project designed to help analyze and visualize the results of statistical methods such as t-tests, ANOVA, and others.

## Description

RR_PROJECT_BULATOVA_POPP is a comprehensive Python library designed for automated statistical hypothesis testing and data visualization. The package simplifies the decision-making process by automatically selecting the appropriate parametric or non-parametric test based on the data characteristics, including normality and sample size. It also provides robust visualizations to ensure clear and insightful presentation of results.

Main features:
1. Automatic Test Selection
- Automatically chooses between parametric and non-parametric tests based on:
    - Normality of data, determined using Shapiro-Wilk or D’Agostino-Pearson tests depending on the sample size.
    - Homogeneity of variances for multi-group tests.
    - Supports a wide range of statistical tests:
    - Paired samples: Paired t-test, Wilcoxon signed-rank test.
    - Independent samples: Independent t-test, Mann-Whitney U test.
    - Multi-group comparisons: One-way ANOVA, Alexander-Govern test, Kruskal-Wallis test.
2. Assumption Checks
- Normality Testing:
    - Shapiro-Wilk test for small samples.
    - D’Agostino-Pearson test for larger datasets.
    - Homoscedasticity (Equal Variances):
    - Bartlett’s test for verifying variance equality across groups.
3. Descriptive Statistics
- Provides detailed summaries for each sample:
    - Mean, median, mode, variance, standard deviation.
    - Skewness, kurtosis, range, minimum, and maximum.
4. Advanced Visualizations
- Visualizations are integrated into the analysis to ensure intuitive understanding:
    - Histograms with KDE: Displays data distributions and overlays the ideal normal curve.
    - Q-Q Plots: For assessing normality.
    - Boxplots: Highlights variability and spread across groups.
    - Joyplots: Overlays group distributions, emphasizing mean or median values for quick interpretation.
    - Custom Visualization for Differences: Specialized plots for paired tests, showing distributions and differences between samples.

## Installation

To install this package, use `pip install rr_project_bulatova_popp` 

##  Examples 

### Example 1

```python
from rr_project_bulatova_popp import PairedTtest

df = pd.read_csv('..\\Datasets\\dataset_1.csv') 

paired_test = PairedTtest(df, ['col1', 'col2'])

paired_test.normality_visualization()
```
__Result:__

![Example 1](images/ex1.jpg)

### Example 2

```python
from rr_project_bulatova_popp import PairedTtest

df = pd.read_csv('..\\Datasets\\dataset_1.csv') 

multi_group1 = MultiGroupTest(df, ['sem2_alc3', 'sem2_alc2', 'sem2_alc5'])

multi_group1.run_test()
```
__Result:__
```
---The Shapiro-Wilk normality test has been performed---

          sem2_alc3 sem2_alc2 sem2_alc5
stat       0.958085  0.954866  0.940237
p_value     0.31377  0.261891  0.112078
is_normal      True      True      True
All THE SAMPLES ARE NORMALLY DISTRIBUTED

---The one-way ANOVA test has been performed---

H0: Two or more groups have the same population mean
```
![Example 1](images/ex2.jpg)