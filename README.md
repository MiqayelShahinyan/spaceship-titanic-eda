# Spaceship Titanic — EDA

## Dataset
Source: https://www.kaggle.com/competitions/spaceship-titanic  
Task: binary classification — predict whether passenger was Transported  
Size: ~8700 rows, 14 features

## What this notebook does
Exploratory data analysis: data quality, distributions, target relationships, 
feature engineering ideas.

## Key findings
Facts (from data):
- CryoSleep is strongly correlated with Transported
- Passengers from Europa/Mars transported more than Earth
- Decks B and C have the highest transport rate
- Side P/S of cabin affects transport rate
- Passengers in the same group usually share the same outcome
- Most passengers travel to TRAPPIST-1e

Implications for modeling:
- CryoSleep, Cabin (deck/side), HomePlanet, group_id are likely strong features
- Spending columns are highly skewed → log-transform may help
- group_id can be used to build group-level features

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