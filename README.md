# student-intervention-risk-model
# Student Intervention Risk Model

Machine learning project exploring whether student performance data can identify students who may benefit from academic intervention before final course outcomes are known.

## Project Overview

The goal of this project was to predict students' final course grades and evaluate whether a predictive model could support earlier academic intervention.

A central question was whether useful predictions could be made without relying on first-term and second-term grades. Earlier predictions would give educators more time to provide academic support.

The analysis showed a clear tradeoff between early identification and predictive accuracy.

## Data

The dataset contained:

- 395 students
- 35 demographic, behavioral, attendance, family, support, and academic variables
- Student records from two Portuguese schools

Variables included:

- Prior grades
- Absences
- Previous course failures
- Study time
- Educational support
- Family characteristics
- Parent education
- Student activities
- Health
- Higher-education intentions

## Tools

- Python
- pandas
- NumPy
- scikit-learn
- Jupyter Notebook
- Matplotlib
- Statistical analysis
- Machine learning

## Data Preparation

The analysis included:

- Missing-value treatment
- Outlier analysis
- Exploratory data analysis
- Distribution analysis
- Correlation analysis
- Feature selection
- Model comparison
- Hyperparameter tuning

Missing values in age and absence variables were imputed.

Zero values in G2 and G3 were investigated as potential outliers and removed from the final modeling analysis after testing their effect on model performance.

## Exploratory Analysis

Correlation analysis showed that prior academic performance was substantially more predictive of final grades than the remaining demographic, behavioral, and support variables.

G2 was the strongest individual predictor of final grade.

Additional features were evaluated using correlation analysis and iterative model testing.

## Models Evaluated

Four modeling approaches were compared:

1. Linear Regression
2. Support Vector Machine Regression
3. Lasso Regression
4. Tuned Support Vector Machine Regression

Models were evaluated both with and without prior G1 and G2 grades.

Performance was measured using:

- Root Mean Squared Error (RMSE)
- R-squared (R²)

## Results

| Model | RMSE with G1/G2 | R² with G1/G2 | RMSE without G1/G2 | R² without G1/G2 |
|---|---:|---:|---:|---:|
| Linear Regression | 0.876 | 0.927 | 3.116 | 0.073 |
| SVM Regression | 1.130 | 0.878 | 3.089 | 0.092 |
| Lasso Regression | 1.314 | 0.836 | 3.260 | -0.010 |
| Tuned SVM Regression | 0.879 | 0.920 | 2.554 | 0.323 |

### Selected Model

Linear Regression using prior G1 and G2 grades produced:

- RMSE: 0.876
- R²: 0.927
- Final-grade predictions typically within approximately one grade point of actual results

## Key Finding

Prior academic performance was critical to prediction quality.

Models excluding G1 and G2 performed substantially worse. Even the strongest model without prior grades, the tuned SVM, produced:

- RMSE: 2.554
- R²: 0.323

The results did not support deploying the no-prior-grade models for early intervention.

## Recommendation

Use the Linear Regression model with prior-grade information as a decision-support tool for identifying students who may benefit from additional academic support.

The model should supplement educator judgment rather than automatically determine intervention decisions.

Future implementations should combine model results with additional information such as:

- Attendance trends
- Teacher observations
- Existing support services
- Current academic progress
- Intervention participation

## Next Steps

Future work could include:

- Testing the model on new student cohorts
- Tracking intervention participation
- Measuring student performance after intervention
- Retraining models with intervention outcome data
- Testing additional feature-engineering approaches
- Evaluating whether new variables improve earlier prediction

## Project Files

- `student_intervention_model.ipynb` - Full Python analysis and modeling workflow
- `docs/student_intervention_executive_summary.pdf` - Executive summary of findings

## Skills Demonstrated

- Python data analysis
- Data cleaning
- Exploratory data analysis
- Feature engineering
- Regression modeling
- Model evaluation
- Hyperparameter tuning
- Statistical interpretation
- Education analytics
- Data visualization
- Translating technical findings into recommendations for nontechnical stakeholders
