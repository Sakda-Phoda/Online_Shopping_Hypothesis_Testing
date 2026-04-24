# 🛒 Online Shopping A/B Testing: Statistical Analysis & Business Impact

---

## 📌 Project Overview
This project evaluates the effectiveness of three key e-commerce features: a **New Recommendation System**, a **Button Color Change**, and multiple **Marketing Campaigns**. By implementing a robust Statistical Hypothesis Testing pipeline, the goal is to distinguish genuine business improvements from random variance and accurately estimate their impact on sales and conversion rates.

---

## 📊 Summary of Key Findings
**1. Recommendation System Impact (Algorithm A/B Test)** 
- **Goal:** Determine if the new algorithm increases the number of items added to the cart.
- **Insight:** Because the data is not normally distributed, the **Brunner-Munzel test** was used instead of a standard T-test. 
- **Business Value:** Alongside the p-value, **Bootstrap Confidence Intervals** were applied to estimate the actual monetary impact (per person) the new algorithm brings to total sales.

**2. UI/UX Optimization (Button Color)** 
- **Goal:** Analyze whether changing the button color significantly impacts user conversion rates.
- **Insight**: Used a **Z-Test** to compare conversion rates and checked **Cohen's** h to make sure the difference was big enough to actually be useful for the business, not just a result of random luck.

**3. Marketing Campaign Effectiveness (A/B/n Testing)** 
- **Goal:** Compare the success rates across multiple promotional campaigns.
- **Insight:** Evaluated overall variance using a **Chi-Square Test** and **Cramer's V / Cohen's W** for effect size. 
- **Findings:** Compared campaigns side-by-side to find the clear winners, making sure the results are highly accurate and not due to chance.

---

## 🛠 Tech Stack & Methodology
* **Statistical Rigor & Power Analysis:** Implemented robust power analysis (`statsmodels`, `pingouin`) across all tests to prevent Type II errors and ensure sample sizes were large enough to detect meaningful effects.
* **Distribution-Aware Testing:** Automated normality checks (`pg.normality`) to intelligently route data to either parametric (T-Test) or non-parametric (Brunner-Munzel) statistical tests.
* **Effect Size Over P-Values:** Prioritized measuring the magnitude of changes (Cohen’s d, h, w, and Cramer’s V) to answer "How much does this matter?" rather than just "Is there a difference?".
* **Advanced Error Control:** Utilized `itertools.combinations` and `multipletests` for post-hoc analysis, strictly adjusting alpha thresholds to maintain integrity when running multiple comparisons.

---
## 💻 Tech Stack
* **Data Manipulation:** `Pandas`, `NumPy`
* **Statistical Testing:** `SciPy` (Brunner-Munzel, Bootstrap), `Statsmodels` (Z-test, Multiple Comparisons)
* **Advanced Analytics:** `Pingouin` (Power Analysis, Normality, Effect Size)
* **Data Visualization:** `Matplotlib`, `Seaborn` (Visualized with `ggplot` style and `Set2` palette)
* **Workflow & Utilities:** `Kagglehub` (Data Sourcing), `Itertools` (Pairwise Combinations)

---

## 📚 Data Source
- **Dataset:** Online Shopping Hypothesis Testing
- **Source:** [Kaggle - sakdaphoda/online-shopping-hypothesis-testing](https://www.kaggle.com/datasets/sakdaphoda/online-shopping-hypothesis-testing)