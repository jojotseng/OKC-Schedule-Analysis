# NBA Schedule Analysis Project

**Author:** Joseph Tseng  
**Date:** August 2025  
**Organization:** Oklahoma City Thunder Data Science Assessment

---

## 📋 Project Overview

This project analyzes NBA scheduling patterns and their impact on team performance from 2014-2024. The analysis includes schedule density metrics, travel burden calculations, rest day patterns, and predictive modeling to quantify how schedule-related factors affect regular season wins.

### Key Objectives
1. Analyze scheduling trends and identify patterns in back-to-back games, rest days, and travel
2. Develop interactive visualization tools for schedule analysis
3. Build machine learning models to estimate schedule impact on team wins (2019-2024)

---

## 🎯 Key Findings

### Schedule Trends (2014-2024)
- **Back-to-back games reduced by ~23%** across the league
- **Average rest days increased by 11.7%** (1.69 → 1.89 days)
- **4-in-6 game stretches decreased** from 27.1 to 23.4 per team per season
- **Prime-time game distribution shifted** toward Tuesday/Wednesday games

### Schedule Impact on Wins (2019-2024)
Using an ensemble Random Forest model with cross-validation:
- **Most helped by schedule:** LAC (+14.5 wins over 5 seasons)
- **Most hurt by schedule:** DET (-17.0 wins over 5 seasons)
- **Model performance:** R² = 0.29 (CV), explaining ~29% of win variance
- **Top predictive factors:** Opponent strength (55%), travel burden (18%), rest patterns (15%)

### 2024-25 OKC Thunder Schedule Analysis
- **17 back-to-back games** (favorable vs. league average)
- **Peak density:** 5 games in 7 days (January 3rd)
- **Total travel:** 41,956 miles (below Western Conference average)
- **Strategic advantages:** Well-distributed rest periods during playoff race

---

## 📊 Methodology

### Part 1: Schedule Analysis
Analyzed 2014-2024 NBA schedules to identify:
- 4-in-6 game stretches (sliding 6-night windows)
- Back-to-back games frequency
- Rest day patterns and distributions
- Team-specific scheduling anomalies

**Technical Approach:**
- Sliding window analysis for game density metrics
- Per-82-game normalization for cross-season comparisons
- Statistical variance analysis to assess scheduling fairness

### Part 2: Trend Visualization
Created comprehensive visualizations showing:
- Reduction in high-density game periods over time
- Evolution of weekly game distribution patterns
- Travel distance trends and patterns
- Monthly game distribution changes

**Key Techniques:**
- Time-series analysis with rolling averages
- Heatmap visualizations for weekly game density
- Multi-panel comparative plots for trend identification

### Part 3: Predictive Modeling
Built machine learning models to quantify schedule impact on wins:

**Model Architecture:**
- **Algorithm:** Random Forest Regressor (ensemble approach)
- **Features:** 14 curated schedule factors including:
  - Travel metrics (distance, high-travel games, burden scores)
  - Rest factors (back-to-backs, average rest, short rest games)
  - Schedule density (7-day rolling windows, high-density periods)
  - Opponent strength (average win%, SOS, games vs. strong teams)
  - Home/away balance

**Validation Strategy:**
- 5-fold cross-validation for robust performance estimation
- TimeSeriesSplit for temporal validation
- Multiple model comparison (Random Forest, Gradient Boosting, Ridge, ElasticNet)

**Model Performance:**
- Cross-validation R²: 0.291
- Training R²: 0.894
- RMSE: 3.2 wins per season
- MAE: 2.4 wins per season

---

## 🛠️ Technical Stack

### Languages & Libraries
- **Python 3.x**
  - `pandas` - Data manipulation and analysis
  - `numpy` - Numerical computing
  - `scikit-learn` - Machine learning models and validation
  - `plotly` - Interactive visualizations
  - `matplotlib` & `seaborn` - Statistical plotting

### Key Algorithms
- Random Forest Regression (primary model)
- Gradient Boosting (comparison)
- Ridge Regression (regularization comparison)
- Haversine formula for geographic distance calculations

### Data Processing
- DateTime manipulation for schedule analysis
- Rolling window calculations for density metrics
- Feature engineering with polynomial interactions
- StandardScaler normalization for model inputs

---

## 📁 Project Structure

```
nba-schedule-analysis/
├── data/
│   ├── schedule.csv              # Game schedules 2014-2024
│   ├── schedule_24_partial.csv   # 2024-25 draft schedules
│   ├── locations.csv             # Team location coordinates
│   └── team_game_data.csv        # Historical game results
├── notebooks/
│   └── schedule_analysis.ipynb   # Main analysis notebook
├── visualizations/
│   ├── okc_schedule_dashboard/   # Interactive OKC schedule plots
│   └── den_schedule_dashboard/   # Interactive DEN schedule plots
├── models/
│   └── schedule_impact_model.pkl # Trained ML model
├── README.md
└── requirements.txt
```

---

## 🎨 Visualizations

