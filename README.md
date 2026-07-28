# predicting game revenue on steam
### what drives financial success among top-selling titles?

![status](https://img.shields.io/badge/status-completed-brightgreen?style=flat-square)
![year](https://img.shields.io/badge/capstone-2026-lightgrey?style=flat-square)
![team](https://img.shields.io/badge/team-3%20members-lightgrey?style=flat-square)

---

## overview

A business intelligence initiative analyzing which game attributes are most associated with higher net revenue across Steam games. Using Gamalytic Steam analytics data, the project examines revenue performance patterns across publisher class, pricing, review performance, player engagement, and market demand. Framed for an audience of game developers, publishers, and platform operators looking to understand what separates high-performing titles from the rest.

---

## dataset

**Gamalytic Steam Analytics Data** · Spring 2026

Two datasets were used, both sourced from Gamalytic and sharing the same base population of 10,638 Steam game titles (500+ reviews, revenue > 0, base price > 0). After excluding Hobbyist titles and incomplete rows, the final dataset used for modeling contained 10,572 observations.

| variable | type | description |
|----------|------|-------------|
| name | Text | Title of the Steam game |
| releaseDate | Date | Date the game was released on Steam |
| copiesSold | Numeric | Estimated total units sold |
| price | Numeric | Game retail price in USD |
| revenue | Numeric | Estimated gross revenue (USD) — primary outcome variable |
| averagePlaytime | Numeric | Mean hours played per player |
| reviewScore | Numeric | Aggregate player review score (0–100 scale) |
| publisherClass | Categorical | AAA / AA / Indie classification |
| reviewCount | Numeric | Total volume of player reviews (Random Forest predictor) |
| wishlists | Numeric | Number of Steam wishlists (Random Forest predictor) |

---

## research dimensions

Each dimension is owned by one team member:

- **Publisher Class** — AAA vs. AA vs. Indie revenue performance
- **Price Tier** — Free / Under $20 / $20–$40 / $40+
- **Review Score Tier** — Mixed / Positive / Very Positive / Overwhelmingly Positive

---

## methods

| method | purpose |
|--------|---------|
| Descriptive Statistics | Summarize revenue distributions across dimensions |
| Welch ANOVA + Tukey HSD | Test for significant differences across publisher class and review tier groups |
| Multiple Linear Regression | Baseline revenue prediction with transformed predictors |
| K-Fold Cross Validation (k=5) | Model validation & generalizability |
| Random Forest (500 trees) | Non-linear pattern detection and feature importance ranking |

### data transformations

| variable | transformation | reason |
|----------|---------------|--------|
| revenue | log10 | Heavy right skew |
| copiesSold | log10 | Heavy right skew |
| averagePlaytime | log10(x + 1) | Heavy right skew; zero values present |
| price | square root | Moderate right skew |
| reviewScore | sqrt(k − x) | Moderate left skew; reflect-and-root |

---

## key findings

- **Publisher class** is strongly associated with revenue. AAA titles represent 9.7% of games but capture 44.3% of total revenue. Indie titles make up 70.3% of games but only 19.5% of revenue.
- **Price tier** is a statistically significant predictor. Premium pricing ($40+) is most strongly associated with higher revenue. Competing on low price alone is the least effective strategy.
- **Review score** has a statistically significant but practically modest relationship with revenue. Very Positive and Overwhelmingly Positive games showed no significant revenue difference (p = 0.9986). Review volume is a stronger predictor than review score.
- **Regression final model** (R² = 0.488) identified log_avgPlaytime, sqrt_price, and publisher_Indie as the three significant predictors of log revenue.
- **Random Forest** (R² = 0.907, RMSE = 0.242, MAE = 0.189) identified review count as the strongest predictor, followed by wishlists, price, and average playtime.

---

## content

- 📂 Data preparation & cleaning
- 📊 Dimension analyses
- 📈 Regression analysis (3 model specifications)
- 🌲 Random Forest analysis (R² = 0.907)
- 💡 Business recommendations

---

## key limitation

Revenue figures are Gamalytic estimates, not officially reported values. Gamalytic uses a proprietary method informed by review counts, player activity, and review-to-sales ratios. Findings should be interpreted as market-performance estimates. Direct revenue-linked fields were excluded from modeling to avoid data leakage.

---

## 📋 progress log

| date | milestone | status | file |
|------|-----------|--------|------|
| 04/27/2026 | Data Preparation | ✅ Completed | [Progress Log #1](./ProjectProgressLog1_cvaranko.pdf) |
| 05/11/2026 | Model Design | ✅ Completed | [Progress Log #2](./ProjectProgressLog2_cvaranko.pdf) |
| 05/26/2026 | Model Implementation | ✅ Completed | [Progress Log #3](./ProjectProgressLog3_cvaranko.pdf) |

---

## team

| member | dimension |
|--------|-----------|
| Carolina Varanko | Price Tier · Regression Analysis |
| Student #1 | Publisher Class · Random Forest |
| Student #2 | Review Score Tier |

---

*Project completed — Spring 2026 · DATA 485*
