# College Scorecard Data Analysis in Python
Author: Ariel Anderson

## Introduction 
According to the [U.S. Department of Social Security](https://www.ssa.gov/policy/docs/research-summaries/education-earnings.html), college graduates net higher lifetime earnings than peers without a bachelor's or graduate degree. Yet, the [National Center for Educational Statistics](https://nces.ed.gov/fastfacts/display.asp?id=98) shows that enrollment in 4 year institutions has steadily fallen. Rising tuition costs, increased competition, lack of educational preparedness, student debt burden, and relative value of specific degree types may be factors in determining why enrollment has fallen. This is an exploratory project which examines various variables that could be contributing to decreased enrollement. The project also explores variables that may contribute to a student's success and lifetime earnings. This project was develope using publically accessible data from the [U.S. Department of Education College Scorecard](https://collegescorecard.ed.gov/). 

This document provides additional context to each section in the accompanying jupyter notebook. 

## Jupyter Noteboook Sections 
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

The second part of this project examines tuition rates in relation to median debt held by student, both in state and out of state, over a 20 year period starting with the academic year of 2000-2001 and ending with the academic year of 2019-2020. 



