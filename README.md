# Determining the Impact of Socio-Economic Factors on ACT/SAT Scores
Repository for DATA 3320 project 2.

# Project Description
This project will apply regression analysis to determine how various socio-economic factors and a school's capital allocation correlate to their students' average SAT and ACT scores. This process will determine a predictive model that can estimate what a school's typical SAT/ACT score will be given their socio-economic and capital allocation information.

# Data
Three datasets will be used. The first is from EdGap, which sources standardized test scores from each state's department of education. EdGap also tracks socio-economic factors by zip code through the Census Bureau’s American Community Survey. EdGap Data can be viewed at: https://github.com/joeyuy/Education-Inequality/blob/main/EdGap_data.xlsx

The second dataset is from the National Center for Education Statistics (NCES) which provides additional information for each school. The data can be viewed at: https://drive.usercontent.google.com/u/0/uc?id=1HvW2w-o2XZzCm4KTvnb1Bb3BvoAa14BP&export=download

The third data set is from the US Census Annual Survey of School System Finances Tables, and gives insight into how much money schools in a district are putting into various departments. The data can be viewed at: https://github.com/joeyuy/Education-Inequality/blob/main/school_census_data.csv

The EdGap and NCES datasets uniquely identify each school via the NCESSCH School ID, while the Census data identifies regions with the NCES id, a substring of the NCESSCH id.

# Data Preparation
Data from the above mentioned data sources were filtered down to relevant socio-economic, capital allocation, and performance (ACT scores) variables. Then, they are merged using the NCESSCH ID variable as the primary key. Rows with out of range variables (eg negative percentages) are dropped. To prepare the data for regression analysis, the data is split into a training and test set (80/20 ratio) and quantitative variables are normalized. Each of these data sets were cleaned by imputing NaN's in quantitative data, and dropping rows with NaN's in qualitative data.

Data preparation was done in the jupyter notebook file: Education_Inequality_Data_Preparation.ipynb

The cleaned training and testing data sets can be viewed at:
1. education_train.csv
2. education_test.csv

# Regression Analysis
The prepared data sets were used to build a regression analysis model. The best potential subsets of model features were first identified. These subsets were tested with random tuning parameters using elastic net regression on the training data. After determining the best subset and paramter to move on with, the model is applied on the test data and results are interpreted. All analysis can be viewed at: Education_Regression_Analysis.ipynb

# Authors
Joel Stockton Uy 

https://www.linkedin.com/in/joel-uy/

# License
This project is licensed under the terms of Open Software License 3.0

License Keyword: OSL-3.0

