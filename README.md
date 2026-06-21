# Titanic Survival - Exploratory Data Analysis

A mini data analysis project exploring the Titanic passenger dataset (`train.csv`) using `pandas`, `numpy`, and `matplotlib`. The notebook walks through data inspection, cleaning, grouped survival-rate analysis, and visualization.

## Project Structure

```
.
├── notebook.ipynb   # Main notebook
├── train.csv          # Titanic dataset (must be placed in the same directory)
└── README.md
```

## Requirements

- Google Colab (recommended), or Jupyter Notebook / JupyterLab locally
- Python 3.x
- pandas
- numpy
- matplotlib

These libraries come pre-installed on Google Colab, so no setup is needed there. For local use, install with:

```bash
pip install pandas numpy matplotlib jupyter
```

## Dataset

The notebook expects a `train.csv` file (the classic Titanic dataset with columns such as `Survived`, `Pclass`, `Sex`, `Age`, `Embarked`, etc.).

**On Colab:** upload `train.csv` to the session via the Files panel (left sidebar → Upload), or mount Google Drive and point `pd.read_csv()` to the file's path there. Files uploaded directly to the session are deleted when the runtime disconnects, so re-upload if you restart.

## What the Notebook Does

1. **Data Loading & Inspection**
   - Loads `train.csv` into a DataFrame
   - Inspects structure with `.info()` and `.describe()`
   - Checks for missing values with `.isnull()`

2. **Data Cleaning**
   - Fills missing `Age` values with the column mean
   - Fills missing `Embarked` values with the column mode

3. **Survival Analysis (Grouped)**
   - Survival rate by `Sex`
   - Survival rate by `Pclass`
   - Survival rate by `Embarked`
   - Average `Age` of survivors vs. non-survivors

4. **Feature Engineering**
   - Adds an `AgeGroup` column, bucketing passengers into `Child`, `Adult`, and `Senior`

5. **Visualizations**
   - Bar chart: survival rate by gender
   - Bar chart: survival rate by passenger class
   - Histogram: age distribution
   - Pie chart: passenger class distribution

## How to Run

1. Open `notebook.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Upload `train.csv` to the Colab session (Files panel → Upload), or mount Google Drive and update the file path in the `pd.read_csv()` call.
3. Run all cells in order (Runtime → Run all).

## Key Insights (typical for this dataset)

- Female passengers had a notably higher survival rate than male passengers.
- 1st class passengers survived at a higher rate than 2nd and 3rd class.
- Younger passengers (children) tended to have higher survival rates.

## Notes

- The `AgeGroup` bucketing logic (`categorize_age`) currently classifies almost everyone as `Adult` (anyone over 10 and up to 30); ages above 30 are labeled `Senior`. You may want to adjust these thresholds (e.g., Child ≤ 12, Adult 13–59, Senior 60+) for more realistic groupings.
- An unused `data` dictionary (sample student scores) appears early in the notebook and is not connected to the rest of the analysis — safe to remove if cleaning up.
