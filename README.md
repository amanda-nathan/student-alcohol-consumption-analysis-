# Student Alcohol Consumption Analysis

This is an exploratory and psychometric analysis of student survey data.  
The goal is to test whether reliable composite scales can be built from survey responses, focusing on alcohol use and related behaviors, using data from the [UCI Student Performance Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00320/student.zip).

## Dataset

* **Source:** UCI Machine Learning Repository – Student Performance Dataset
* **File Used:** `student-mat.csv`
* **Description:** Demographic, social, and academic attributes for 395 secondary school students in Portugal.

## Analysis & Methodology

Rather than relying on single items, this project builds small composite indices and tests their internal reliability:

* Spearman Correlation  
* Spearman–Brown Prophecy Formula (two-item reliability)  
* Ordinal Cronbach’s Alpha (multi-item consistency)  
* Bootstrapping for confidence intervals  

## Findings

1. **Alcohol involvement** (weekday + weekend drinking) formed a reliable 2-item scale (ρ_SB = 0.780, 95% CI ≈ 0.73–0.82).  
2. **Socializing risk** (adding “goout”) reduced reliability (ordinal α = 0.693). Dropping `goout` restored scale strength.  
3. **Other composites** like *social support* (α = 0.060) and *academic engagement* (ρ_SB = 0.27) showed very poor reliability.  
   → These failures highlight why validated instruments are essential.  
4. Male students showed slightly higher mean scores on alcohol and socializing composites than female students.  

## Files in this Repository

* [`student-alcohol-consumption.ipynb`](student-alcohol-consumption.ipynb): Full analysis notebook  
* `scale_summary.csv`: Reliability statistics for tested scales  
* `scale_scores.csv`: Composite scores for each student
