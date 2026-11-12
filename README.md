# Earthquake Damage Prediction Using Machine Learning

## Project Overview
This project predicts the level of damage to buildings affected by the 2015 Gorkha earthquake in Nepal using machine learning techniques.

The objective is to classify buildings into three damage categories based on their geographical location, structural characteristics, construction materials, and other building-related information.

## Problem Statement
Predict the ordinal target variable `damage_grade`:

- **Grade 1:** Low damage
- **Grade 2:** Medium damage
- **Grade 3:** Almost complete destruction

The project also includes exploratory data analysis, model comparison, geographic generalization evaluation, and recommendations for reducing building damage during earthquakes.

## Dataset
The dataset contains information about buildings affected by the Gorkha earthquake.

- Training records: 260,601
- Original building features: 38
- Unique identifier: `building_id`
- Target variable: `damage_grade`

The dataset includes geographic identifiers, building age, number of floors, building area, foundation type, roof type, ground-floor type, construction materials, and secondary-use information.

Categorical values are anonymized. The same character appearing in different columns does not necessarily represent the same category.

## Technologies Used
- Python
- Jupyter Notebook
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- XGBoost

## Project Workflow
1. Data loading and merging
2. Data cleaning and validation
3. Exploratory Data Analysis (EDA)
4. Outlier analysis
5. Feature engineering
6. Categorical encoding and numerical scaling
7. Model training and evaluation
8. Model comparison
9. Geographic generalization testing
10. Final analysis and recommendations

## Machine Learning Models
The following models were evaluated:

- Logistic Regression
- Tuned Logistic Regression
- Random Forest Classifier
- Extra Trees Classifier
- XGBoost Classifier
- Balanced XGBoost Classifier

## Model Results

### Random Split Evaluation

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 70.03% | 0.6755 |
| Tuned Logistic Regression | 70.03% | 0.6755 |
| XGBoost | 71.78% | 0.6469 |
| Balanced XGBoost | 65.71% | 0.6333 |
| Extra Trees | 62.37% | 0.6038 |
| Random Forest | 60.76% | 0.5879 |

### Geographic Generalization
A geographic split was used to evaluate performance on regions excluded from training.

The final Random Forest model, trained without geographic ID features, achieved:

- Accuracy: **53.43%**
- Macro F1-score: **0.4844**

Five-fold GroupKFold validation on the geographic training data produced a mean macro F1-score of approximately **0.4798**.

The Random Forest was selected as the leading candidate in the geographic evaluation. Further validation is required before production deployment.

## Key Findings
- Building construction characteristics are associated with damage severity.
- Foundation type and ground-floor type showed relatively strong associations with the target.
- Geographic features were highly predictive in a random split but did not generalize reliably to unseen regions.
- Grade 2 and Grade 3 were frequently confused during geographic evaluation.
- Class imbalance affected model performance, especially for the minority Grade 1 category.

## Recommendations
- Encourage earthquake-resistant construction practices.
- Improve foundation and structural design standards.
- Promote engineered construction materials and professional supervision.
- Identify high-risk geographic areas for inspection and retrofitting.
- Improve public awareness and earthquake preparedness.
- Use machine learning predictions as decision-support tools alongside engineering assessments.

## How to Run
1. Clone this repository.
2. Install the required Python libraries.
3. Place the dataset files in the expected project directory.
4. Open the Jupyter Notebook.
5. Run the notebook cells from top to bottom.

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
```

## Project Deliverables
- Complete Jupyter Notebook
- Data Analysis Report
- Model Comparison Report
- Challenges Faced Report
- Suggestions for Seismologists
- Final Geographic Holdout Classification Report

## Limitations
The model predicts damage grades from historical building and earthquake-related survey information. It does not predict when or where an earthquake will occur. Its performance on unseen geographic regions is lower than on a random split, so it should not be used as a standalone safety or engineering decision system.

## Conclusion
This project demonstrates how machine learning can help analyze building vulnerability and estimate earthquake damage severity. Geographic validation highlights the importance of testing models on unseen regions rather than relying only on random train-test splits.

**Project:** PRCP-1015 – Earthquake Damage Prediction
