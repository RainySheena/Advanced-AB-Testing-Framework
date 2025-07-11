# Project 3: A Framework for Advanced A/B Testing & Causal Inference

---

### 1. Project Overview

This project details the development and implementation of a sophisticated framework for A/B testing and causal inference during my internship at Apple. The goal was to elevate the company's experimentation capabilities beyond standard t-tests to ensure that results were statistically robust, sensitive, and trustworthy.

I designed and executed end-to-end testing processes, incorporating advanced techniques to increase statistical power (CUPED), control for observational bias (PSM, DiD), and ensure statistical validity in complex scenarios (Clustered Standard Errors).

---

### 2. Business Problem & Goal

* **Problem**: Standard A/B tests at scale often suffer from two key issues: 1) **Low Sensitivity**, requiring long run times or massive sample sizes to detect meaningful effects, and 2) **Hidden Biases**, where naive analysis can lead to incorrect conclusions about an intervention's true impact. A specific and critical challenge was the common discrepancy between the unit of randomization and the unit of analysis, which violates the i.i.d. (independent and identically distributed) assumption of standard statistical tests.

* **Goal**: The objective was to build and implement a comprehensive experimental framework that would:
    1.  Increase the statistical power and sensitivity of our tests, thereby reducing the Minimum Detectable Effect (MDE) and experiment duration.
    2.  Enable accurate measurement of treatment effects in scenarios where true randomization was not feasible.
    3.  Guarantee the statistical integrity of all experimental results by formally addressing complex data structures.

---

### 3. My Methodologies & Process

To achieve these goals, I implemented a multi-layered approach to experimentation:

1.  **End-to-End Experimental Design**: I was responsible for the full lifecycle of key experiments. This included stakeholder consultation for hypothesis formulation, metric selection and decomposition, and conducting power analysis to determine appropriate sample sizes and experiment durations.

2.  **Variance Reduction with CUPED**: To increase test sensitivity, I implemented the CUPED (Controlled-Experiment using Pre-Experiment Data) technique. By leveraging pre-experiment data as a covariate to control for pre-existing user variance, this method significantly reduced the variance of our target metrics. This allowed us to detect smaller effects (lower MDE) with the same sample size, leading to faster and more efficient testing.

3.  **Quasi-Experimental Analysis for Causal Inference**: For situations where clean A/B tests weren't feasible (e.g., a policy rollout affecting a whole region), I executed analyses using advanced causal inference methods. This included using **Difference-in-Differences (DiD)** to compare treatment and control group trends over time, and **Propensity Score Matching (PSM)** to create a statistically comparable control group from observational data, ensuring a more accurate measurement of treatment effects.

4.  **Ensuring Statistical Validity with Clustered Standard Errors**: This was a critical innovation to solve the unit-of-analysis problem. When the unit of randomization (e.g., store) was different from the unit of analysis (e.g., store-day), standard error calculations would be artificially underestimated, leading to a higher risk of false positives. I proposed and implemented **Clustered Standard Errors**, which correct for this intra-cluster correlation by grouping observations at the randomization level. This ensured the p-values and confidence intervals were accurate and that business decisions were based on statistically robust findings.

---

### 4. Tech Stack

* **Programming Languages & Tools**: `Python`, `R`, `SQL`, `Stata`

---

### 5. My Contribution

* **Methodological Leadership**: I moved the team's testing capabilities beyond standard practices by researching, proposing, and implementing advanced statistical techniques like CUPED and Clustered Standard Errors.
* **Rigorous Execution**: I independently conducted end-to-end analyses for critical business experiments, ensuring a high degree of statistical rigor and providing trustworthy results that leadership could rely on.
* **Critical Problem Solving**: I identified and solved a crucial flaw in the existing analysis pipeline related to the unit-of-analysis discrepancy, an innovation that significantly improved the reliability of all subsequent experimental results on the team.

---

### 6. Results & Impact

* **Key Result**: The implementation of this advanced framework led to a significant increase in the statistical power and trustworthiness of our A/B tests. For example, the use of CUPED reduced the MDE on key sales metrics by an average of 15-20%, allowing us to run experiments significantly faster.
* **Business Impact**: This framework provided the business with more reliable and sensitive experimental results, leading to better-informed and more confident product and marketing decisions. It established a new standard of statistical rigor for the team and created a formal playbook for tackling complex experimental designs in the future.
