# Heart Disease in Cleveland in 1990

## Data Information
The data used for analysis came from the Cleveland Clinic Foundation in 1990. It includes medical information from patients that measure different levels of cholesterol, heart beats, blood sugar levels, and whether or not these patients have a heart disease.

This database contains 76 attributes, but all published experiments
refer to using a subset of 14 of them. In particular, the Cleveland
database is the only one that has been used by ML researchers to 
this date. The "goal" field refers to the presence of heart disease
in the patient. It is integer valued from 0 (no presence) to 4.
Experiments with the Cleveland database have concentrated on simply
attempting to distinguish presence (values 1,2,3,4) from absence (value
0).  

The names and social security numbers of the patients were recently 
removed from the database, replaced with dummy values.

One file has been "processed", that one containing the Cleveland 
database. All four unprocessed files also exist in this directory.

## Public Interest Question
How does serum cholesterol and fasting blood sugar affect number of positive heart disease diagnosis in Cleveland?

## Source
Author: V.A. Medical Center, Long Beach and Cleveland Clinic Foundation:
	  Robert Detrano, M.D., Ph.D.
	  
https://archive.ics.uci.edu/dataset/45/heart+disease

## Variables
1. **age:** age in years
2. **sex:** sex (1 = male; 0 = female)
3. **cp:** chest pain type
      -- Value 1: typical angina
      -- Value 2: atypical angina
      -- Value 3: non-anginal pain
      -- Value 4: asymptomatic
4. **trestbps:** resting blood pressure (in mm Hg on admission to the hospital)
5. **chol:** serum cholesterol in mg/dl
6. **fbs:** (fasting blood sugar > 120 mg/dl)  (1 = true; 0 = false)
7. **restecg:** resting electrocardiographic results
      -- Value 0: normal
      -- Value 1: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
      -- Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria
8. **thalach:** maximum heart rate achieved
9. **exang:** exercise induced angina (1 = yes; 0 = no)
10. **oldpeak** = ST depression induced by exercise relative to rest
11. **slope:** the slope of the peak exercise ST segment
      -- Value 1: upsloping
      -- Value 2: flat
      -- Value 3: downsloping
12. **ca:** number of major vessels (0-3) colored by flourosopy
13. **thal:** 3 = normal; 6 = fixed defect; 7 = reversible defect
14. **num:** diagnosis of heart disease (angiographic disease status)
      -- Value 0: < 50% diameter narrowing
      -- Value 1: > 50% diameter narrowing

## Data Exploration
This is a quick summary of heart disease data from Cleveland in 1988. It shows the maximum, minimum, quartiles, median, and mean for most variables from the table. They give a clue about the ranges from each of the variables.

![Image](https://github.com/SMarbella/Cleveland-Heart-Disease-1990/blob/main/Data%20Exploration.png)
![Image](https://github.com/SMarbella/Cleveland-Heart-Disease-1990/blob/main/Data%20Exploration%20ggpairs.png)

According to the linear model, the intercept is the cholesterol level because the linear model function chooses the first column alphabetically. Residuals are the differences between the linear model's guess and the actual observation. The model underestimated the values by 121.91. The 1Q column indicates that 25% of the observations are smaller than -35.48. The median or middle of all the residuals indicates the the model underpredicts the average values by -5.48. The 3Q column indicates that 75% of all residuals are smaller than 28.52. The Max column is the largest positive residual, meaning that the model overestimated a value by 317.52.

The fbs> 120 mg/dl variable represents the indicator that indicates if the blood sugar is greater than 120 mg/dl. The Estimate column for cholesterol levels indicates that most of its values lie at an average of 246.481 with a standard error of 3.229. The error means that the deviation from the average varies up to 3.229. The number of people with blood sugar > 120 mg/dl is has a higher average than cholesterol by 1.430. The average number of people with higher blood sugar is 247.911. The linear model says that the relationship between cholesterol levels and ppeople's blood sugar is not significant due to the high p-value.

The linear model says that the relationship between cholesterol levels and blood sugar is not very significant because the correlation is very weak (Multiple R-squared: 9.685e-05).

![Image](https://github.com/SMarbella/Cleveland-Heart-Disease-1990/blob/main/Linear%20Model%20Summary.png)

## Plot
The programming language I used to generate my graphs and analytical results is R using R Studio. I used the boxplot graph to answer the public interest question.

![Image](https://github.com/SMarbella/Cleveland-Heart-Disease-1990/blob/main/Heart%20Disease%20Boxplot.png)

## Brief Summary
How does serum cholesterol and fasting blood sugar affect number of positive heart disease diagnosis in Cleveland?

The graph shows that people with heart disease and people without heart disease have a similar overlap with their cholesterol and fasting blood sugar levels. The risk of having heart disease remains similar no matter the blood sugar level.

People with higher cholesterol levels have a significantly higher risk of getting heart disease. Looking at the two red bar plots that symbolize people who are at risk of heart disease, the median for those who have higher blood sugar is slightly higher than those who have lower blood sugar. The bar plot for heart disease patients with higher fasting blood sugar levels is narrower than those who have a lower blood sugar level, which raises the cholesterol median by approximately 10 mg/dl.

People who are not at risk of heart disease generally have lower cholesterol levels than those with heart disease. Comparing the two green bar plots, the bar plot is narrower for those who have a higher blood sugar level.
