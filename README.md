# Marketing A/B Testing Conversion Impact Analysis

## Business problem
Evaluate whether users assigned to the Ad group converted at a higher rate than users assigned to the PSA control group, quantify uncertainty, and assess whether the result could be commercially attractive under explicit assumptions.

## Dataset
- File: `marketing_AB.csv`
- Rows: 588,101 users
- Groups: Ad and PSA
- Outcome: `converted`
- Behavioural fields: `total ads`, `most ads day`, `most ads hour`

The dataset does not include actual revenue, margin, or advertising costs.

## Methods
1. Data quality checks: missing values, unique user IDs, and removal of the sequential `Unnamed: 0` index column.
2. Sample Ratio Mismatch (SRM) goodness-of-fit test against the documented 96% Ad / 4% PSA allocation.
3. Conversion rates, absolute difference in percentage points, relative lift, 95% confidence interval, and two-proportion z-test.
4. 5,000-iteration bootstrap confidence interval.
5. Power / minimum detectable effect (MDE).
6. Descriptive segment comparisons by observed ad-exposure bucket, day with most ads, and time block.
7. Holm and Benjamini–Hochberg multiple-testing adjustments for the 14 segment comparisons.
8. Illustrative business impact, ROI sensitivity, and break-even calculations.

## Key findings
- Ad group conversion rate: **2.555%**.
- PSA group conversion rate: **1.785%**.
- Absolute difference: **+0.769 percentage points**.
- Relative lift: **+43.09%**.
- Analytical 95% CI for the difference: approximately **+0.595 to +0.943 percentage points**.
- Two-proportion z-test: **z = 7.370**, **p ≈ 1.71 × 10⁻¹³**.
- SRM test: **p ≈ 0.9998**; no evidence of mismatch with the expected 96% / 4% allocation.
- Estimated incremental conversions in the Ad group versus applying the PSA rate: approximately **4,343**; the confidence-interval-scaled range is approximately **3,360 to 5,326**.
- Under the illustrative assumption of ₹0.50 per ad impression, estimated spend is about **₹70.07 lakh** and the scenario ROI is negative in the Low, Base, and High conversion-value cases.
- At the assumed ₹0.50 impression cost, break-even requires about **₹1,613 per incremental conversion**. These are scenario calculations, not observed campaign financials.

## Recommendation
Do not make a profitability decision until actual cost per impression and contribution margin per conversion are available. Recalculate the scenario table with finance-approved values. Consider a separately randomized frequency-cap experiment to test whether limiting or changing ad frequency changes conversion.

## Limitations
- The control group received PSAs, so the comparison is Ad versus PSA, not Ad versus no advertising.
- A causal interpretation of the overall group difference depends on the experiment's random assignment being implemented correctly.
- `total ads`, `most ads day`, and `most ads hour` are post-treatment behavioural variables. Segment analyses using them are descriptive and do not prove that more exposure or a particular time/day causes conversion.
- Revenue, contribution margin, and ad cost are absent; ROI figures rely on illustrative assumptions.
- Multiple-testing corrections cover the 14 segment comparisons, not every analysis in the notebook.

## How to run
1. Download this notebook and `marketing_AB.csv`.
2. Keep both files in the same folder, or upload the CSV into your Google Colab session.
3. Run the notebook from top to bottom.
4. Review the scenario assumptions in Section 9 and replace them with real business inputs before using the ROI recommendation.
