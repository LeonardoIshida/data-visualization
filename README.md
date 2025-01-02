<br />
<div align="center">
    <img src="https://www.opendatasoft.com/wp-content/uploads/2022/08/Blog-thumbnail.png" alt="Logo" width="400">
  </a>

  <h1 align="center">Data Visualization</h1>
  <br>
</div>

## Data Visualization Project: <a href="https://openml.org/search?type=data&id=42723&sort=runs&status=active"> University Dataset </a>

This repository contains the project deliverables for the Computational Visualization course.  This project focuses on exploring and analyzing a dataset of US universities, using visualization techniques to answer specific research questions.

### Project Overview

This project aims to apply the concepts and techniques learned in the Computational Visualization course to explore, analyze, and communicate insights from a dataset of US universities.  The project involves data profiling, preprocessing, creating static and interactive visualizations, and formulating insightful conclusions.

### Project Description - Phase 1

The project is structured around the following key components:

1. **Data Profiling:** The chosen dataset provides a comprehensive overview of US universities, including demographic and financial information about students, geographical data, and university characteristics. The dataset comprises 48 variables and 7063 observations, with a significant portion (30.8%) of missing cells.

2. **Data Preprocessing:**  Several preprocessing steps were performed to prepare the data for analysis and visualization:
    * **Missing Values:**
        * Grades (SAT, ACT): Imputed using the mean and adjusted based on university rankings.
        * Costs (academic year, program year): Imputed using the mean, but removed for visualizations to avoid distortion.  The imputation is retained for other analysis.
        * Acceptance Rate: Imputed using the mean, and adjusted based on external data (linked in the slides).
        * Financial Returns, Family Income: Imputed using the mean.
        * Faculty Salaries, Spending per Student, Tuition: Imputed using the median.
        * Age, Female Percentage: Imputed using the mean.
        * Spatial Data (zip code, latitude, longitude):  Not imputed due to potential inconsistencies. Left as missing.
    * **New Feature Creation:** A `classification` feature was created to categorize universities as "top," "average," or "bad" based on SAT and ACT scores to refine the analysis.
    * **Normalization:**  SAT and ACT scores were normalized using z-scores due to their different scales but similar meaning. For parallel coordinate plots, min-max scaling was used for scores and female percentage.
    * **Column Removal:** The `school_webpage` column was removed due to many missing values, and the `religious_affiliation` column was removed due to a high percentage (90%) of missing data.


3. **Research Questions:**  The project seeks to answer the following research questions:
    * **SAT and ACT:** How are SAT and ACT scores distributed? Is one test more difficult than the other?
    * **Return on Investment:**  Do students who attend more expensive universities have a higher financial return in the long term (10 years) or short term (6 years)?
    * **Income and Financial Aid:** Do students from lower-income families tend to seek universities that offer more financial aid?
    * **Female Participation:**  What is the percentage of female students in US universities? Is there a correlation between higher SAT/ACT scores and the proportion of female students?
    * **Demographics:** How are student demographics distributed across universities? Is there any correlation with location?

4. **Visualization and Analysis:** Various visualizations were created to explore and answer the research questions (examples provided in the slides):
    * Scatterplots (SAT/ACT correlation)
    * Density plots (financial return)
    * Heatmaps (correlation between cost and financial return)
    * Linear regression plots (impact of college cost on earnings)
    * 2D Density plots (family income vs. scholarship percentage)
    * Histograms (female student percentage)
    * Parallel Coordinates (comparing male and female student performance)
    * Bar charts (demographics by region)
    * Histograms (racial demographics)


5. **Insights:**  Key insights derived from the analysis and visualizations include:
    * Strong correlation between SAT and ACT scores.
    * Potential progression in career earnings after graduation.
    * Possible, but not strong, correlation between university cost and financial return.
    * Higher likelihood of students from lower-income families attending universities offering more financial aid.
    * Uneven distribution of student demographics, with notable concentrations of Hispanic students in Outlying Areas.
    * No significant performance difference between male and female students based on grades, despite varying female representation across universities.

6. **Further Exploration:** Future research questions include analyzing the relationship between future earnings, demographics, and gender; examining female student representation and graduation rates in more conservative states; and exploring differences in university characteristics based on financial aid and student demographics.

### Project Description - Phase 2

This phase of the project expands on the foundation laid in Phase 1, encompassing the following:

1. **Continued Analysis:**  This phase addresses the research questions posed in Phase 1 with a greater depth of analysis, incorporating new visualizations and insights where applicable.

2. **Interactive Visualizations:** Several interactive visualizations were developed using Vega-Altair to enhance data exploration and understanding:
    * **Correlation Heatmap:** An interactive heatmap allows users to filter universities based on demographic criteria and observe the resulting changes in correlation coefficients between variables such as race, gender, earnings, and admission scores.
    * **Parallel Coordinates Plot:** This interactive visualization allows for the exploration of relationships between demographics, earnings, and test scores using brushing and filtering, providing a dynamic way to analyze patterns and trends.
    * **Choropleth Map with Bar Chart:** Three interactive choropleth maps visualize female student percentage, graduation rate, and a derived "conservativeness" score by US state.  An associated bar chart acts as a brush, enabling interactive filtering and regional comparisons.
    * **UMAP and PCA Plots:**  Interactive UMAP and PCA plots were used to explore the relationship between university characteristics and financial aid, enabling clustering and analysis of factors influencing scholarship availability.  A separate UMAP plot visualized the relationship between part-time student percentage and other features.
    * **Scatter Plots with Linked Brushing:** Scatter plots were used to investigate the relationships between university classification (Carnegie classification), test scores (SAT/ACT), spending per student, and family income, utilizing interactive brushing and tooltips to highlight individual university data.
    * **Interactive Density Plots:**  Interactive density plots were created to investigate the relationship between family income, financial aid, graduation rate, part-time student status, and post-graduation earnings, allowing for exploration of socioeconomic factors and student outcomes.


3. **Key Insights and Findings:**

    * **Demographics and Earnings:**  A negative correlation was observed between future earnings and the percentage of Black, female, and Hispanic students, suggesting potential disparities.  Further investigation revealed a possible stronger negative correlation for non-white, non-Asian female students.  Analysis also indicated that universities with a higher percentage of female students do not necessarily produce graduates with the highest earnings.
    * **Conservatism and Education:** In conservative states, there is a lower graduation rate compared to the national average.  Interestingly, the percentage of female students in these states is not significantly lower than the national average, challenging initial assumptions.
    * **Financial Aid and University Characteristics:** UMAP and PCA analyses revealed clustering patterns related to financial aid.  Universities with higher scholarship rates were more dispersed, while those with lower rates clustered more distinctly, with some overlap.  Further analysis showed a strong correlation between higher test scores, earnings, tuition costs, and lower acceptance rates and scholarship percentages.
    * **Academic Performance and University Type:** Universities focused on research and medicine tend to have higher spending per student and attract students with higher test scores.
    * **Family Income and Graduation Rates:** A strong positive correlation was found between family income and graduation rates, suggesting that financial stability positively influences academic success.  A relationship was observed between lower family income and part-time student status, possibly due to students balancing work and studies.  A general trend showed that higher family income is inversely proportional to the level of upward mobility achieved after graduation, with some exceptions in top-ranked institutions.

4. **Reflections:** The project provided valuable learning experiences in data exploration, visualization techniques, and the importance of interactive elements for in-depth analysis.  The process of formulating and answering research questions through visualization proved particularly insightful.
