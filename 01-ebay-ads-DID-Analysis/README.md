#  In-Depth Evaluation of eBay Search Ads ROI Based on DiD Analysis
![EBay_logo](https://github.com/user-attachments/assets/ce4b9840-eb3a-4eb9-b067-6d945f7def1d)<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg
   id="eBay_logo"
   data-name="eBay logo"
   version="1.1"
   viewBox="0 0 1000 400.75098"
   sodipodi:docname="eBay.svg"
   width="1000"
   height="400.75098"
   inkscape:version="1.4 (86a8ad7, 2024-10-11)"
   xml:space="preserve"
   xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
   xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:svg="http://www.w3.org/2000/svg"><sodipodi:namedview
     id="namedview4"
     pagecolor="#ffffff"
     bordercolor="#000000"
     borderopacity="0.25"
     inkscape:showpageshadow="2"
     inkscape:pageopacity="0.0"
     inkscape:pagecheckerboard="0"
     inkscape:deskcolor="#d1d1d1"
     inkscape:zoom="0.5"
     inkscape:cx="546"
     inkscape:cy="199"
     inkscape:window-width="1366"
     inkscape:window-height="705"
     inkscape:window-x="-8"
     inkscape:window-y="-8"
     inkscape:window-maximized="1"
     inkscape:current-layer="eBay_logo" /><defs
     id="defs1"><style
       id="style1">
      .cls-1 {
        fill: #0968f6;
      }

      .cls-1, .cls-2, .cls-3, .cls-4 {
        stroke-width: 0px;
      }

      .cls-2 {
        fill: #92c821;
      }

      .cls-3 {
        fill: #f02d2d;
      }

      .cls-4 {
        fill: #ffbd14;
      }
    </style></defs><g
     id="g4"><path
       class="cls-4"
       d="m 633.07803,212.53323 c -45.43873,1.48929 -73.6715,9.689 -73.6715,39.61897 0,19.37591 15.44713,40.38162 54.66334,40.38162 52.57698,0 80.64259,-28.65902 80.64259,-75.66331 l 0.003,-5.16994 c -18.43302,0 -41.16414,0.16089 -61.63704,0.83266 z m 111.75103,62.10248 c 0,14.58313 0.42155,28.9782 1.69406,41.94092 h -46.61408 c -1.24325,-10.67368 -1.6972,-21.27945 -1.6972,-31.56656 -25.20195,30.97941 -55.17735,39.88537 -96.76149,39.88537 -61.67674,0 -94.70072,-32.59982 -94.70072,-70.30689 0,-54.61215 44.91583,-73.86739 122.89013,-75.65391 21.32332,-0.48686 45.27419,-0.55894 65.07531,-0.55894 l -0.003,-5.33606 c 0,-36.56098 -23.44364,-51.59335 -64.06765,-51.59335 -30.15876,0 -52.38579,12.48057 -54.6764,34.0468 h -52.65168 c 5.57217,-53.77165 62.06643,-67.37115 111.74005,-67.37115 59.50837,0 109.77228,21.17288 109.77228,84.11481 z"
       id="path1"
       style="fill:#ffbc13;fill-opacity:1" /><path
       class="cls-3"
       d="m 199.63633,185.86602 c -1.94427,-46.87735 -35.77951,-64.41973 -71.94139,-64.41973 -38.99421,0 -70.12667,19.7327 -75.58026,64.41973 z M 51.034408,219.1909 c 2.704332,45.48365 34.069782,72.38437 77.197532,72.38437 29.88033,0 56.45979,-12.17498 65.35948,-38.66041 h 51.68424 c -10.05205,53.73979 -67.15384,71.98058 -116.303,71.98058 C 39.606424,324.89544 0,275.67889 0,209.30653 0,136.24203 40.965642,88.12194 129.78809,88.12194 c 70.69867,0 122.49992,36.99926 122.49992,117.75572 v 13.31324 z"
       id="path2"
       style="fill:#f12c2d;fill-opacity:1" /><path
       class="cls-1"
       d="m 380.83181,290.6235 c 46.57228,0 78.44078,-33.52181 78.44078,-84.10854 0,-50.58203 -31.8685,-84.10854 -78.44078,-84.10854 -46.31058,0 -78.44392,33.52651 -78.44392,84.10854 0,50.58673 32.13334,84.10854 78.44392,84.10854 z M 252.2854,0 h 50.10249 l -0.005,125.87707 c 24.55682,-29.25975 58.38892,-37.75513 91.68976,-37.75513 55.83503,0 117.85132,37.6773 117.85132,119.02875 0,68.12232 -49.32155,117.74475 -118.78114,117.74475 -36.35726,0 -70.58062,-13.04265 -91.68663,-38.88294 0,10.32107 -0.57618,20.72364 -1.70503,30.56413 h -49.17162 c 0.85513,-15.90944 1.70555,-35.7184 1.70555,-51.74693 z"
       id="path3"
       style="fill:#0968f6;fill-opacity:1" /><path
       class="cls-2"
       d="M 1000,96.45747 845.05541,400.75099 H 788.94926 L 833.49578,316.25589 716.89033,96.45747 h 58.6266 l 85.80469,171.73057 85.56283,-171.73057 z"
       id="path4"
       style="fill:#93c822;fill-opacity:1" /></g></svg>


## 1.Project Overview
### 1.1 Business Context & Core Questions
In Search Engine Marketing (SEM), organizations frequently face a classic attribution dilemma: **Do paid search ads drive truly incremental sales, or do they merely cannibalize organic search traffic that would have occurred anyway (the substitution effect)?**
To precisely evaluate the true Return on Investment (ROI) of search ads, eBay conducted an A/B experiment across selected Designated Market Areas (DMAs) in the US. Search advertising was completely paused in the treatment DMAs, while the control DMAs maintained their regular ad campaigns. This project leverages advanced causal inference models to isolate natural market fluctuations and quantify the true business impact of pausing these ads.

### 1.2 Geographic Randomized Controlled Trial (Geo-RCT)
**Experimental Design:** The U.S. market was strategically partitioned into 210 mutually exclusive Designated Market Areas (DMAs), serving as independent experimental units to mitigate spillover effects.
**Treatment vs. Control Assignment:**
* **Treatment Group (Intervention):** A randomly selected subset of DMAs where all paid search advertising for non-branded, "generic" keywords (e.g., "running shoes") was completely halted for a multi-month observation window.
* **Control Group (Business-as-Usual):** The remaining DMAs where search advertising spend and bidding strategies were maintained at their historical baselines.

**Analytical Objective:** To rigorously isolate and quantify the true "causal lift" (incremental value) of generic search ads on total sales. This geographic split effectively controls for unobserved regional heterogeneity, seasonal trends, and macroeconomic shocks.


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
