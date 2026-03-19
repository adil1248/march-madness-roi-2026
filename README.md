# The March to Impact

**Which March Madness Teams Actually Move the Wage Needle?**

An interactive data visualization ranking all 68 teams in the 2026 NCAA Men's Basketball Tournament by how much they actually raise graduates' wages — adjusted for regional cost of living, dropout rates, and school accessibility.

## 🔗 Live Site

**[View the interactive visualization →](https://adil1248.github.io/march-madness-roi-2026/)**

## 📊 What This Shows

Most college ROI rankings use raw salary numbers and ignore the reality that:
- A $55K salary in Iowa buys more than $65K in New York
- 35% graduation rates mean 65% of students paid tuition but got no degree
- Elite schools with 5% acceptance rates only impact a tiny fraction of students

This analysis fixes that by:

### 1. **Regional Cost-of-Living Adjustment**
Using BEA Regional Price Parities (2024), all earnings are converted to real purchasing power. Regional schools are compared to their local HS baseline, not the national average.

### 2. **Dropout Penalty**
Graduation rates determine actual outcomes. Dropouts get zero earnings boost but still paid tuition for 2 years.

### 3. **Accessibility & Scale**
The "Impact Score" weights ROI by acceptance rate and enrollment. A large state school with 80% acceptance and decent ROI beats a tiny elite school with amazing ROI but 5% acceptance.

## 🎯 Key Findings

- **X of 68 teams have negative adjusted ROI** — graduates literally earn less than local HS-only workers
- **Large accessible state schools dominate** when you factor in scale
- **Low-COL states (Iowa, Kansas, Arkansas) get huge boosts** — modest salaries go much further
- **Elite schools (Penn, Duke, Vanderbilt)** have incredible per-student ROI but low Impact scores due to tiny enrollment

## 📈 Data Sources

- **Earnings**: U.S. Dept. of Education College Scorecard (median earnings 10 years after enrollment)
- **Cost of Living**: Bureau of Economic Analysis Regional Price Parities (2024)
- **HS Baseline**: Bureau of Labor Statistics CPS Q1 2025 ($50K/yr national median for HS-diploma-only workers)
- **Graduation Rates**: IPEDS 6-year graduation rates
- **ROI Framework**: Georgetown CEW "Ranking 4,600 Colleges by ROI" (2025)
- **Acceptance Rates & Enrollment**: Common Data Sets 2024-25

## 🧮 Methodology

### Step 1: State HS Baseline
Nationally, full-time HS-only workers earn median $50K/yr (BLS). This scales by state RPP:
- Iowa (RPP 87.8) → $43.9K baseline
- New York (RPP 106.2) → $53.1K baseline
- California (RPP 110.7) → $55.4K baseline

### Step 2: Draw Classification
- **National** (≤25% acceptance): Compared to national baseline
- **Broad** (26-60% acceptance): 50/50 blend
- **Regional** (>60% acceptance): Compared to state baseline

### Step 3: COL-Adjusted Earnings
```
Real Earnings = Nominal × (100 / RPP)
```

### Step 4: True Annual Gain vs. HS
```
COL-Adjusted Earnings - Blended HS Baseline
```

### Step 5: Adjusted ROI (lifetime)
```
(GradRate × AnnualGain × 40yrs - Tuition × 4.5yrs) + 
((1 - GradRate) × (0 - Tuition × 2yrs))
```

Graduates get 40-year premium minus tuition. Dropouts get zero premium but still paid 2 years tuition.

### Step 6: Impact Score
```
AdjROI × (AcceptRate / 50) × log₂(Enrollment / 5K)
```

Weights ROI by accessibility and scale.

## 🛠️ Built With

- HTML/CSS/JavaScript
- No frameworks — vanilla JS for maximum portability
- Hand-compiled data from federal sources

## 📄 License

MIT License — feel free to fork, modify, and use this methodology for other datasets.

## 🏀 About

Created for March Madness 2026. All 68 tournament teams ranked by actual wage impact.

---

**Methodology details, sources, and assumptions are fully documented in the interactive glossary and methodology panels on the live site.**
