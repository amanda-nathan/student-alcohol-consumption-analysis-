# Student Alcohol Consumption Analysis

This is an exploratory and psychometric analysis of student survey data. The primary goal is to create and validate reliable scales for measuring student social behaviors, particularly those related to alcohol use, using data from the UCI Machine Learning Repository.

## Dataset

* **Source:** [UCI Machine Learning Repository: Student Performance Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00320/student.zip)
* **File Used:** The analysis uses the `student-mat.csv` file from within the downloaded zip archive. (The notebook sets up that download for you.)
* **Description:** The data includes demographic, social, and academic attributes for 395 secondary school students in Portugal.

## Analysis & Methodology

Instead of relying on single-item indicators, this project constructs multi-item composite scales and tests their statistical reliability.

The primary methods used include:
* Spearman Correlation
* Spearman-Brown Prophecy Formula (for two-item scale reliability)
* Ordinal Cronbach's Alpha (for multi-item scale internal consistency)
* Bootstrapping for confidence intervals

## Findings

1.  **A reliable `alcohol_involvement` scale was created** by combining weekday (`Dalc`) and weekend (`Walc`) alcohol use. This two-item scale demonstrated good reliability (ρ_SB = 0.780).
2.  A three-item "socializing risk" scale that included `goout` was tested and found to be **less reliable**. The analysis showed that the `goout` item weakened the scale's internal consistency.
3.  Other potential scales for "family functioning" and "academic engagement" were tested and **rejected due to very poor reliability scores**.
4.  Visualizations show that, in this sample, **male students reported higher average scores for alcohol involvement** and socializing risk than female students.

## Files in this Repository

* `student-alcohol-consumption.ipynb`: The main Jupyter Notebook containing the full analysis.
* `scale_summary.csv`: A summary table of the reliability statistics for the tested scales.
* `scale_scores.csv`: The calculated composite scores (`alcohol_involvement`, `socializing_risk`) for each student.