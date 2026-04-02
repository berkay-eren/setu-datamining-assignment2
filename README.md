# Predictive Modelling with World Bank & UN HDI Data

This project looks at global development data and tries to understand how different economic and social indicators relate to human development.

The main focus is on predicting life expectancy, classifying countries by HDI level, and exploring how countries group together based on their indicators.

---

## What this project does

There are three main parts:

- Predict life expectancy at birth (regression)
- Predict HDI group (classification)
- Find natural clusters of countries (clustering)

The idea is to go through a full data mining process from raw data to model results.

---

## Data used

The project uses four datasets:

- World Bank indicators (main dataset)
- HDI data by country
- HDI statistical annex (for reference)
- World Bank metadata (to understand indicators)

The World Bank dataset is the most complex one. It includes many indicators over multiple years, and it needed cleaning before it could be used.

---

## Data preparation

Before modelling, several steps were needed:

- Replace missing values ("..") with proper NaN
- Clean column names
- Convert values to numeric
- Remove duplicates and invalid rows
- Choose a single year for modelling (2019)
- Remove indicators with too many missing values
- Reshape the data from long format to wide format
- Merge with HDI data

After this, each country is represented as a single row with multiple indicators.

---

## Regression (Life Expectancy)

The goal here is to predict life expectancy at birth.

Models used:
- Baseline (mean prediction)
- Linear Regression
- Random Forest

Results show that:
- Linear regression already performs well
- Random forest performs better and captures more complex patterns

The most important factors include income, health conditions, birth rates, and access to basic services like water and electricity.

---

## Classification (HDI Group)

This part predicts which HDI category a country belongs to:

- Low
- Medium
- High
- Very High

The model uses the same indicators but removes life expectancy to avoid leakage.

---

## Clustering

Clustering is used to see if countries naturally group in a similar way to HDI categories.

Methods used:
- K-Means
- Gaussian Mixture Models

This helps compare data-driven groupings with official HDI classifications.

---

## Tools

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

---

## Key observations

- 2019 is the most suitable year due to better data availability
- Many indicators are strongly related to life expectancy
- Non-linear models work better than simple linear ones
- Missing data is a major limitation in global datasets
