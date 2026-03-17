# Scholastic-Travel-Retention-Modeling
Scholastic Travel Retention Modeling (Machine Learning Project)
# Scholastic Travel Retention Modeling

Machine learning classification project focused on predicting whether a Scholastic Travel customer will return the following year. The project compares multiple supervised learning approaches, applies feature engineering to structured trip and customer data, and translates model results into practical retention recommendations.

## Project Overview
This project was completed for an applied machine learning classification assignment centered on the **Retention Modeling at Scholastic Travel Company** case. The objective was to classify customers as **Retained** or **Churned** for the upcoming year using historical labeled data, then generate predictions for an unlabeled submission file.

The analysis compares three classification approaches:
- **K-Nearest Neighbors (KNN)**
- **Random Forest Classifier**
- **Gaussian Process Classification (GPC)**

The project emphasizes model evaluation, feature engineering, hyperparameter tuning, and interpretation of predictors that influence customer retention.

## My Contribution
My primary contribution focused on the **tree-based modeling component**, especially the **Random Forest model**. I worked on:
- building the preprocessing and modeling pipeline
- engineering time-based and trip-structure features
- testing multiple hyperparameter configurations
- evaluating model performance using accuracy, precision, recall, and AUC
- identifying important predictors and translating them into business recommendations

## Problem Statement
Customer churn is a critical issue for organizations that rely on repeat engagement. In this case, the goal was to identify which Scholastic Travel customers were unlikely to book a trip the following year so the company could intervene earlier and improve retention.

## Methods
### Data Preparation
The project used labeled customer data from Scholastic Travel along with a separate unlabeled prediction dataset. Data preparation included:
- converting date columns into usable datetime objects
- engineering lead-time and engagement variables
- creating rate-based features from trip activity fields
- encoding categorical variables where appropriate
- scaling numeric features for distance-based models such as KNN

### Feature Engineering
Examples of engineered features include:
- `planning_window`
- `meeting_span`
- `days_to_departure`
- `deposit_to_first_meeting`
- `trip_length_from_dates`
- `grade_range`
- `discount_pax_rate`
- `cancel_pax_rate`
- `fpp_rate`

These features were designed to capture planning behavior, trip structure, and customer engagement.

### Models Evaluated
**KNN** was used as a distance-based baseline and refined through feature selection and hyperparameter tuning.

**Random Forest** was used as a flexible tree-based ensemble capable of handling nonlinear relationships, interactions, and mixed predictor types.

**Gaussian Process Classification** was selected as a third model to explore a less commonly used supervised classification method and compare its performance with the more standard approaches.

## Evaluation Metrics
All models were evaluated using:
- **Accuracy**
- **Precision**
- **Recall**
- **ROC-AUC**

These metrics were used together to assess both overall classification quality and the tradeoff between correctly identifying churn risk and avoiding false alarms.

## Key Results
Among the tested models, the **Random Forest classifier** delivered the strongest overall performance on the held-out test set.

Best Random Forest configuration:
- `n_estimators = 250`
- `max_features = 0.5`
- `class_weight = balanced_subsample`

Performance:
- **Accuracy:** 0.818
- **Precision:** 0.831
- **Recall:** 0.879
- **AUC:** 0.868

Important predictors included:
- `SingleGradeTripFlag`
- `grade_range`
- `IsNonAnnual`
- `SPRNewExisting_EXISTING`
- `FPP`
- `planning_window`
- `TotalPax`
- `TotalSchoolEnrollment`
- `deposit_to_first_meeting`

## Recommendations
Based on model findings, practical recommendations for Scholastic Travel include:
1. Promote single-grade trips, which appear strongly associated with retention.
2. Monitor planning and lead-time behavior to identify accounts that may need earlier outreach.
3. Track cancellation and discount patterns as early warning signals for churn risk.
4. Use payment and participation indicators to prioritize high-impact retention efforts.

## Repository Structure
```text
Classification Project/
├── Tree-Based Model (Abigail)/
│   └── RandomForest_Completed.ipynb
├── K-Nearest Neighbors (Ana)/
│   └── ML_classification_KNN.ipynb
├── Learn about a New Model (Nancy)/
│   └── ML_Classification_Gaussian_Process_Classification.ipynb
├── Project Written Files/
│   ├── Written Report.docx
│   ├── Classification Project Predictions.csv
│   └── supporting documents
└── Code Archive/
    └── combined and starter notebooks
```

## Tools Used
- Python
- Jupyter Notebook
- pandas
- scikit-learn
- matplotlib / visualization tools
- model selection and preprocessing pipelines

## Notes
If this project is uploaded publicly, make sure sharing the course data and case materials complies with your class policy before posting raw datasets or assignment files.

## Author Note
This repository reflects a collaborative class project. My featured work centers on the tree-based modeling and predictive analysis components.
