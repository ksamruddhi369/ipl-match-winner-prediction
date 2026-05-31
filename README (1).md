# 🏏 IPL Match Winner Prediction

Predicting the winner of IPL cricket matches using historical match data and machine learning. The project includes exploratory data analysis, feature engineering, XGBoost classification, and SHAP-based model explainability.

---

## 📌 Problem Statement

Can we predict which team will win an IPL match before it starts, using only pre-match information like team history, venue, toss outcome, and season?

---

## 📂 Dataset

- **Source:** [IPL Complete Dataset (2008–2020) – Kaggle](https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020)
- **Size:** 1090 matches after cleaning
- **Key files used:** `matches.csv`

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas, NumPy | Data manipulation |
| Matplotlib, Seaborn | EDA & visualizations |
| Scikit-learn | Preprocessing, train-test split |
| XGBoost | Prediction model |
| SHAP | Model explainability |

---

## 📊 Exploratory Data Analysis

Key findings from EDA:
- **Mumbai Indians** are the most successful IPL team with 140+ wins
- **64.2%** of toss winners choose to field first
- Toss win does **not** significantly correlate with match win
- Team performance varies considerably across seasons

---

## ⚙️ Feature Engineering

| Feature | Description |
|---|---|
| `team1_winrate` | Historical win rate of team 1 |
| `team2_winrate` | Historical win rate of team 2 |
| `winrate_diff` | Difference in win rates between both teams |
| `toss_is_team1` | Whether team 1 won the toss (binary) |
| `venue` | Match venue (label encoded) |
| `season` | IPL season year |
| `toss_decision` | Bat or field after winning toss |

---

## 🤖 Models & Results

| Model | Accuracy | AUC-ROC |
|---|---|---|
| Logistic Regression (baseline) | 51.83% | — |
| XGBoost (final) | 54.13% | 0.572 |

> **Note:** IPL match prediction is inherently difficult due to the sport's unpredictability. Even professional analysts rarely exceed 60–65% accuracy without real-time player and pitch data. The focus of this project is on feature engineering, model explainability, and deriving actionable insights.

---

## 🔍 SHAP Explainability

SHAP (SHapley Additive exPlanations) was used to interpret model predictions.

**Top findings:**
- `winrate_diff` is the most influential feature — a larger gap in historical win rates strongly influences the predicted outcome
- `venue` has significant impact — certain grounds heavily favour specific teams
- `season` matters — team strength and form varies year to year
- `toss_is_team1` and `toss_decision` have the least impact, confirming that toss outcome is not a reliable predictor

---

## 📁 Project Structure

```
ipl-match-winner-prediction/
│
├── matches.csv               # Raw dataset
├── ipl_prediction.ipynb      # Main notebook (EDA + Model + SHAP)
└── README.md                 # Project documentation
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/yourusername/ipl-match-winner-prediction.git
cd ipl-match-winner-prediction
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap
```

3. Open the notebook
```bash
jupyter notebook ipl_prediction.ipynb
```
Or open directly in **Google Colab**

---

## 💡 Key Takeaways

- Historical win rate difference between teams is the strongest pre-match predictor
- Venue significantly affects match outcomes in IPL
- Toss result has minimal predictive power — contradicting popular belief
- Sports prediction models are limited without real-time data (player form, pitch, weather)

---

## 👩‍💻 Author

**Sam**
BSc Data Science | SIES College, Navi Mumbai
