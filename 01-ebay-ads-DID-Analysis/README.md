#  In-Depth Evaluation of eBay Search Ads ROI Based on DiD Analysis
![EBay_logo](https://github.com/user-attachments/assets/ce4b9840-eb3a-4eb9-b067-6d945f7def1d)
    
## 1.Project Overview
### 1.1 Business Context & Core Questions
In Search Engine Marketing (SEM), organizations frequently face a classic attribution dilemma: **Do paid search ads drive truly incremental sales, or do they merely cannibalize organic search traffic that would have occurred anyway (the substitution effect)?**
To precisely evaluate the true Return on Investment (ROI) of search ads, eBay conducted an A/B experiment across selected Designated Market Areas (DMAs) in the US. Search advertising was completely paused in the treatment DMAs, while the control DMAs maintained their regular ad campaigns. This project leverages advanced causal inference models to isolate natural market fluctuations and quantify the true business impact of pausing these ads.

### 1.2 Experiment Design
**Experimental Design:** The U.S. market was strategically partitioned into 210 mutually exclusive Designated Market Areas (DMAs), serving as independent experimental units to mitigate spillover effects.
**Treatment vs. Control Assignment:**
* **Treatment Group (Intervention):** A randomly selected subset of DMAs where all paid search advertising for non-branded, "generic" keywords (e.g., "running shoes") was completely halted for a multi-month observation window.
* **Control Group (Business-as-Usual):** The remaining DMAs where search advertising spend and bidding strategies were maintained at their historical baselines.

**Analytical Objective:** To rigorously isolate and quantify the true "causal lift" (incremental value) of generic search ads on total sales. This geographic split effectively controls for unobserved regional heterogeneity, seasonal trends, and macroeconomic shocks.

## 2. Data Overview & Preprocessing
The dataset contains 18,200 rows, each representing a unique Designated Market Area in one day during the A/B test period. Key variables include:

| Variable | Description |
| :--- | :--- |
| **DMA** | The name of the Designated Market Area (DMA), a geographic region used for advertising targeting and analysis. |
| **Code** | A unique numeric identifier assigned to each DMA (e.g., 501 for New York). |
| **Date** | The calendar date of the observation, covering the duration of the experiment (Q2 2024). |
| **Population** | The estimated population of the DMA. This variable helps control for market size in the analysis. |
| **MedianHHIncome** | Median household income in the DMA. Captures economic differences that may affect consumer spending behavior. |
| **Broadband** | The percentage of households in the DMA with access to high-speed internet. Serves as a proxy for digital infrastructure and online shopping accessibility. |
| **Urbanization** | A score representing the degree of urbanization in the DMA (e.g., higher values indicate more urban areas). Affects search behavior, device usage, and shopping patterns. |
| **eCommIndex** | An internally developed index indicating the overall propensity of residents in the DMA to engage in e-commerce. Higher values reflect more digitally engaged markets. |
| **MedianAge** | The median age of residents in the DMA. Useful for controlling demographic differences in online shopping preferences. |
| **CollegeDeg** | The percentage of adults in the DMA holding at least a college degree. May correlate with digital literacy or brand awareness. |
| **CostIndex** | A composite cost-of-living index for the DMA, scaled so that 100 represents the national average. Higher values indicate more expensive regions. |
| **Treatment** | A binary indicator (0 or 1) denoting whether the DMA was assigned to the treatment group (ads turned off during Post period). |
| **Post** | A binary indicator (0 or 1) for the experiment phase. 0 denotes the Pre-treatment period (all DMAs receive ads), and 1 denotes the Post-treatment period (when treatment DMAs stop receiving ads). |
| **DayIndex** | A sequential day counter, starting from 0 on April 1, 2024. Useful for time series plotting and trend analysis. |
| **AdSpend** | The dollar amount eBay spent on paid search advertising in the DMA on that day. For treatment DMAs during the Post period, this value is 0. |
| **PaidClicks** | The number of clicks on eBay's paid search ads from users in the DMA on that day. |
| **OrganicClicks** | The number of clicks from organic (unpaid) search results, capturing traffic that reached eBay without ad spend. |
| **TotalClicks** | The total number of search-driven clicks, computed as the sum of PaidClicks and OrganicClicks. |
| **SalesAds** | The dollar value of sales attributed to users who arrived via paid search ads. This helps in estimating the direct return from ad-driven traffic. |
| **TotalSales** | The total dollar value of all sales in the DMA on that day, from both organic and paid traffic, as well as non-search sources. |

## 3. Analytical Framework & Methodology
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
