# Tech Careers: Insights from Stack Overflow 2025 Developer Survey

## Overview

An end-to-end data science project following the **CRISP-DM** methodology, analyzing the Stack Overflow 2025 Developer Survey (~49,000 responses, 172 features) to answer three business questions about modern tech careers.

## Libraries Used

- **pandas** — data manipulation and analysis
- **numpy** — numerical computing
- **scikit-learn** — machine learning models and evaluation
- **matplotlib** — static visualizations
- **seaborn** — statistical plots

## Motivation

The tech industry evolves rapidly. Understanding what drives developer salaries, job satisfaction, and remote work arrangements helps both individuals make career decisions and organizations build better hiring and retention strategies. The Stack Overflow Developer Survey is one of the largest and most comprehensive snapshots of the global developer community.

## Business Questions

1. **What factors predict developer salary?** — Regression on `ConvertedCompYearly` using a Random Forest Regressor.
2. **Which factors are most associated with job satisfaction?** — Binary classification on `JobSat` (≥7 = Satisfied) using a Gradient Boosting Classifier.
3. **Can we predict if a developer works remotely?** — Multi-class classification on `RemoteWork` (Remote / Hybrid / In-person) using a Random Forest Classifier.

## Files

| File | Description |
|------|-------------|
| `developer_insights.ipynb` | Main Jupyter notebook with full CRISP-DM analysis |
| `data/survey_result_2025.csv` | Stack Overflow 2025 Developer Survey responses |
| `data/survey_result_2024.csv` | Stack Overflow 2024 Developer Survey responses (reference) |
| `blog_post.md` | Medium-style blog post summarizing key findings |
| `charts/` | Saved chart images (salary distribution, feature importances, etc.) |
| `README.md` | This file |

## Summary of Results

| Model | Algorithm | Key Metric |
|-------|-----------|------------|
| Salary Prediction | RandomForestRegressor | R² = 0.51, MAE = $33,279, RMSE = $48,303 |
| Job Satisfaction | GradientBoostingClassifier | Accuracy = 70.64%, Precision = 71.94%, Recall = 96.67%, F1 = 82.49% |
| Remote Work | RandomForestClassifier | Accuracy = 55.30%, Weighted F1 = 0.52 |

**Key Findings:**
- **Salary** is most strongly predicted by Country, YearsCode, and WorkExp. The model explains ~51% of salary variance (R² = 0.51).
- **Job satisfaction** is driven by ConvertedCompYearly, WorkExp, and YearsCode. The classifier achieves 70.64% accuracy with strong recall (96.67%).
- **Remote work** is best predicted by Country, YearsCode, and WorkExp, though the three-class problem proves challenging (55.30% accuracy).
- A fictional scenario ("Alex Chen") yields a predicted salary of $114,460, 71.28% probability of being satisfied, and 53.18% probability of working remotely.

## How to Run

1. Ensure Python 3.8+ is installed with the required libraries:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
2. Open `developer_insights.ipynb` in Jupyter Notebook or VS Code.
3. Run all cells sequentially.

## Acknowledgments

- Data provided by [Stack Overflow](https://stackoverflow.com/) through their annual Developer Survey.
- This project was created for educational purposes following the CRISP-DM data science process.
