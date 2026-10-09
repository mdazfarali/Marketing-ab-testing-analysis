# Executive Summary — Marketing A/B Testing

## Decision
**Statistically positive, profitability unproven.** The Ad group converted more often than the PSA control group, but the dataset has no actual revenue or advertising-cost data. Do not claim the campaign is profitable until unit economics are verified.

## Main results
- **Ad conversion rate:** 2.555%
- **PSA conversion rate:** 1.785%
- **Absolute difference:** +0.769 percentage points
- **Relative lift:** +43.09%
- **95% confidence interval:** +0.595 to +0.943 percentage points
- **Two-proportion z-test:** z = 7.370, p ≈ 1.71 × 10⁻¹³
- **SRM check:** p ≈ 0.9998; observed split matches the expected 96% Ad / 4% PSA allocation.
- **Estimated incremental conversions:** approximately 4,343 (approximate CI-scaled range: 3,360–5,326).

## Business scenario
At an illustrative cost of ₹0.50 per impression, estimated ad cost is approximately ₹70.07 lakh. With illustrative conversion values of ₹100, ₹250, and ₹500, ROI is negative in all three scenarios. Break-even is approximately ₹1,613 per incremental conversion, or an impression cost of about ₹0.077 at ₹250 per conversion.

**These financial values are illustrative, not actual campaign economics.**

## Recommended next actions
1. Obtain real cost per impression and contribution margin per conversion.
2. Replace the assumptions and rerun the sensitivity analysis.
3. Test ad frequency with a randomized frequency-cap experiment.
4. Treat exposure, day, and time segments as descriptive because they use post-treatment behaviour.
