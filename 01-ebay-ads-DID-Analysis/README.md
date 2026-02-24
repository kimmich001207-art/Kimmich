# Project Showcase: In-Depth Evaluation of eBay Search Ads ROI via Causal Inference Framework

### 1. Business Context & Core Questions
In Search Engine Marketing (SEM), organizations frequently face a classic attribution dilemma: **Do paid search ads drive truly incremental sales, or do they merely cannibalize organic search traffic that would have occurred anyway (the substitution effect)?**
To precisely evaluate the true Return on Investment (ROI) of search ads, eBay conducted an A/B experiment across selected Designated Market Areas (DMAs) in the US. Search advertising was completely paused in the treatment DMAs, while the control DMAs maintained their regular ad campaigns. This project leverages advanced causal inference models to isolate natural market fluctuations and quantify the true business impact of pausing these ads.

### 2. Analytical Framework & Methodology
To derive the most rigorous business conclusions, this project moved beyond simple mean comparisons and deployed a comprehensive econometric causal inference framework:
* **Core Model Evolution:** Starting with a baseline Difference-in-Differences (DID) model that incorporated `Population` as a scaling factor for heteroskedasticity, the analysis was ultimately upgraded to a **Two-Way Fixed Effects (TWFE) model**.
* **Noise Pulverization Mechanism:** By introducing DMA Fixed Effects, the model perfectly absorbed long-term economic and cultural baseline differences across regions. The inclusion of Date Fixed Effects effectively stripped away macro-level volatility and day-of-week seasonality affecting the entire network.
* **Cross-Validation:** A **Synthetic Control Method (SCM)** was additionally introduced, utilizing machine-learning-optimized weights to "clone" a synthetic treatment group from the donor pool, providing an epic cross-validation against the TWFE model.

### 3. Key Metric Findings
Based on the daily baseline levels of the control group prior to the experiment, the model yielded the following precise causal estimates:

**A. Policy Execution Confirmation: Ad Spend and Paid Clicks**
* **AdSpend**: $\beta_3 = -44.14$ ($p < 0.001$)
* **PaidClicks**: $\beta_3 = -44.11$ ($p < 0.001$)
* **Conclusion:** The experiment was strictly executed. The daily average ad spend in the treatment group significantly dropped by approximately $44, with a corresponding decrease of about 44 paid clicks.

**B. Substitution Effect Test: Did Organic Traffic Make Up for the Loss?**
* **OrganicClicks**: $\beta_3 = +1.97$ ($p = 0.827$)
* **Conclusion:** The increase in organic clicks is statistically insignificant. This indicates that users did not shift en masse to clicking organic links simply because the ads disappeared. **The substitution effect is extremely weak.**

**C. True Impact on Overall Traffic and Sales**
* **TotalClicks**: $\beta_3 = -42.14$ ($p < 0.001$). Total traffic dropped significantly, and the volume of lost traffic is roughly equivalent to the decrease in paid clicks.
* **TotalSales**: $\beta_3 = -17.54$ ($p = 0.001$). Against a baseline daily average of ~$2,806, pausing the ads caused the treatment group's daily total sales to experience a pure causal decline of **$17.54**.

---

### 4. Robustness Checks: Validating the Causal Inference
To guarantee that the $17.54 decline in daily sales is an absolute causal effect rather than a statistical artifact, two rigorous econometric validation tests were performed:

**A. Parallel Trends Assumption (Event Study / Dynamic DID)**

By restructuring the timeline into relative weeks (anchored at $T=-1$), the dynamic DID model demonstrated that prior to the intervention ($T < 0$), all 95% confidence intervals of the estimated coefficients perfectly crossed the zero axis, confirming statistically identical sales trajectories before the experiment. Immediately following the policy implementation ($T \ge 0$), the trend line experienced a precipitous, sustained drop below the zero axis. This perfectly validates the parallel trends assumption and proves the negative shock was immediate and lasting.

**B. Spatial Placebo Test (Permutation Test)**

To rule out random market fluctuations and omitted variables, a Monte Carlo simulation was executed with 200 iterations. By randomly assigning "fake treatment" statuses and re-running the TWFE model, the resulting 200 "fake causal effects" formed a perfect normal distribution centered at zero. The actual extreme effect (-$17.54) fell far outside the left tail of this random distribution ($P-value \approx 0.000$). This irrefutably proves that the observed sales loss is not a coincidental outcome.

---

### 5. Business Insights & Strategic Recommendations

Synthesizing the multi-validated data above, we can definitively assess the business value of these search ads:

1. **Do the ads have "Incremental Value"? — Yes.**
   The data completely debunks the internal assumption that "organic traffic will completely substitute paid traffic." These ads did drive substantial additional traffic and true sales for eBay, rather than serving as meaningless redundant exposures.
2. **Are the ads "Profitable"? — Severely unprofitable.**
   Calculating the true Return on Ad Spend (ROAS):
   * Saved daily ad cost: **$44.14**
   * Lost daily total sales: **$17.54**
   * **True ROAS** = 17.54 / 44.14 **$\approx$ 0.40**

**[Final Strategic Recommendation]**
Regarding the specific search ads covered in this experiment (likely branded keyword ads lacking new-user acquisition power or retargeting ads), while they do generate some true incremental volume, their **customer acquisition cost is exorbitantly high** (generating only $0.40 in revenue for every $1 spent). 
**It is strongly recommended that eBay permanently pause these specific search ads** or implement a drastically aggressive bid reduction. The freed-up budget pool ($44 per day per DMA) should be fully reallocated to other internal, high-yield marketing channels with a proven ROAS > 1 to maximize global profitability.
