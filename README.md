# BST260FinalProject

**Project Title**: Off The Clock: Gender Inequity In and Out of the Workforce
**Data Source**: OECD data
**Group Members**: Sarah Christensen, Kelly Fung, Dipal Nagda, Anu Neupane, & Julia Olsen

### How to Navigate Repository
Our repository contains our data file and several RMD files containing our analyses.  
**Data file**: data1.csv  
**Recommended order of file viewing**:  
      1. 1_Descriptive Stats and Linear Regression_Dipal Nagda  
      2. 2_Maps_Anu Neupane  
      3. 3_MachineLearning2_Kelly Fung  
      4. 4_MachineLearning_Sarah Christensen
      5. 5_Shiny App_Julia Olsen  

### Website & Screencast Links:
- Website:
- Screencast:

### Overview and Motivation - Anu
Gender inequality, a widely prevalent social phenomenon, has risen to the forefront of global discussion after the COVID- 19 pandemic. An article published by UN women (https://data.unwomen.org/sites/default/files/inline-files/Whose-time-to-care-brief_0.pdf) states that while women already spent about three times as many hours in unpaid domestic work than men, the pandemic has exacerbated this gap. During the pandemic, women spent more hours in care and domestic work. Women were also more likely than men to leave the workforce , potentially as a consequence of increased workloads. 

While some countries tried to reduce the burden of women by offering cash benefits and care facilities, data shows that an overwhelming percentage of the worlds women and girls will be facing impoverished conditions as a result of the pandemic. 

Through this project we want to get a better understanding of the economic disadvantages that women face worldwide. By exploring factors such as differences in time spent in paid and unpaid work, leadership representation and maternity leave among others, we want to present a coherent picture of the economic and political gender disparities across OECD (Organisation for Economic Co-operation and Development) countries in this dataset. 

### Related Work - Anu 

Our motivation for this project was the article (link provided above) published by UN Women which dives deep into disparities in unpaid domestic work as a result of the COVID pandemic and an interactive dashboard (https://interactive.unwomen.org/multimedia/explainer/unpaidcare/en/index.html?gclid=CjwKCAiA78aNBhAlEiwA7B76p5E1YtiUgfS3TnuIViVn56UPe4krtgSfQtNlM2G8TeP2Od7f5VzjPRoCCJgQAvD_BwE) which allows individuals to calculate the amount of time they spend on unpaid domestic and care tasks and how that compares to the global average. 

### Initial Questions - Kelly

Our initial question for the project was: How does the amount of time spent in unpaid work differ between men and women, and which employment-related variables are predictors of that disparity? 

Over the course of the project, we also incorporated analyses for the following questions: 

- Are there any global differences in time spent in unpaid labor between men and women?
- How have employment trends and leadership representation for women changed longitudinally? 
- What are some key predictors of the length of maternity and parental leave?

### Data - Sarah

We used publicly available data from the Organization for Economic Co-operation and Development (OECD)  (https://stats.oecd.org/index.aspx?queryid=54757) in our analyses. These data include country-level measurements collected annually (and, in some cases, quarterly) on a number of variables ranging from “time spent in unpaid work” to “female share of seats on boards of the largest publicly listed companies”. (An exhaustive list of variables used can be found below). Queries for variables of interest were selected for on the OECD website in addition to variable measurements for time (1970-present, including some years divided out quarterly), sex (male, female), and age (categories: total, 15+, 55+, 15-24, 15-64, 25-64, and 55-64). The final query was downloaded as comma separated value files (.csv files) and read into R Studio resulting in a single, long-format dataframe. Duplicate variables were dropped, and an OECD country label was added as a separate variable to the dataframe. This allowed us to analyse results only within OECD countries and to compare OECD countries against non-OECD countries. By design, further analysis on this dataframe required individuals to filter by variables of interest and convert data to wide format prior to running analyses. 

Definitions and units for variables in data frame:

- unpaid_time: Time spent in unpaid work (minutes per day)
- paid_time: Time spent in paid work (minutes per day)
- total_time: Time spent in total work (minutes per day)
- agriculture_work: Share of employed working in agriculturex (percentages)
- services_work: Share of employed working in services (percentages)       
- maternity_leave: Length of maternity leave (weeks)
- leave_job_protection: Length of parental leave with job protection (weeks)
- total_paid_leave: Total length of paid maternity and parental leave (weeks)
- paternal_leave: Length of paid father-specific leave (weeks)
- share_managers: Share of employed who are managers (percentages)
- female_share_boards: Female share of seats on boards of the largest publicly listed companies (percentages)
- share_involuntary_parttime: Share of employed in involuntary part-time employment (percentages)
- prop_unpaid: Proportion of time in total work spent in unpaid labor (percentages) 

### Exploratory Analysis - Dipal

We first used a variety of descriptive statistics to explore the data and understand the underlying trends in unpaid, paid, and total labor between the OECD countries. A total of 35 OECD countries are represented in the analysis. To standardize and compare the time spent in unpaid labor between all countries, we created a ratio variable of unpaid time over total labor time. The shares of paid and unpaid time were compared using independent two-sample t-tests, demonstrating statistically significant differences in unpaid time between men and women. 

We next created a series of bar charts to visualize the differences between countries and sex, with respect to labor time and other economic and political variables. These covariates, such as maternity leave and share of involuntary labor time, demonstrated great variability between the OECD countries. Finally, to prepare for the linear regression, a series of scatter plots were created to assess for linearity between proportion of time in unpaid labor and the included covariates. Our initial hypothesis was that increased political and economic representation of women would correlate to lower proportion of unpaid labor. Given our small sample size and lack of important other covariates in our dataset, we did not see a linear trend in these scatter plots.

### Final Analysis - Julia

Linear regression: We combined several of the covariates into a model to assess their correlation with the proportion of unpaid time amongst women in OECD countries. Though none of these covariates emerged as statistically significant predictors, we evaluated the direction of the coefficients as suggestive of potential trends in the data. A significant limitation of our linear regression model is the omission of significant predictors (such as income, educational status and age) from our dataset.

Final analysis for Maps: The maps allow us to hypothesize that in countries where women spend more time in unpaid work, men usually spend more time in paid work. Women may also have less representation in leadership positions in countries where they spend more time in unpaid work compared to men and/ or countries where men spend more time in paid work compared to women. 

