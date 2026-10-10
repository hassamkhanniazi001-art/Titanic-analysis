# Titanic Passenger Survival Analysis

## Overview

This project explores the Titanic passenger dataset using Python and exploratory data analysis (EDA). 
The goal is to understand the dataset, assess data quality, investigate survival patterns, and communicate 
findings through summary tables and visualizations.

## Questions explored

- How did survival rates differ by sex?
- How did passenger class relate to survival?
- How did age and passenger class relate to survival?
- Did survival rates differ by port of embarkation?
- How were family travel, ticket fare, and passenger class distributed?
- Which numerical features showed relationships with one another?
- Which passengers paid the highest fares?

## Tools and libraries

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Notebook contents

1. **Dataset inspection** — previews the data, checks its dimensions and data types, and examines unique values and duplicate rows.
2. **Missing-data analysis** — counts missing values and calculates their percentages by column.
3. **Data cleaning** — removes duplicate rows, fills missing `Age` values with the median, and fills missing `Embarked` values with the mode.
4. **Group analysis** — compares survival rates across sex, passenger class, age bands, and embarkation port; also explores family travel and fare groups.
5. **Visualization** — uses histograms, boxplots, a correlation heatmap, and bar plots to examine distributions and relationships.
6. **Summary findings** — records answers to the analysis questions and highlights patterns observed in the data.

## Main findings

The notebook's analysis indicates that:

- Women had a substantially higher survival rate than men.
- First-class passengers had a higher survival rate than third-class passengers.
- The `Cabin` column has a large amount of missing data (about 77% in this dataset).
- `Age` has missing values; the notebook fills these with the median age.
- `Embarked` has a small number of missing values; the notebook fills these with the most frequent value.
- `Fare` has a strongly right-skewed distribution and several high-value outliers.
- `SibSp` and `Parch` show a relationship, as both describe family relationships aboard the ship.

These are descriptive patterns in this dataset; they do not by themselves establish cause and effect.

## Dataset

The notebook uses the Titanic passenger dataset commonly distributed for introductory data analysis and 
machine-learning practice. The original file is not included in this repository, so obtain the CSV separately 
from the dataset source and update the file path in the notebook before running it.

The notebook currently uses a machine-specific absolute Windows path. For portability, 
place the CSV in a project `data/` folder and load it with a relative path, for example:

```python
df = pd.read_csv("data/Titanic-Dataset.csv")
```

Only redistribute the dataset if its source license and terms permit it.

## How to run

1. Download or clone this repository.
2. Obtain the Titanic CSV dataset and place it at `data/Titanic-Dataset.csv` (or adjust the notebook's path).
3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

4. Start Jupyter and open `Titanic analysis uni I.ipynb`.
5. Run the notebook cells from top to bottom.

## Notes and limitations

- Missing `Cabin` values are retained rather than filled, because a large proportion of the column is missing.
- Median and mode imputation are simple baseline choices. They can affect distributions and group comparisons, so interpret results with this in mind.
- The age grouping currently uses `Age > 18` for the `Adult` category; therefore, age 18 is classified as `Minor`. Consider defining and documenting the cutoff explicitly.
- The fare groups use two equal-width bins. Because fares are skewed, quantile-based bins may sometimes give a more balanced comparison.
- Correlation measures association, not causation. `Pclass` is an ordinal category, so its numeric correlation should be interpreted carefully.
- Some conclusions in the notebook include historical explanations that are not tested by the analysis itself. Present those as context rather than as results proven by the data.

## Project status

An exploratory analysis and learning project. Future improvements could include clearer statistical comparisons, 
better-labelled plots, reusable relative paths, and a concise summary of limitations.
