# STATISTICS-2 — Extra Activity 5 (Central Limit Theorem)

## Activity title
**ACTIVITY-5: Demonstration of the Central Limit Theorem (CLT)** using the *Height* data from the **Weight-Height** dataset.

---

## Overview / Objective
Is activity ka objective **Central Limit Theorem (CLT)** ko empirically demonstrate karna hai using Height data.

We consider two cases:

### Case I — Sampling distribution of the sample mean
For various sample sizes:

\[
n \in \{5, 10, 30, 50, 100\}
\]

We repeatedly draw **100 samples** (with replacement), compute their **sample means**, and compare the empirical distribution to the theoretical normal distribution:

\[
\bar{X} \approx N\left(\mu, \frac{\sigma^2}{n}\right)
\]

We examine how **center**, **spread**, and **shape** change with increasing \(n\).

### Case II — Sampling distribution of the standardized sum
For the same \(n\) values, we compute the sum:

\[
Y = \sum_{i=1}^{n} X_i
\]

Then standardize it as:

\[
Z = \frac{Y - n\mu}{\sigma\sqrt{n}}
\]

We compare the empirical distribution of \(Z\) to:

\[
N(0, 1)
\]

to observe CLT convergence for totals.

---

## Files in this folder
- `Activity_5_(Colab).ipynb` — main Python/Colab notebook (simulation + plots).
- `ACTIVITY-5(1).xlsx` — Excel dataset (must contain column `Height`).
- `ACTIVITY-5.2.docx` — activity instructions / write-up reference.
- `README.md` — this documentation + summarized results.

---

## Requirements
Notebook uses:
- Python 3
- numpy
- pandas
- matplotlib
- scipy (`scipy.stats.norm`)
- openpyxl (Excel reading)

Install (if running locally):
```bash
pip install numpy pandas matplotlib scipy openpyxl
```

---

## How to run (Google Colab recommended)
1. Open `Activity_5_(Colab).ipynb` in Google Colab.
2. Run drive mount:
   ```python
   from google.colab import drive
   drive.mount('/content/gdrive')
   ```
3. Set the Excel file path (currently blank in notebook):
   ```python
   df = pd.read_excel('')
   ```
   Example:
   ```python
   df = pd.read_excel('/content/gdrive/MyDrive/ACTIVITY-5(1).xlsx')
   ```
4. Ensure the dataset column name matches:
   ```python
   heights = df['Height'].values
   ```
5. Run the remaining cells to generate tables + histograms.

---

## Notebook summary (Method)
### Population parameters (treat dataset as population)
- \(\mu =\) population mean of heights
- \(\sigma =\) population standard deviation (using `ddof=0`)

### Experiment settings
- `n_list = [5, 10, 30, 50, 100]`
- `R = 100` repeated samples per \(n\)

For each \(n\):
- Sample with replacement \(R\) times
- Save `sample_means` and `sample_sums`
- Compare:
  - Empirical mean of sample means
  - Empirical SD of sample means
  - Theoretical standard error \( \sigma/\sqrt{n} \)
- Plot:
  - Histogram of sample means + normal overlay \(N(\mu, \sigma/\sqrt{n})\)
  - Histogram of standardized sums \(Z\) + standard normal overlay \(N(0,1)\)

---

## Results

### Population statistics (from notebook output)
- **Population mean (µ)** ≈ **66.36756**
- **Population sigma (σ)** ≈ **3.847336**

---

## Case I — Sampling Distribution of the Sample Mean

We computed **100 sample means** for each \(n\) and compared their distribution to:

\[
N\left(\mu, \frac{\sigma^2}{n}\right)
\]

### Summary table
| Sample Size (n) | Mean of Sample Means | SD of Sample Means | Theoretical SE (σ/√n) |
|---:|---:|---:|---:|
| 5   | 66.4491 | 1.840964 | 1.720581 |
| 10  | 66.6048 | 1.210076 | 1.216634 |
| 30  | 66.2649 | 0.654985 | 0.702424 |
| 50  | 66.4026 | 0.563667 | 0.544095 |
| 100 | 66.3805 | 0.403552 | 0.384734 |