### Interactive Schedule Dashboard
Created comprehensive interactive visualization tool featuring:
- **Game Density Plot:** 7-day rolling window with high-density markers
- **Rest Days Analysis:** Color-coded bar charts for rest patterns
- **Travel Analysis:** Distance tracking with cumulative burden metrics
- **Schedule Calendar Heatmap:** Difficulty scores across the season
- **Home/Away Timeline:** Visual roadmap of location changes

**Features:**
- Hover tooltips with detailed game information
- Zoom and pan capabilities for period-specific analysis
- Anomaly highlighting (back-to-backs, high travel, dense periods)
- Comparative analysis between teams

### Key Insights Visualized
1. NBA league-wide trend toward player health optimization
2. OKC's favorable 2024-25 schedule positioning
3. Schedule impact distribution across all 30 NBA teams
4. Feature importance rankings in predictive models

---

## 📈 Results & Impact

### Business Value
1. **Strategic Planning:** Identified optimal rest periods for load management
2. **Performance Prediction:** Quantified schedule-related win expectations
3. **Competitive Analysis:** Compared schedule difficulty across teams
4. **Resource Allocation:** Highlighted high-stress periods for staffing

### Statistical Insights
- Schedule factors explain ~29% of win variance (significant real-world impact)
- Charlotte (CHA) faced most 4-in-6 stretches historically (28.1 avg)
- New York (NYK) faced fewest 4-in-6 stretches (22.2 avg)
- Difference likely due to random variation rather than systematic bias

### Model Validation
- Cross-validation ensures generalizability
- Feature importance aligns with basketball domain knowledge
- Residual analysis shows no systematic bias by team or season
- Out-of-sample predictions realistic and actionable

---

## 🚀 Key Learnings

### Technical Skills Demonstrated
- Advanced time-series analysis for sports scheduling
- Geographic calculations using Haversine distance formula
- Ensemble machine learning with proper validation techniques
- Interactive data visualization with Plotly
- Feature engineering for complex domain problems

### Domain Expertise
- NBA scheduling constraints and competitive balance
- Player fatigue and rest impact on performance
- Travel burden quantification for professional sports
- Schedule optimization trade-offs

### Data Science Best Practices
- Rigorous cross-validation to prevent overfitting
- Multiple model comparison for robust conclusions
- Clear documentation and reproducible analysis
- Business-focused presentation of technical results

---

## 📊 Sample Visualizations

### Schedule Impact by Team (2019-2024)
```
Most Helped:
  LAC: +14.5 wins
  PHX: +12.9 wins
  LAL: +11.3 wins

Most Hurt:
  DET: -17.0 wins
  WAS: -14.9 wins
  POR: -11.0 wins
```

### OKC 2024-25 Schedule Metrics
- **Back-to-backs:** 17 games
- **Peak density:** 5 games / 7 days (Jan 3)
- **Longest trip:** 1,493 miles to Boston
- **Home games:** 40 of 80 (50%)
- **Rest advantage:** 3 periods with 3+ days rest

---

## 🔍 Future Enhancements

### Potential Extensions
1. **Real-time tracking:** Live dashboard updates during season
2. **Injury modeling:** Incorporate injury risk based on schedule factors
3. **Opponent-specific effects:** Model performance vs. specific teams under fatigue
4. **Optimization algorithm:** Generate optimal schedules given constraints
5. **Player-level analysis:** Individual load management recommendations

### Additional Research Questions
- How do playoff seeding races interact with schedule difficulty?
- What is the marginal effect of each additional mile of travel?
- Do teams adapt their strategies based on schedule density?
- How have recent rule changes affected scheduling patterns?

---

## 💡 Conclusions

This analysis demonstrates that **NBA schedule factors have measurable and significant impacts on team performance**, with the most extreme cases showing 15+ win swings over five seasons. The NBA's ongoing efforts to reduce back-to-back games and increase rest days represent meaningful improvements in player health and competitive balance.

Key takeaways:
1. **Scheduling matters:** Can swing 3-4 wins per season for typical teams
2. **Travel burden is real:** High-mileage teams face measurable disadvantages  
3. **Rest days critical:** Back-to-backs and short rest significantly impact performance
4. **Opponent strength dominant:** Schedule difficulty primarily driven by who you play, not when
5. **Recent improvements:** League-wide trends show commitment to player welfare

The interactive visualization tools and predictive models provide actionable insights for front office decision-making, coaching staff preparation, and strategic planning.

---

## 📧 Contact

**Joseph Tseng**  
Data Scientist | Sports Analytics Enthusiast  
[GitHub](https://github.com/yourusername) | [LinkedIn](https://linkedin.com/in/yourprofile) | [Email](mailto:your.email@example.com)

---

## 📄 License

This project was completed as part of an NBA team assessment. Data sources are proprietary and not included in this repository.

---

## 🙏 Acknowledgments

- Oklahoma City Thunder organization for the opportunity
- NBA for comprehensive scheduling data
- The data science and sports analytics community for methodological inspiration

---

*Last Updated: October 2025*
