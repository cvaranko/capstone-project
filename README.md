# predicting game revenue on steam
### what drives financial success among top-selling titles?

![status](https://img.shields.io/badge/status-in%20progress-orange?style=flat-square)
![year](https://img.shields.io/badge/capstone-2026-lightgrey?style=flat-square)
![team](https://img.shields.io/badge/team-3%20members-lightgrey?style=flat-square)

---

## overview

A business intelligence initiative analyzing which game attributes are most associated with higher net revenue among the top 1,500 revenue-generating titles on Steam. Framed for an audience of game developers, publishers, and platform operators looking to understand what separates high-performing titles from the rest.

---

## dataset

**Top 1,500 Games on Steam by Revenue** · Kaggle, September 2024

| feature | description |
|--------|-------------|
| Price | Listed sale price of the game |
| Review Score | Aggregate user review percentage |
| Publisher Class | AAA / AA / Indie classification |
| Average Playtime | Mean hours played per user |
| Release Date | Original launch date |
| Net Revenue | Target variable (log-transformed) |

---

## research dimensions

Each dimension is owned by one team member:

- **Publisher Class** — AAA vs. AA vs. Indie
- **Price Tier** — Free / Under $20 / $20–$40 / $40+
- **Review Score** — High vs. Low (above / below 70%)

---

## methods

| method | purpose |
|--------|---------|
| Multiple Linear Regression | Baseline revenue prediction |
| Random Forest | Non-linear pattern detection |
| K-Fold Cross Validation (k=5) | Model validation & generalizability |

---

## bi deliverables

- 📊 Revenue dashboard
- 💰 Price tier comparison panel
- 🌲 Feature importance report
- 📄 Insight brief

---

## key limitation

This dataset is limited to already high-performing titles. Findings reflect patterns among top-grossing games and may not generalize to the broader Steam library.

---
 
## progress log
 
| date | milestone | status | file |
|------|-----------|--------|--------|
| 04/27/2026 | Data Preparation | ✅ Completed | [Progress Log #1](./ProjectProgressLog1_cvaranko.pdf) |
| 05/11/2026 | Model Design | ✅ Completed | [Progress Log #2](./ProjectProgressLog2_cvaranko.pdf) |
| 05/26/2026 | Model Implementation | ⌛ In Progress | - |
| 06/01/2026 | Model Improvement | 🔜 Not Started | - |
| 06/08/2026 | PowerPoint Draft | 🔜 Not Started | - |
 
---

*Project in progress — expected completion June 21st, 2026.*