### Interpretation by n

#### For n = 5
- **Center:** mean of sample means ≈ 66.4491 (close to µ = 66.3676)
- **Spread:** SD ≈ 1.8410, theoretical SE ≈ 1.7206
- **Shape:** approaching bell curve; larger \(n\) yields smoother, narrower distribution

**Interpretation:** As \(n\) increases, sampling distribution becomes more normal and concentrated around µ; spread follows \(σ/\sqrt{n}\).

#### For n = 10
- **Center:** ≈ 66.6048 (close to µ = 66.3676)
- **Spread:** SD ≈ 1.2101, theoretical SE ≈ 1.2166
- **Shape:** more bell-shaped, narrower

**Interpretation:** CLT behavior improves; spread matches theoretical SE closely.

#### For n = 30
- **Center:** ≈ 66.2649 (close to µ = 66.3676)
- **Spread:** SD ≈ 0.6550, theoretical SE ≈ 0.7024
- **Shape:** noticeably more normal

**Interpretation:** By \(n \ge 30\), CLT approximation becomes strong.

#### For n = 50
- **Center:** ≈ 66.4026 (close to µ = 66.3676)
- **Spread:** SD ≈ 0.5637, theoretical SE ≈ 0.5441
- **Shape:** smooth and narrow

**Interpretation:** Mean concentrates around µ and SE aligns with theory.

#### For n = 100
- **Center:** ≈ 66.3805 (close to µ = 66.3676)
- **Spread:** SD ≈ 0.4036, theoretical SE ≈ 0.3847
- **Shape:** closest to normal, narrowest

**Interpretation:** Strongest CLT agreement for mean distribution.

---

## Case II — Standardized Sums (Z)

For each \(n\), we computed sums \(Y\) and standardized:

\[
Z = \frac{Y - n\mu}{\sigma\sqrt{n}}
\]

According to CLT, \(Z \approx N(0,1)\).

### Summary table
| n | Mean(Z) | SD(Z) |
|---:|---:|---:|
| 5   | 0.0474  | 1.0700 |
| 10  | 0.1950  | 0.9946 |
| 30  | -0.1462 | 0.9325 |
| 50  | 0.0644  | 1.0360 |
| 100 | 0.0336  | 1.0489 |

### Interpretation by n

#### For n = 5
- **Center:** Mean(Z) ≈ 0.0474 (expected 0)
- **Spread:** SD(Z) ≈ 1.0700 (expected 1)
- **Shape:** close to bell curve; improves with larger \(n\)

**Interpretation:** Small deviations at low \(n\); convergence improves as \(n\) increases.

#### For n = 10
- **Center:** ≈ 0.1950
- **Spread:** ≈ 0.9946
- **Shape:** close to bell curve; improving

**Interpretation:** Approaching standard normal as predicted.

#### For n = 30
- **Center:** ≈ -0.1462
- **Spread:** ≈ 0.9325
- **Shape:** close to normal

**Interpretation:** By \(n \ge 30\), CLT convergence becomes clearer.

#### For n = 50
- **Center:** ≈ 0.0644
- **Spread:** ≈ 1.0360
- **Shape:** close to normal

**Interpretation:** Standardized sums align closely with \(N(0,1)\).

#### For n = 100
- **Center:** ≈ 0.0336
- **Spread:** ≈ 1.0489
- **Shape:** very close to normal

**Interpretation:** Strong CLT agreement for totals at large \(n\).

---

## Conclusion
Across both cases, results validate the CLT:

- The sampling distribution of the mean follows:

\[
\bar{X} \sim N\left(\mu, \frac{\sigma^2}{n}\right)
\]

- The standardized sum follows:

\[
Z \sim N(0,1)
\]

As \(n\) increases, the match improves in:
- **Center** (mean closer to theoretical expectation),
- **Spread** (SD closer to theoretical SE / 1),
- **Shape** (more bell-shaped histograms).

---

## Notes / Common issues
- `pd.read_excel('')` me path blank mat chhodo—correct path do.
- Agar column `Height` exact match nahi kar raha, column name adjust karo.
- Colab Drive path usually: `/content/gdrive/MyDrive/...`
