# 🤖 IPL Win Predictor — Machine Learning Edition

> A machine learning model that predicts IPL match winners using historical win rates, toss decisions, venue and team data. Built with Scikit-learn's Random Forest Classifier, trained on 10 seasons of IPL data (2008–2017).

![Python](https://img.shields.io/badge/Python-3.13-blue?style=flat&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat&logo=scikitlearn)
![Pandas](https://img.shields.io/badge/Pandas-2.0-lightblue?style=flat&logo=pandas)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

---

## 📌 Project Overview

This project builds on [IPL Decoded](#) (Phase 1 EDA) by turning descriptive insights into a **predictive model**. Given two teams, a venue, and toss information, the model predicts the likely match winner with a confidence score.

**Algorithm:** Random Forest Classifier (200 trees)  
**Matches used:** 626 (cleaned, completed matches only)  
**Train/Test split:** 80% / 20%  
**Final Accuracy:** **51.59%**

---

## 🎯 Problem Statement

> Can we predict which team will win an IPL match using only pre-match information — team names, venue, toss outcome, and historical performance?

This is a **multi-class classification problem** — predicting one winner out of 14 possible IPL teams.

---

## 🧠 Approach

### 1. Baseline Model (Logistic Regression)
First attempt used only categorical features — team names, venue, toss decision — encoded as numbers.
**Result: 23.81% accuracy** — only 3x better than random guessing (7% for 14 classes).

### 2. Feature Engineering — The Key Improvement
The baseline model lacked context. I engineered a critical new feature: **historical win rate**, calculated chronologically for each team *before* every match (avoiding data leakage by never using future match results).

New features added:
- `team1_winrate` — team 1's win rate from all prior matches
- `team2_winrate` — team 2's win rate from all prior matches
- `team1_won_toss` — binary flag for toss outcome

### 3. Upgraded Model (Random Forest)
Switched from Logistic Regression to a **Random Forest Classifier** (200 trees, max depth 10) — better suited for capturing non-linear patterns across multiple features.

**Result: 51.59% accuracy** — more than **double** the baseline.

---

## 📊 Model Performance

| Metric | Baseline (LogReg) | Final (Random Forest) |
|---|---|---|
| Accuracy | 23.81% | **51.59%** |
| Key features | Team, venue, toss | + Win rate, toss flag |
| vs Random guess (7%) | 3.4x better | **7.4x better** |

### Best Predicted Teams
- **Rajasthan Royals** — 92% recall (correctly caught 11/12 actual wins)
- **Mumbai Indians** — 52% recall, 21 test matches (most common team)
- **Chennai Super Kings** — 59% recall, strong precision (0.62)

### Weakest Predictions
- **Kochi Tuskers Kerala, Pune Warriors** — short-lived franchises (1–2 seasons), too little training data
- **Rising Pune Supergiant(s)** — inconsistent spelling in raw Kaggle data across seasons, splitting one team's history into two labels

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Core language |
| Pandas / NumPy | Data manipulation |
| Scikit-learn | LabelEncoder, train/test split, RandomForestClassifier, metrics |
| Matplotlib / Seaborn | Confusion matrix visualisation |
| Jupyter Notebook | Development environment |

---

## 📁 Project Structure

```
IPL-Win-Predictor/
│
├── ipl_win_predictor.ipynb   # Main notebook — full pipeline
├── matches.csv                # Match-level dataset
├── README.md                  # This file
└── LICENSE                    # MIT Licence
```

---

## 🚀 How to Run

```bash
git clone https://github.com/tejeshwini2425/IPL-Win-Predictor.git
cd IPL-Win-Predictor
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook
```

Open `ipl_win_predictor.ipynb` and run all cells top to bottom.

### Example prediction:
```python
predict_winner(
    team1='Mumbai Indians',
    team2='Chennai Super Kings',
    venue='Wankhede Stadium',
    toss_winner='Mumbai Indians',
    toss_decision='field'
)
# Output: Predicted Winner: Mumbai Indians | Confidence: 66.0%
```

---

## 💡 Key Learnings

- **Feature engineering matters more than algorithm choice.** Switching from team names alone to historical win rates more than doubled accuracy — before even changing the model.
- **Data leakage is a real risk.** Win rates had to be calculated using only matches *before* the current one (chronological order), or the model would "cheat" by seeing future results.
- **Real-world data has bugs.** A team name spelling inconsistency ("Rising Pune Supergiant" vs "Rising Pune Supergiants") silently split one team's history into two, hurting model performance — a reminder to always audit categorical data.
- **Accuracy alone isn't the full story.** The confusion matrix and per-team classification report revealed which teams the model handles well (Rajasthan Royals) versus poorly (short-lived franchises with little data).
- **51.59% accuracy is meaningful**, not low — cricket has high inherent randomness, and this is ~7x better than the random-guess baseline of 7% across 14 teams.

---

## Key Insights
- [Player] had the highest strike rate among top run scorers (20XX–2017)
- [Venue] showed the highest win % for chasing teams
- Teams winning the toss and choosing to bowl first won X% more often in death overs

## 🗺️ Future Improvements

- Fix the team name spelling inconsistency at the source
- Add player-level features (key players available, recent form)
- Add head-to-head historical record as a feature
- Try Gradient Boosting (XGBoost) for comparison
- Hyperparameter tuning via GridSearchCV

---

## 👤 Author

**Tejeshwini**  
B.Tech Data Science Student  
[GitHub](https://github.com/tejeshwini2425)

---

## 📄 Licence

This project is licensed under the **MIT Licence** — see the [LICENSE](LICENSE) file for details.
