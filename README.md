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

     The dataset includes loan recors with several important bowrrower and loan attributes:

  - interest_rate:    is the target variable 

  - fico_range:       borrower credit score range. We converted this feature to numeric by separating it into  
                      three different numeric columns: fico_low, fico_high, and fico_score

  - amount_requested:  total loan amount asked for

  - amount_funded_by_investors:    How much investors funded

  - loan_length:    Term in months (36 aand 60)

  We determined that most relevant variables for predicting interest rate are:
    
    - fico_score (strong fico-score correlation with interest_rates "the higher fico_score is the lower  
      interest_rate is)
    - loan_length (60-month loans cost  more)
    - amount_requested (larger loans often see higher laon fees)
