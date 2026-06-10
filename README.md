# Spaceship Titanic — EDA

## Dataset
Source: https://www.kaggle.com/competitions/spaceship-titanic  
Task: binary classification — predict whether passenger was Transported  
Size: ~8700 rows, 14 features

## What this notebook does
Exploratory data analysis: data quality, distributions, target relationships, 
feature engineering ideas.

## Key findings
The Spaceship Titanic when appeared in cosmic mystery in 2912 the passengers were transported to an alternate dimension. We understand what the anomalia were in the right side of the spaceship were was leaving most of prysleeping people from Europa and and Mars. The most of people's destination was TRAPPIST-1e. People from Earth cryposleeped less and there were no VIP person because they were poor but the cryosleeping peoples were more likely to be transported. Peoples from B and C deck were transported more than others and we can predict that the B and C deck were extrimly on the right side of the spaceship. Passengers from the same group often share the same Transported outcome. Many groups are fully consistent (all transported or all not transported), which indicates strong group-level dependency.

## Next steps
1. Create engineered features:
   - TotalSpending, NoSpending, LogSpending
   - group_size, is_alone, group_survival_rate
   - Deck, Side, interactions

2. Clean missing values and encode categories.

3. Train baseline models (RandomForest, GradientBoosting).

4. Move to strong models (CatBoost / XGBoost / LightGBM).

5. Validate using Stratified K-Fold.

6. Analyze feature importance and refine features.

7. Iterate feature engineering based on model feedback.

## How to run
1. Download `train.csv` from Kaggle and place into `data/`
2. `conda activate ml-learn`
3. `jupyter lab eda.ipynb`