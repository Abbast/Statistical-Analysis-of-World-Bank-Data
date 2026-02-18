# Capstone Project — Statistical Analysis of World Bank Data (Capstone_1.ipynb)

This repository explores indicators from the World Bank's Worldwide Bureaucracy Indicators (WWBI) dataset. The notebook is capstone analysis that focuses on gender-related labor market indicators across countries, with a primary focus on European Union member states.

Notebook permalink:
https://github.com/Abbast/Statistical-Analysis-of-World-Bank-Data/blob/6d8a4c1d407fa9014734451db36fa6c7b59394cc/Capstone_1.ipynb

Data source:
- Worldwide Bureaucracy Indicators (WWBI) — World Bank Data Catalog  
  https://datacatalog.worldbank.org/dataset/worldwide-bureaucracy-indicators

Raw CSV used by the notebook:
- https://raw.githubusercontent.com/Abbast/Thinkfulta18/main/WWBIData.csv

## Project goal / Research questions

Primary question
- On average, is there a difference in the female share of paid private sector employees in European Union member nations between 2012 and 2017?

Secondary (time-permitting)
- On average, is there a difference in the female-to-male wage ratio in the private sector of EU member nations between 2000 and 2018?

## What the notebook does (high level)

- Loads the WWBI dataset (CSV hosted in the Thinkfulta18 repository).
- Inspects basic structure and contents (shape, head of frame).
- Identifies and reports missing values and superficial data-quality issues.
- Filters the data to relevant indicators such as:
  - "Females, as a share of private paid employees" (Indicator Code: BI.PWK.PRVS.FE.ZS)
  - (Planned) indicators for female-to-male wage ratio, etc.
- Performs exploratory plots and summary statistics (Seaborn / Matplotlib).
- Performs normality checks (e.g., SciPy normaltest and Shapiro–Wilk) and proceeds with appropriate statistical testing to compare means across years or groups.

## Notable findings / status (from the notebook)
- The dataset contains many missing values; the loaded CSV has rows with numerous NaNs.
- The notebook extracts the "Females, as a share of private paid employees" indicator and begins the analysis pipeline for the main research question.
- Additional cleaning and careful subsetting (EU membership filtering, handling missing values across years) are required before the final hypothesis tests.

## Dependencies

The notebook uses the following Python libraries:
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- jupyter (for local execution)

## Known issues and suggestions

- Data completeness: Many indicators and country-year combinations are NaN. Before performing hypothesis tests, carefully select countries and years with sufficient non-missing observations.
- EU membership filtering: The notebook references EU member nations in the research question. You will need a list of EU member country names or ISO codes to filter the WWBI data correctly (this step is not fully automated in the notebook).
- Indicator consistency: Make sure the indicator names/codes match exactly (strings in the source CSV) before filtering; indicator codes are more robust than names.
- Column "Unnamed: 23": This trailing column appears empty and can be removed.
- Reproducibility: Consider adding a requirements.txt or environment.yml with pinned versions if you need exact reproducibility.

## Suggested next steps (to complete the analysis)

1. Build or import a list of EU member countries (for the target comparison).
2. Subset the WWBI indicator rows to only EU countries and the relevant indicator codes.
3. For the primary question: extract 2012 and 2017 observations (or aggregate per country over those years), handle missingness (pairwise deletion or imputation), and choose an appropriate test:
   - If normally distributed: paired or independent t-test as applicable.
   - If not normal: Wilcoxon signed-rank or Mann-Whitney U test, depending on pairing.
4. For the secondary question: conduct the same process on the female-to-male wage ratio indicator (ensure the indicator is present and sufficiently populated).
5. Add clear reporting of test statistics, p-values, effect sizes, and concise interpretation.

## Contact / author

Author: Abbast (GitHub: Abbast)  
Repository: https://github.com/Abbast/Statistical-Analysis-of-World-Bank-Data

## License

No license specified in the repository. If you plan to share or reuse code/data, add an appropriate LICENSE file.

