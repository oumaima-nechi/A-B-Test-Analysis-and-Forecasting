
# Search Ranking System A/B Test Analysis and Forecasting

![A/B Testing Illustration]()


## 🔍 Project Overview
This project evaluates the effectiveness of a new search ranking system for an online travel agency (OTA) and forecasts its business impact. The primary goal is to determine whether the new ranking algorithm increases booking conversions without negatively impacting the time it takes users to make a booking, and to forecast the expected conversion lift when fully deployed.

## 💼 Business Context
Optimizing search results can significantly impact user experience and conversion rates in e-commerce and travel platforms. This A/B test aims to validate whether the new search ranking system delivers better results that lead to more bookings without increasing friction in the booking process.

## 💻 Development Environment
This project was developed using DataLab, a powerful interactive computing environment for data science. DataLab provided the Jupyter notebook interface used to conduct the analysis, with built-in support for Python libraries essential for A/B test analysis.

## 📊 Data Sources
The analysis uses two primary data sources:
- `sessions_data.csv`: Contains session-level data including session IDs, user IDs, timestamps, and booking information
- `users_data.csv`: Contains user experiment group assignments (control vs. variant)

## 📏 Metrics
The experiment analyzes two key metrics:
1. **Primary Metric**: Conversion rate (whether a session resulted in a booking)
2. **Guardrail Metric**: Time to booking (minutes from session start to booking completion)

## ✅ Success Criteria
The experiment is considered successful and ready for full rollout if:
- The primary metric (conversion) shows a statistically significant positive effect
- The guardrail metric (time_to_booking) either shows no statistically significant change or a positive effect (decrease in time)

## 🔬 Methodology
The analysis follows these steps:
1. Data preprocessing and joining session data with experiment group assignments
2. Computing conversion as a binary flag (1 if booking occurred, 0 otherwise)
3. Performing a Sample Ratio Mismatch (SRM) test to ensure balanced experiment groups
4. Analyzing the primary metric using a z-test for proportions and calculating effect size
5. Analyzing the guardrail metric using a t-test and calculating effect size
6. Making a decision based on statistical significance and effect direction

## 📈 Statistical Analysis
- **Confidence Level**: 90% (α = 0.10)
- **Statistical Tests**:
  - Chi-square test for Sample Ratio Mismatch
  - Z-test for conversion rate comparison
  - T-test for time-to-booking comparison

## 🧮 Results

### Sample Ratio Mismatch Test
- Control group: 7,630 sessions
- Variant group: 7,653 sessions
- p-value: 0.8524
- Interpretation: No significant imbalance between control and variant group sizes

### Primary Metric (Conversion)
- p-value: 0.0002
- Effect size: +14.22%
- Interpretation: Statistically significant increase in conversion rate

### Guardrail Metric (Time to Booking)
- p-value: 0.5365
- Effect size: -0.79%
- Interpretation: No statistically significant change in time to booking

## 🎯 Conclusion
Based on the results, the new search ranking system demonstrates a strong positive impact on conversion rate with a 14.22% increase that is statistically significant. The time to booking (guardrail metric) showed a minor decrease of 0.79%, but this change was not statistically significant.

Since the primary metric shows significant improvement and the guardrail metric was not negatively affected, the recommendation is to proceed with full rollout of the new search ranking system.

## 🛠️ Implementation
The analysis was performed using Python in DataLab with the following key libraries:
- pandas: Data manipulation and analysis
- scipy.stats: Statistical testing
- pingouin: Advanced statistical tests
- statsmodels: Statistical models and tests

All code is contained in the `notebook.ipynb` Jupyter notebook file, which includes data loading, preprocessing, analysis, and visualization steps.
