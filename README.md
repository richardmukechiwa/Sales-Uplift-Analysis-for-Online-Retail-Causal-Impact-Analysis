# Sales-Uplift-Analysis-for-Online-Retail-Causal-Impact-Analysis

##  Causal Impact Analysis on Revenue, Quantity, and Unit Price

This project showcases a causal impact analysis performed on a dataset with features such as `revenue`, `quantity`, and `unit_price`. The goal was to assess the impact of an intervention on these variables.

## Project Overview

- used the `CausalImpact` package to estimate the effect of an intervention on `revenue`.

### Dataset

-   used a time series dataset where the intervention was introduced during a known period.
-   
  **Link :** https://github.com/andresvourakis/synthetic-e-commerce-data-with-marketing-campaign

- **Revenue**: Total revenue generated.
- **Quantity**: Number of units sold.
- **Unit Price**: Price per unit sold.

### Results Summary
The results of the analysis suggest a **statistically significant** positive impact of the intervention on revenue. Here is a brief summary:

| Metric                       | Average  | Cumulative |
|-------------------------------|----------|------------|
| **Actual (Post-Intervention)** | 747.95   | 37397.29   |
| **Predicted (s.d.)**           | 675.05 (11.06) | 33752.63 (552.88) |
| **Absolute Effect (s.d.)**     | 72.89 (11.06) | 3644.66 (552.88)  |
| **Relative Effect (s.d.)**     | +10.8% (1.64%) | +10.8% (1.64%) |
| **Posterior Probability**      | 100%    |            |

### Interpretation
- The intervention caused an **increase** in revenue by **72.89 units** on average, representing a **10.8%** relative increase.
- This effect is statistically significant, with a posterior probability of 100%, indicating the effect was unlikely to occur by chance.

### Code Snippet
Here’s a brief code snippet for the analysis:

```python
from causalimpact import CausalImpact

# Pre and post-intervention periods
pre_period = ['2021-01-01', '2021-07-19']
post_period = ['2021-07-20', '2021-09-07']

# Causal Impact analysis
impact = CausalImpact(df[['revenue', 'quantity', 'unit_price']], pre_period, post_period)
print(impact.summary())

```

### Visualization

- visualized the results of the causal impact analysis to better understand the intervention effect:
  
##### Predicted and actual values
  
![Predicted and y values](https://github.com/richardmukechiwa/Sales-Uplift-Analysis-for-Online-Retail-Causal-Impact-Analysis/blob/main/cuasalimpact1.png)

##### Point Effects

![Point Effects](https://github.com/richardmukechiwa/Sales-Uplift-Analysis-for-Online-Retail-Causal-Impact-Analysis/blob/main/causalimpact2.png)

##### Cumulative Effect

![Cumulative Effect](https://github.com/richardmukechiwa/Sales-Uplift-Analysis-for-Online-Retail-Causal-Impact-Analysis/blob/main/causalimpact3.png)






