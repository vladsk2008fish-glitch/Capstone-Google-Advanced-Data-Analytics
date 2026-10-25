# Employee Attrition Analysis

### Data-driven retention insights for Salifort Motors

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![scikit--learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)

This capstone explores employee attrition data and builds a classification model to help HR identify patterns associated with employees leaving. It combines exploratory analysis, data preparation, model evaluation, and practical retention recommendations in a Jupyter notebook.

## Contents

- [About the project](#about-the-project)
- [Repository structure](#repository-structure)
- [Key findings](#key-findings)
- [Tools](#tools)
- [Running the notebook](#running-the-notebook)
- [Responsible use](#responsible-use)
- [Data source](#data-source)

## About the project

Salifort Motors' HR team wants to better understand employee attrition and identify areas where supportive retention measures may help. The notebook examines satisfaction, performance evaluation, workload, tenure, promotions, workplace accidents, department, and salary.

The workflow follows the **PACE** framework:

| Stage | Purpose |
| --- | --- |
| **P — Plan** | Define the HR question, stakeholders, and ethical considerations |
| **A — Analyze** | Inspect, clean, and explore the employee data |
| **C — Construct** | Prepare features and train classification models |
| **E — Execute** | Interpret results and recommend follow-up actions |

## Repository structure

```text
.
├── README.md
├── Activity_ Course 7 Salifort Motors project lab.ipynb
└── HR_capstone_dataset.csv
```

## Key findings

The exploratory analysis identifies workload, project count, and job satisfaction as useful areas for further retention investigation. These are associations in observational data, not proof of cause.

The notebook's tuned **Random Forest** was selected by cross-validation to prioritize recall. On its held-out test set of 2,399 records, the classification report shows:

| Class | Precision | Recall | F1-score |
| --- | ---: | ---: | ---: |
| Stayed | 0.99 | 1.00 | 0.99 |
| Left | 0.98 | 0.93 | 0.95 |

Overall test accuracy was **0.99** (rounded). The model has not been evaluated here with test ROC-AUC, and the XGBoost comparison in the notebook has not yet been run. Treat these results as an initial evaluation on one random holdout, not a guarantee of future or team-level performance.

Recommended follow-up includes reviewing project allocation and sustained working hours, checking satisfaction and manager support, and auditing promotion and overtime practices for consistency.

## Tools

| Tool | Use |
| --- | --- |
| **Python** | Analysis and model development |
| **pandas, NumPy** | Data cleaning and transformation |
| **Matplotlib, Seaborn** | Exploratory visualization |
| **scikit-learn** | Train/test split, model tuning, and evaluation |
| **XGBoost** | Optional model comparison included in the notebook |
| **Jupyter** | Interactive notebook environment |

## Running the notebook

Install Python, then install the notebook dependencies:

```bash
python -m pip install jupyterlab pandas numpy scipy matplotlib seaborn scikit-learn xgboost
```

Launch JupyterLab from the repository folder:

```bash
jupyter lab
```

Open `Activity_ Course 7 Salifort Motors project lab.ipynb` and run the cells from top to bottom. Keep `HR_capstone_dataset.csv` beside the notebook so its relative file path resolves. The XGBoost cells are a comparison workflow; run them successfully before reporting any XGBoost results.

## Responsible use

Employee attrition data is sensitive. Protect access to the dataset and any model outputs, review errors and fairness across relevant groups, and explain uncertainty to stakeholders. Predictions should only inform confidential, supportive follow-up; they must not be used as the sole basis for hiring, promotion, compensation, or termination decisions. Validate any intervention using later data and employee feedback.

## Data source

The dataset is supplied in this repository for the capstone exercise. Its source is the [HR Analytics and Job Prediction dataset on Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv).
