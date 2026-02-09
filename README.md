# Injury Classification with OSHA Severe Injury Report Data

## Project Overview
This is a sample project for my application to Brown University's Sc.M Data Science program. The project analyzes OSHA's Severe Injury Reports dataset, with the goal of identifying the strongest predictors of certain types of injuries using features from the dataset. The selected model achieved 84% accuracy, and applications for this project could include a suite of software tools for occupational safety professionals to better anticipate and prevent workplace injuries.

## Tech Stack
- **Data Engineering:** Alteryx
- **Visualization:** Tableau
- **Analysis & Modeling:** Python
- **Statistical Methods:** Cramer's V, Mutual Information, VIF Analysis

## Methodology

### Phase 1: Feature Engineering (Alteryx)
- Consolidated specific industry codes into generalizable categories for analysis
- Reduced data sparsity and improved model generalization
- Created binary flags (Amp Bool/Hosp Bool) for severity indicators
- Result - Final dataset with 100K+ incidents with 5 engineered features

### Phase 2: Exploratory Analysis (Tableau)
- Built interactive dashboards showing event distribution by industry
- Identified General Event patterns that preliminarily informed feature selection
- Visualized high-level trends in the dataset

### Phase 3: Statistical Analysis & Modeling (Python)

**Feature Selection:**
- Categorical association analysis (Cramer's V, Mutual Information)
- Multicollinearity check (VIF < 10 for all features)
- Selected 5 features with statistical justification

**Modeling Approach:**
- Trained 3 classifiers: Random Forest, XGBoost, Logistic Regression
- 5-fold cross-validation to prevent overfitting
- Class balancing to handle 56.9:1 imbalance

**Key Statistical Decision:**
- Inclusion of Amp Bool despite low MI score: it became a useful predictor for Contact Incidents, which were prevalent in the dataset

## Results

**Model Performance:**
- Best Model: XGBoost
- Test Accuracy: 84.41%
- F1-Score (Macro): .6525
- Cross-validation confirmed generalization (CV is similar to Test)

**Feature Importance Validation:**
- Top 3 predictors: General Source, General Nature, General Part of Body
- Amp Bool inclusion validated with a model importance of 0.1446 (similar to General Part of Body in Top 3)

**Impact:**
- The analysis identified injury source and nature as the strongest predictors of injury event type, with the goal of helping safety programs target high-risk combinations like machinery-related contact injuries. This model could enable occupational safety professionals to allocate prevention resources more strategically across industries, using data-driven insights to anticipate and address the injury patterns most likely to occur in specific workplace settings.

## Skills Demonstrated

**Technical:**
- Feature engineering for categorical data generalization
- Statistical association analysis (non-parametric methods)
- Handling severe class imbalance
- Model validation & overfitting prevention

**Analytical:**
- Justified feature selection with multiple metrics
- Workflow: EDA, Feature Selection, Validation, Modeling
- Interpreted model performance in business context

## Repository Contents
```
├── OSHA Severe Injury Report_Feature Selection and Classification Model Comparison.ipynb
    # Full Python analysis
├── OSHA Severe Injury Data Visualization.twbx
    # Interactive visualizations
├── OSHA Workflow.yxmd
    # Feature engineering pipeline
└── README.md
    # This file
```

## Next Steps
- Hyperparameter tuning for model performance gain
- Incorporate NLP analysis of incident narratives

## At a Glance
- **Dataset:** 100K+ OSHA severe injury incidents ([OSHA Severe Injury Reports](https://www.osha.gov/severe-injury-reports))
- **Time Period:** 2015-2025
- **Models Compared:** 3
- **Final Features:** 5 (from 30 initial variables)
- **Best Model F1-Score:** .6525

## Alteryx Workflow
<img width="479.227" height="300" alt="Screenshot 2026-01-31 205901" src="https://github.com/user-attachments/assets/2f4fbb3c-cf7a-42be-8bc7-3d27dc4e97ac" />



