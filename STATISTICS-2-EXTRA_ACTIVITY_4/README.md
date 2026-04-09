Extra Activity 4 — Google Quarterly Profit (2009–2024)
Data / Topic
We study the quarterly profit of Google from 2009 to 2024.

Total number of years: 16
Total number of quarters (data points): 63
Note: The unit (e.g., USD millions/billions) and the data source should match what is used in ACTIVITY-4.xlsx.

Goal
Fit a best‑fit line (trend model) for profit over time (by quarter).
Compute the error (residual) for each quarter.
Check whether the error variable can be reasonably modeled by a Normal distribution.
Use the Normal model to estimate probabilities of observing certain error sizes.
Model Setup
Time variable
Let t represent the quarter index (for example: 1, 2, 3, …, 63).

Best‑fit line (trend model)
We model profit using a linear trend:

[ \hat{y}(t) = a + bt ]

Where:

( \hat{y}(t) ) = estimated profit in quarter (t)
(a) = intercept
(b) = slope (average change in profit per quarter)
In Excel / Google Sheets, you can compute:

b = SLOPE(profit_range, t_range)
a = INTERCEPT(profit_range, t_range)
Random Variable Definition
Define the random variable X as:

[ X = y - \hat{y} ]

Where:

(y) = actual profit
(\hat{y}) = estimated profit from the best‑fit line
Interpretation:

X > 0 → actual profit is higher than predicted
X < 0 → actual profit is lower than predicted
Claim
The error variable (X) can be modeled as a Normal distribution.

So we estimate profit using the best‑fit line, compute errors, and then determine probabilities of different error values.

Steps / Method
Use the profit dataset for 63 quarters (2009–2024).
Create the quarter index (t = 1,2,\dots,63).
Fit the best‑fit line ( \hat{y}(t) = a + bt ).
For each quarter:
compute the estimated profit ( \hat{y} )
compute the error ( X = y - \hat{y} )
Summarize the errors using a frequency table (grouped by error size).
Compare the observed error pattern with a Normal model.
Observed Error Frequencies (from data)
Total number of quarters = 63

Below is the observed relative frequency for each error value/bin (as computed from the dataset):

Relative frequency at 0 = 0
Relative frequency at 1000 = 0.09523809524
Relative frequency at 2000 = 0.1111111111
Relative frequency at 3000 = 0.09523809524
Relative frequency at 4000 = 0.1904761905
Relative frequency at 5000 = 0.2222222222
Relative frequency at 6000 = 0.1428571429
Relative frequency at 7000 = 0.06349206349
Relative frequency at 8000 = 0.01587301587
Relative frequency at 9000 = 0.03174603175
Relative frequency at 10,000 = 0.03174603175
Observation
The distribution of errors appears approximately:

symmetric
bell‑shaped
concentrated toward the middle, decreasing toward the extremes
This is a key characteristic of a Normal distribution, so it is reasonable to model the error variable using a Normal model.

Normal Model for Errors
Assume:

[ X \sim N(\mu,\sigma^2) ]

Where:

( \mu ) = mean of the errors
( \sigma ) = standard deviation of the errors
Important: In a perfect linear regression with an intercept, the residual mean is typically close to 0.
Use the exact ( \mu ) and ( \sigma ) computed in your spreadsheet.

Calculating probabilities in Google Sheets
We compute the cumulative probability:

[ F(a) = P(X \le a) ]

Using:

NORM.DIST(a, μ, σ, TRUE)

Computed Normal CDF values:

F(0) = 0
F(1000) = 0.3950589503
F(2000) = 0.4294901186
F(3000) = 0.4644665105
F(4000) = 0.4997198378
F(5000) = 0.5349753544
F(6000) = 0.5699582629
F(7000) = 0.6044001236
F(8000) = 0.6380450173
F(9000) = 0.6706552258
F(10,000) = 0.7020162221
Conclusion
The probabilities calculated from the Normal distribution are reasonably close to the observed pattern, indicating that the Normal model provides a good fit for the errors.

Although probabilities may not be exact (due to uncertainty in errors and possible outliers), the Normal model still provides valuable insights and can support reasonable predictions about future profits.

Thus, the Normal distribution serves as an effective tool for analyzing the error behavior and making probability-based interpretations of the model.

Files Included
ACTIVITY-4.docx — activity write‑up
ACTIVITY-4.xlsx — data + calculations
# Images

![Profit vs Quarters](./profit_vs_quarters.png)

![Probability Curve](./probability_curve.png)
