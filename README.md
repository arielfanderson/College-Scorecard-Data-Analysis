# College Scorecard Data Analysis in Python
Author: Ariel Anderson

## Introduction 
According to the [U.S. Department of Social Security](https://www.ssa.gov/policy/docs/research-summaries/education-earnings.html), college graduates net higher lifetime earnings than peers without a bachelor's or graduate degree. Yet, the [National Center for Educational Statistics](https://nces.ed.gov/fastfacts/display.asp?id=98) shows that enrollment in 4 year institutions has steadily fallen. Rising tuition costs, increased competition, lack of educational preparedness, student debt burden, and relative value of specific degree types may be factors in determining why enrollment has fallen. This is an exploratory project which examines various variables that could be contributing to decreased enrollement. The project also explores variables that may contribute to a student's success and lifetime earnings. This project was develope using publically accessible data from the [U.S. Department of Education College Scorecard](https://collegescorecard.ed.gov/). 

This document provides additional context to each section in the accompanying jupyter notebook. 

## Jupyter Noteboook Sections Methodology 
* Data Collection
* Demographic Changes  
* Tuition Rates & Debt Over Time
* Post Graduate Earnings
* Admission Rates 

## Technologies 
* Python

## Dependencies 
```python
# Data manipulation, cleaning, aggregation, and plots.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
import statsmodels.api as sm

# Access data files.
import os
```

## Data Collection 

Data was downloaded from [U.S. Department of Education College Scorecard](https://collegescorecard.ed.gov/) for the academic years 2000-2020, and stored locally. An API is available for Colleg Scorecard data. However, for this specific project, this method was not used. There is a sinlge file for each academic year. Each file was read in as a dataframe, assigned a column for the academic year, and then concatenated into a single large dataframe which can be indexed by the academic year. 

## Demographic Changes 

Note that the categorizations for demographic data changed in 2008 according to College Score Card. The academic years 2008-2009 and 2009-2010 contained underreported data for demographics, likely due to these changes in reporting. Therefore, years priror to the academic year 2009-2010 were omitted from the data.

This section explores demographic changes over time at 2 and 4 year institutions from the 2009-2010 academic year by looking at the demographic mean as a percentage across all institutions reported in the College Scorecard. College Scorecard uses the following categories for demograhics: White, Black, Asian, Hispanic, Native American/Alaskan Native, Native Hawaiian/Pacific Islander, Two or More reported Races, Non Citizen, and None Reported. Institutions that provided incomplete data were dropped from the analysis. Visualizations are displayed with Seaborn. 

For further insight into demographic changes at 2 and 4 year institutions regional trends could be evaluated.

## Tuition Rates & Debt Over Time

The second part of this project examines tuition rates as well as debt held by students, over a 20 year period starting with the academic year of 2000-2001 and ending with the academic year of 2019-2020. First, tuition rates, both in and out of state, in relation to debt held by student are examined. Data is aggregated by both the median and mean for tuition rates and debt held. Next, debt is shown in relation to groups defined by the College Scorecard: students from families with low income (<$35,000 a year), mediumn income (>$35,000 a year <$70,000 a year), high income (>$70,000 a year), dependent students (students under the age of 24 still claimed as a dependent on federal taxes), independent students (students over the age of 24 that can claim themselves as a independent), students that were eligble for a Pell Grant, students that were not Pell Grant eligible, female students, male students, first generation students, non-first generation students, students that graduated, and students that attended college but withdrew without a degree. 

## Earnings

The part of the project looks at earnings. Earnings are measured 6 years after a student graduates. Currently, earnings data is available from academic year 2003-2004 to 2014-2015.  ACT midpoint data is avaiable starting 2009-2010. Therefore, this data looks at the academic years 2009-2010 to 2014-2015. Data was cleaned to reflect this timelime. 

The first example looks at various variables to determine if earnings may be correlated with another value. Admission rate, debt median, tution in state, tuition out of state, SAT average, ACT English midpoint, ACT Math midpoint, ACT Writing midpoint, and ACT Composite midpoint. were selected from the dataset as possible variables that may correlate with earnings 6 years after graduation of a 4 year institution. A correlation coefficient is found for the correlation between the selected varibales and future earnings. The highest correlation is selected, and Statsmodels is used to demonstrate an Ordinary Least Squares Model. The OLS model is visualized. 

The final method in this section is visualizing earnings, by academic year, as box plots. The visualization can seen in the jupyter notebook. 


