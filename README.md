# Week_3_Descriptive_Statistics
Working with Housing Price  &amp; Titanic cleaned Dataset
# Statistical Thinking & Probability Foundations

Welcome to my repository for **Week 3** of the Data Science Internship program! This week, the focus shifted from foundational data cleaning and exploratory analysis to rigorous mathematical validation using descriptive statistics, probability theory and formal hypothesis testing. 

This repository contains the end-to-end analytical pipeline for two distinct observational datasets: **The Titanic Passenger Manifest** and a **Housing Prices Dataset**.

---

## 🛠️ Technologies & Tools Used
* **Language:** Python 3.10
* **Libraries:** `pandas`, `numpy`, `scipy.stats`, `seaborn`, `matplotlib`
* **Environment:** Jupyter Notebook

---

## 🏠 Project 1: Housing Prices Dataset Analysis

### 📋 Project Overview
This analysis establishes the baseline metrics for a real estate ecosystem, identifies high-density purchasing tiers using continuous probability distributions, and statistically validates geographic value premiums.

### 🔍 Key Findings & Metrics
* **Market Center & Spread:** The average house price is **4,766,729.25**, with a massive standard deviation of **1,870,439.62**. This high variance mathematically confirms a strong right-hand skewness driven by premium luxury transactions pulling the market mean upward.
* **The Market "Sweet Spot":** While exactly **11.74%** of the dataset consists of luxury outlier properties exceeding 7M, continuous normal distribution modeling establishes that there is a **37.72% probability** of a random property falling within the **3M to 5M** tier—marking this the high-volume core of the market.
* **Hypothesis Testing (Location Premium):** Executed a formal **Two-Sample Welch's t-Test** on property unit value (`price_per_sqft`) across location tiers (`prefarea`).
  * *Results:* $T\text{-Statistic} = 2.5183$ | $P\text{-Value} = 0.0125$
  * *Conclusion:* **Reject the Null Hypothesis.** Because $p < 0.05$, the location premium is statistically verified. Geography applies a genuine upward shift to property value.
* **Correlation vs. Causation Insight:** Physical size (`area`, $r = 0.54$) and plumbing density (`bathrooms`, $r = 0.52$) are strongly correlated with price. However, these are proxy metrics. The overall structural scale and luxury tier of the house is the true causal driver of market value, not individual plumbing fixtures in isolation.

---

## 🚢 Project 2: Titanic Dataset Analysis

### 📋 Project Overview
Building on top of Phase 1 data cleaning and categorical mapping, this phase applies statistical tests to prove demographic survival biases and map the deep socioeconomic dependencies governing the historical maritime disaster.

### 🔍 Key Findings & Metrics
* **Economic Polarization:** The financial profile reveals a ticket `Fare` mean of **32.20**, but an extreme standard deviation of **49.69** ($\text{Variance} = 2,469.44$). Because $\text{Std Dev} > \text{Mean}$, it mathematically highlights a highly polarized manifest anchored by lower-class passengers but stretched by extreme luxury outliers.
* **Demographic Survival Bias:** Conditional probability mapping reveals a staggering systemic divide in survival outcomes across gender boundaries:
  * $P(\text{Survived} = 1 \mid \text{Female}) = \mathbf{74.20\%}$
  * $P(\text{Survived} = 1 \mid \text{Male}) = \mathbf{18.89\%}$
  * *Insight:* Being a female passenger made an individual **3.9 times more likely to survive**, validating the structural enforcement of maritime safety protocols.
* **Hypothesis Testing (Socioeconomic Status):** Executed a categorical **Chi-Square Test of Independence** between Ticket Class (`Pclass`) and Survival Status (`Survived`).
  * *Results:* $\chi^2\text{ Statistic} = 102.8890$ | $P\text{-Value} = 4.5493 \times 10^{-22}$
  * *Conclusion:* **Reject the Null Hypothesis.** Because $p \ll 0.05$, a passenger's ticket class tier and their ultimate survival outcome are deeply dependent variables.
* **Correlation vs. Causation Insight:** While higher fares and upper-class designations strongly correlate with survival, wealth did not directly cause survival. Instead, ticket class acted as a proxy for **physical deck proximity to lifeboats** and institutional evacuation priority. First-class cabins sat on upper decks directly beneath the boats, granting immediate communication access and zero structural layout barriers.

---
