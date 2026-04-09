# ACTIVITY - 3: Corporate Bond Ratings Dataset Analysis

## Dataset Overview
The dataset used for this analysis consists of corporate bond ratings and includes key numerical variables such as **CurrentRatio**, **QuickRatio**, and **CashRatio**. The values are **synthetic and scaled (normalized)**, which is why many values (and the means) are close to zero.

**Spreadsheet Link:** https://docs.google.com/spreadsheets/d/1h6O9D3sCPh5a2u3ihRe8GFwbYgQQfwVeol5003C-R_A/edit?usp=sharing

---

## Scatterplots
In this analysis, we examine the relationships between three numerical variables: **CurrentRatio**, **QuickRatio**, and **CashRatio**.

### Scatter Plot 1: CurrentRatio vs QuickRatio
![QuickRatio vs. CurrentRatio](./QuickRatio%20vs.%20CurrentRatio.png)

**Interpretation:** There is a **moderate negative relationship** between CurrentRatio and QuickRatio. This suggests that companies with higher current ratios tend to have lower quick ratios, and vice versa.

### Scatter Plot 2: QuickRatio vs CashRatio
![CashRatio vs. QuickRatio](./CashRatio%20vs.%20QuickRatio.png)

**Interpretation:** There is a **strong positive relationship** between QuickRatio and CashRatio. This implies that companies that are liquid in terms of quick assets also maintain higher cash reserves.

### Scatter Plot 3: CurrentRatio vs CashRatio
![CashRatio vs. CurrentRatio](./CashRatio%20vs.%20CurrentRatio.png)

**Interpretation:** This is a **very weak positive relationship (almost negligible)**. It means that CurrentRatio and CashRatio are nearly independent and do not vary together significantly.

---

## Covariance Calculation
The covariance values between the selected variables are:

- **Cov(CurrentRatio, QuickRatio) = -0.6175027303**
- **Cov(QuickRatio, CashRatio) = 1.404242774**
- **Cov(CurrentRatio, CashRatio) = 0.01834544702**

**Interpretation:**
- A **negative covariance** between CurrentRatio and QuickRatio indicates an **inverse relationship**, where an increase in one variable is associated with a slight decrease in the other.
- A **positive covariance** between QuickRatio and CashRatio suggests that both variables **move together**, increasing or decreasing in tandem.
- The **near-zero covariance** between CurrentRatio and CashRatio indicates **almost no linear relationship** between these two variables.

---

## Mean and Standard Deviation
The mean and standard deviation for the chosen variables are:

### CurrentRatio
- **Mean = -0.002053209172**
- **Standard Deviation = 0.9613188819**

**Interpretation:** The CurrentRatio is centered around zero (normalized), and its variability is moderate. This indicates that most values are not far from the average.

### QuickRatio
- **Mean = -0.01279293548**
- **Standard Deviation = 1.445264062**

**Interpretation:** QuickRatio has the **highest standard deviation**, meaning it shows the most variation among the three ratios. This indicates significant differences in quick-asset liquidity across companies.

### CashRatio
- **Mean = -0.02123610075**
- **Standard Deviation = 1.226798696**

**Interpretation:** CashRatio also varies considerably, but less than QuickRatio. It represents moderate variation in cash holdings among companies.

---

## Chebyshev’s Inequality (k = 2)
Chebyshev’s inequality provides a lower bound on the probability that a random variable lies within **k standard deviations** of the mean.

It states:

- \(P(|X-\mu| \ge k\sigma) \le \frac{1}{k^2}\)
- Therefore, \(P(|X-\mu| < k\sigma) \ge 1 - \frac{1}{k^2}\)

For this analysis we use **k = 2**, so:

- \(P(|X-\mu| < 2\sigma) \ge 1 - \frac{1}{4} = 0.75\)

This means **at least 75%** of the values lie within **2 standard deviations** of the mean.

### CurrentRatio
- Mean (\(\mu\)) = **-0.0021**
- Standard Deviation (\(\sigma\)) = **0.9313**

Using **k = 2**:
- **Upper bound = \(\mu + 2\sigma\) = 1.9205**
- **Lower bound = \(\mu - 2\sigma\) = -1.9247**

**Interpretation:** At least 75% of the CurrentRatio values lie between **-1.9247** and **1.9205**.

### QuickRatio
- Mean (\(\mu\)) = **-0.0128**
- Standard Deviation (\(\sigma\)) = **1.4453**

Using **k = 2**:
- **Upper bound = \(\mu + 2\sigma\) = 2.8778**
- **Lower bound = \(\mu - 2\sigma\) = -2.9034**

**Interpretation:** At least 75% of the QuickRatio values lie between **-2.9034** and **2.8778**.

### CashRatio
- Mean (\(\mu\)) = **-0.0212**
- Standard Deviation (\(\sigma\)) = **1.2268**

Using **k = 2**:
- **Upper bound = \(\mu + 2\sigma\) = 2.4324**
- **Lower bound = \(\mu - 2\sigma\) = -2.4748**

**Interpretation:** At least 75% of the CashRatio values lie between **-2.4748** and **2.4324**.