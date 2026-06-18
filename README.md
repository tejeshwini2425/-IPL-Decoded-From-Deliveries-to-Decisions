# 🏏 IPL Decoded: From Deliveries to Decisions

> A data-driven deep dive into 10 seasons of IPL cricket (2008–2017). Using Python, Pandas, Matplotlib and Seaborn on 150,000+ ball-by-ball deliveries, this project uncovers who the real run machines are, which death bowlers hold their nerve, which venues favour which teams, and whether winning the toss actually matters.

![Python](https://img.shields.io/badge/Python-3.13-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-lightblue?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-teal?style=flat)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

---

## 📌 Project Overview

This is a Phase 1 portfolio project focused on **Exploratory Data Analysis (EDA)** using real IPL data from Kaggle. The goal is to extract meaningful cricket insights from raw data — answering questions that matter to fans, analysts, and selectors alike.

**Dataset:** [IPL Complete Dataset — Kaggle](https://www.kaggle.com/datasets/mnathvijay/ipl-complete-dataset)  
**Matches analysed:** 636  
**Deliveries analysed:** 150,460  
**Seasons covered:** 2008–2017 (10 seasons)

---

## 🎯 Key Questions Answered

| # | Question | Chart Type |
|---|---|---|
| 1 | Who are the top 10 run scorers in IPL history? | Horizontal Bar Chart |
| 2 | Who scores fast AND consistently? | Scatter Plot |
| 3 | Which teams dominate which venues? | Heatmap |
| 4 | Who are the best death over bowlers? | Horizontal Bar Chart |
| 5 | Does winning the toss actually help? | Grouped Bar Chart |

---

## 📊 Charts & Insights

### 1. Top 10 Run Scorers (2008–2017)
SK Raina leads with 4,548 runs, followed by Virat Kohli (4,423) and Rohit Sharma (4,207). The top 10 are dominated by consistent, long-serving players who played across multiple franchises and seasons.

### 2. Strike Rate vs Batting Average — Who is Truly Elite?
Using a scatter plot divided into 4 quadrants by average strike rate and average batting average:
- **Elite (top right):** AB de Villiers, CH Gayle, DA Warner — high average AND high strike rate
- **Consistent but measured:** V Kohli, G Gambhir — high average, slightly lower strike rate
- **Outlier:** GJ Maxwell — strike rate of 157 but average of only 25. Classic aggressive but risky batter.

### 3. Venue Win % Heatmap
- **MI at Eden Gardens: 82%** — Mumbai Indians dominated KKR's home ground
- **CSK at Feroz Shah Kotla: 83%** — CSK were lethal in Delhi even away from home
- **KXIP at PCA Stadium: 100%** — Perfect home record at their own ground
- **RR at Sawai Mansingh: 73%** — Rajasthan Royals were strong at home in Jaipur

### 4. Best Death Over Bowlers (Overs 17–20, min. 60 balls)
Economy rates that prove class under pressure:
- 🥇 Sohail Tanvir — **6.73** (most economical)
- 🥈 SP Narine — **7.44** (mystery spin works even in death!)
- 🥉 DE Bollinger — **7.44**
- SL Malinga — **7.57** (the yorker king, confirmed by data)

### 5. Toss Decision vs Match Outcome
- Winning the toss alone = **51.3% win rate** (barely better than a coin flip)
- Choosing to **field after winning toss = 55.7% win rate**
- Choosing to **bat after winning toss = only 45.6% win rate**
- **Conclusion:** The toss itself doesn't matter much — but fielding first is clearly the smarter IPL strategy.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Core programming language |
| Pandas | Data loading, cleaning, aggregation |
| Matplotlib | Chart drawing and layout |
| Seaborn | Styled visualisations (heatmap, scatter) |
| Jupyter Notebook | Interactive coding environment |

---

## 📁 Project Structure

```
IPL-Decoded-From-Deliveries-to-Decisions/
│
├── ipl_analysis.ipynb       # Main Jupyter notebook with all code
├── matches.csv              # Match-level data (636 matches)
├── deliveries.csv           # Ball-by-ball data (150,460 deliveries)
├── README.md                # This file
└── LICENSE                  # MIT Licence
```

---

## 🚀 How to Run This Project

1. **Clone the repository**
```bash
git clone https://github.com/tejeshwini2425/-IPL-Decoded-From-Deliveries-to-Decisions.git
cd IPL-Decoded-From-Deliveries-to-Decisions
```

2. **Install dependencies**
```bash
pip install pandas matplotlib seaborn jupyter
```

3. **Launch Jupyter Notebook**
```bash
jupyter notebook
```

4. **Open** `ipl_analysis.ipynb` and run all cells top to bottom.

---

## 💡 Key Learnings

- Real-world data is messy — venue names had inconsistencies that needed custom cleaning functions
- Filtering matters — setting minimum thresholds (500 balls for batting, 60 balls for bowling) makes analysis statistically meaningful
- Visualisation choices matter — a heatmap tells a venue story that a table never could
- Domain knowledge helps — understanding cricket made it easier to validate whether results made sense

---

## 🗺️ What's Next (Phase 2)

- 🤖 Build an IPL match **win predictor** using Machine Learning (Logistic Regression)
- 📈 Add **season-by-season trend analysis**
- 🌐 Deploy as an **interactive web dashboard** using Streamlit

---

## 👤 Author

**Tejeshwini**  
B.Tech Data Science Student  
[GitHub](https://github.com/tejeshwini2425) 

---

## 📄 Licence

This project is licensed under the **MIT Licence** — see the [LICENSE](LICENSE) file for details.
