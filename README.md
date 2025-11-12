## Task 1 Retention Modeling and Revenue Simulation

This task aimed to model user retention behavior, simulate daily active users (DAU), estimate monetization through ads and in-app purchases (IAP), and evaluate two variants (A and B) under different business scenarios.

### Retention Modeling

Four retention functions were evaluated—Power Law, Logarithmic, Inverse, and Exponential—against observed retention points (D1, D3, D7, D14) for both variants.

<img width="434" height="172" alt="Screenshot 2025-11-12 at 23 50 57" src="https://github.com/user-attachments/assets/4dac97be-6afd-44ef-a748-5e680bb1ff2e" />


> Power Law achieved the highest average R² and was the best overall fit for both variants. However, the Exponential model was chosen for revenue simulations due to its alignment with many real-world retention decay patterns which can be seen plots below.

 <img width="1251" height="624" alt="Screenshot 2025-11-12 at 23 51 24" src="https://github.com/user-attachments/assets/27ef9b78-2a77-4aa9-ab81-6de93f867627" />
<img width="1246" height="621" alt="Screenshot 2025-11-12 at 23 51 37" src="https://github.com/user-attachments/assets/71e0bbdb-386d-472c-8241-1dc03e638c27" />


### DAU and Revenue Simulation

With an exponential retention model, DAU was simulated for 15 and 30 days, and revenue was calculated using each variant's:
- Purchase rate
- Ad impressions per DAU
- eCPM
- A range of ARPPU values (from $1.0 to $5.0)

<img width="911" height="328" alt="Screenshot 2025-11-12 at 23 51 49" src="https://github.com/user-attachments/assets/ea6c6b1e-6e1a-4350-a02e-0b3a87cd22c6" />


### Critical ARPPU Calculation

The critical ARPPU—the breakeven point at which both variants yield equal revenue—was computed at:

> Critical ARPPU = $3.05

This means:
- If ARPPU is below $3.05, Variant A is more profitable.
- If ARPPU is above $3.05, Variant B is more profitable.

### Revenue Comparison Scenarios

<img width="535" height="238" alt="Screenshot 2025-11-12 at 23 51 59" src="https://github.com/user-attachments/assets/a691d74b-cb19-449d-971d-a8c321313a2d" />


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

<img width="946" height="558" alt="Screenshot 2025-11-12 at 23 53 18" src="https://github.com/user-attachments/assets/b70e0a04-6615-4247-b601-70f36a0481dd" />
<img width="1184" height="189" alt="Screenshot 2025-11-12 at 23 53 25" src="https://github.com/user-attachments/assets/506ee07a-704e-43be-9099-ae41f296e987" />



### 2. Revenue-Based Segmentation (Only Spenders)

- High spenders were significantly more engaged: over **3100 seconds** of gameplay and nearly **8 matches started** on average.
- Medium and low spenders showed less engagement and contributed very little revenue.
- Most monetization came from high-value users, reinforcing the importance of early detection and retention.
<img width="919" height="570" alt="Screenshot 2025-11-12 at 23 53 48" src="https://github.com/user-attachments/assets/1b4fd4b9-9ac5-4bfc-9fb1-41ee063d1cae" />

### 3. Skill-Based Segmentation (Win Rate)

- Users were grouped based on win rate (victory_count / match_end_count), using only those who completed ≥5 matches.
- Surprisingly, **low-skill users played more and stayed longer**, suggesting more time is needed for progression.
- Revenue per user was **nearly equal across all skill levels**, showing skill alone doesn’t predict monetization.
<img width="937" height="182" alt="Screenshot 2025-11-12 at 23 53 58" src="https://github.com/user-attachments/assets/3f2a1cc9-e3d1-4faa-917e-ce59bcd8f54c" />

## Trend Observation

- Average daily session count and duration both **increased over time**, especially for retained users.
- This suggests that long-term users become progressively more engaged.

<img width="1131" height="569" alt="Screenshot 2025-11-12 at 23 52 59" src="https://github.com/user-attachments/assets/54668e06-a45e-415c-830f-a00d92cc184a" />


## Final Insights

- Strong early engagement (especially long Day 1 sessions) is a clear predictor of future monetization.
- Low-skill or medium-engaged users may still be monetization-worthy and should not be ignored.
- Targeting and retaining high-time, high-engagement users is critical, as they drive nearly all revenue.
<img width="912" height="557" alt="Screenshot 2025-11-12 at 23 52 31" src="https://github.com/user-attachments/assets/55bef0f7-b442-40c6-8a80-b78b2d6846b5" />
<img width="908" height="567" alt="Screenshot 2025-11-12 at 23 52 48" src="https://github.com/user-attachments/assets/2b270628-3d89-4774-a1b4-e37e9121b445" />

