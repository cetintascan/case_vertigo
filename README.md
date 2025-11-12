## Task 1 Retention Modeling and Revenue Simulation

This task aimed to model user retention behavior, simulate daily active users (DAU), estimate monetization through ads and in-app purchases (IAP), and evaluate two variants (A and B) under different business scenarios.

### Retention Modeling

Four retention functions were evaluated—Power Law, Logarithmic, Inverse, and Exponential—against observed retention points (D1, D3, D7, D14) for both variants.

| Model        | R² A  | R² B  | Avg R² | DAU A | DAU B |
|--------------|-------|-------|--------|--------|--------|
| Power Law    | 0.985 | 0.984 | 0.985  | 54685  | 56474  |
| Logarithmic  | 0.977 | 0.960 | 0.969  | 54256  | 56981  |
| Inverse      | 0.983 | 0.940 | 0.961  | 49216  | 46939  |
| Exponential  | 0.952 | 0.901 | 0.926  | 50011  | 54454  |

> Power Law achieved the highest average R² and was the best overall fit for both variants. However, the Exponential model was chosen for revenue simulations due to its alignment with many real-world retention decay patterns.

### DAU and Revenue Simulation

With an exponential retention model, DAU was simulated for 15 and 30 days, and revenue was calculated using each variant's:
- Purchase rate
- Ad impressions per DAU
- eCPM
- A range of ARPPU values (from $1.0 to $5.0)

### Critical ARPPU Calculation

The critical ARPPU—the breakeven point at which both variants yield equal revenue—was computed at:

> Critical ARPPU = $3.05

This means:
- If ARPPU is below $3.05, Variant A is more profitable.
- If ARPPU is above $3.05, Variant B is more profitable.

### Revenue Comparison Scenarios

| Scenario                                | Variant A    | Variant B    | Winner |
|----------------------------------------|--------------|--------------|--------|
| 1a – DAU @ Day 15                      | 50,011       | 54,454       | B      |
| 1b – Revenue by Day 15                 | $100,202.61  | $102,003.50  | B      |
| 1c – Revenue by Day 30                 | $100,202.61  | $102,003.50  | B      |
| 1d – 10-Day Sale (Day 15–24)           | $261,095.22  | $282,668.86  | B      |
| 1e – New Source Mix from Day 20        | $230,689.88  | $247,250.01  | B      |
| 1f – Only New Source (30-Day)          | $209,551.28  | $206,636.88  | A      |

### Insights and Recommendations

- Variant B consistently outperformed Variant A in most scenarios, especially in terms of DAU and revenue over both 15- and 30-day periods.
- Introducing a 10-day sale (with a 1% boost in purchase rate) significantly increased total revenue, with Variant B gaining the most from the uplift.
- Adding a new user source from Day 20 increased traffic but introduced quality concerns. When modeled exclusively (scenario 1f), the new source favored Variant A, suggesting it adversely impacts Variant B more.
- In practical terms, the 10-day sale had the highest incremental value and should be prioritized over acquiring lower-retention traffic.

# Task 2 Summary

This analysis explores user behavior and monetization patterns in a mobile game dataset, focusing on segmentation and behavioral trends within the first 30 days of gameplay.

## Data Cleaning and Preparation

- Filtered out rows with missing IDs, invalid sessions or revenue, and ensured proper datetime formats.
- Computed `days_since_install` to track user behavior relative to install date.

## Key Segmentation Analyses

### 1. Time Spent Segmentation (Low / Medium / High)

- High-time users generated nearly **100% of the total revenue**, with most coming from in-app purchases.
- These users played the most matches and had the longest session durations.
- Match completion rate was also high among these users, indicating stronger engagement quality.

### 2. Revenue-Based Segmentation (Only Spenders)

- High spenders were significantly more engaged: over **3100 seconds** of gameplay and nearly **8 matches started** on average.
- Medium and low spenders showed less engagement and contributed very little revenue.
- Most monetization came from high-value users, reinforcing the importance of early detection and retention.

### 3. Skill-Based Segmentation (Win Rate)

- Users were grouped based on win rate (victory_count / match_end_count), using only those who completed ≥5 matches.
- Surprisingly, **low-skill users played more and stayed longer**, suggesting more time is needed for progression.
- Revenue per user was **nearly equal across all skill levels**, showing skill alone doesn’t predict monetization.

## Trend Observation

- Average daily session count and duration both **increased over time**, especially for retained users.
- This suggests that long-term users become progressively more engaged.

## Final Insights

- Strong early engagement (especially long Day 1 sessions) is a clear predictor of future monetization.
- Low-skill or medium-engaged users may still be monetization-worthy and should not be ignored.
- Targeting and retaining high-time, high-engagement users is critical, as they drive nearly all revenue.

