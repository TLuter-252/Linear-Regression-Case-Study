# Loan Interest Rate Analysis

## 1. Project Objective
The goal of this project is to understand **what drives the interest rate** on individual loans.  
The main question we want to answer is:

**Which borrower or loan features change the interest rate?**

This matters for new business owners because a lower interest rate makes borrowing cheaper, lowers monthly payments, and reduces overall financial risk.

---

## 2. Data Overview
We worked with a loan dataset that includes:

- `interest_rate` — the loan's interest rate (**our target variable**).  
- `fico_range` — the borrower’s credit score range (example: `720–724`).  
- `amount_requested` — how much money the borrower asked for.  
- `amount_funded_by_investors` — how much investors actually funded.  
- `loan_length` — how long the loan lasts (in months).

### Creating `fico_score`
Because `fico_range` is a range like “720–724”, we converted it into a single number called **fico_score** by taking the mean of the range.  
This made it easier to use in plots.

---

## 3. Exploratory Analysis

Before modeling, we looked at simple relationships between the features and interest rate.

### FICO Score vs Interest Rate
When we plotted `fico_score` against `interest_rate`, we saw:

**Higher credit scores usually have lower interest rates.**

### Loan Length vs Interest Rate
When we plotted `loan_length` against `interest_rate`, we saw:

**Longer-term loans tend to have higher interest rates.**

### Loan Amount
Loan amount variables did not show strong patterns with interest rate, so they were not used in the final model.

---

## 4. Modeling Approach

We built a **linear regression model** using `interest_rate` as the target.

### Using MinMaxScaler
We scaled numeric features using:

```python
scaler = MinMaxScaler()
df[columns] = scaler.fit_transform(df[columns])
```

**Why:**  
- Regression works better when features are on the same scale.  
- Prevents large features from overpowering smaller ones.  

### Using `transform()`
After fitting the scaler, we used:

```python
X_scaled = scaler.transform(X)
```

This ensures the model receives the same scaling used during training.

### OLS Model (Statsmodels)
We used:

```python
ols_model.summary()
```

This gave us:

- **Coefficients (coef):** Show direction and strength of each feature’s effect.  
  - `fico_score` had a **negative coef** → higher score = lower rate  
  - `loan_length` had a **positive coef** → longer term = higher rate  

- **p-values:** Both features had **p < 0.05**, meaning they significantly affect interest rate.

- **R-squared:** Showed the model explains a meaningful part of interest rate changes.

---

## 5. Results Summary for Business Owners

### Key Findings
- **Credit score is the biggest driver of interest rate.**
- **Longer loan lengths lead to higher interest rates.**



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

  # 4- Modeling Approach

  Feature Engineering

     - Converted fico_range to three numeric fico features: fico_low, fico_high, and fico_score
  
  Model Used

     - Linear Regression (sklearn)
  
  Selected Features:

     - interest_rate, fico_score, loan_length, amount_requested, amount_funded_by_investors

  Model Performance

     - R2 Score: 
     - Residual Plots:
     - FICO Score had the strongest negative coefficient
     - Loan length (60-month) had mvery minimal positive effect on interest rate