# What Factors Most Correlate to a Low Interest Rate

## Project Overview

### **<ins>Research Question: </ins>**
**Question:______**

## Findings
1. 
2. 
3. 
4. 



## Authors

- [@mad1h](https://www.github.com/mad1h)
- []()
- []()
- []()

## Joe's Notes for PowerPoint Presentation:

# 1- Project Objective
  - Tile: What factors drive the interest rates offered to borrowers?

  - Goal: Identify which borrower or loan characteristics most strongly influence interest rates, so business  
    owners can understand how to secure better loan terms.

  - Why This Matters: 
    
    - Interest rate = cost of borrowing
    - Even small differences can change totalt cost by thousands
    - Understanding what lendors prioritize helps business owners improve their loan profiles

# 2- Data Overview

     The dataset includes loan records with several important bowrrower and loan attributes:

  - interest_rate:    is the target variable 

  - fico_range:       borrower credit score range. We converted this feature to numeric by separating it into  
                      three different numeric columns: fico_low, fico_high, and fico_score

  - amount_requested:  total loan amount asked for

  - amount_funded_by_investors:    How much investors funded

  - loan_length:    Term in months (36 and 60)

  We determined that most relevant variables for predicting interest rate are:
    
    - fico_score (strong fico-score correlation with interest_rates "the higher fico_score is the lower  
      interest_rate is)
    - loan_length (60-month loans cost more)
    - amount_requested (larger loans requested often see higher interest_rates)
    - amount_funded (larger loans funded often see higher interest_rates)

# 3- Exploratory Insights

  Variables/Features Realtionship Highlights:

- Higher FICO scores substantially lower interest rates, which is a clear negative correlation

- 60-month loans have significantly higher interest rates. This means  that longer terms are considered to have  
  more risks and therefore results in more interest.  

- Amount requested and funded have extremely small positive correlation with higher interest_rates

  Distribution Notes:  

    - Interest rate is right-skewed
    - Loan length only has two levels
    - FICO is right-skewed
  

  Useful Visuals:

    - Scatter plot: FICO Score vs interest_rate
    - Scatter plot: amount_requested vs interest_rate
    - Boxplot: interest_rate by loan_length