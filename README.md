# LoanTap Logistic Regression

<div align="center">
  <img src="https://github.com/user-attachments/assets/60f6679a-0c7c-4a0d-b6a5-89d7341bcd4f" width = 200 height =170//>
  <img src="LoanTap Logo.png" width = 200 height =170>
  <img src="https://github.com/user-attachments/assets/03bce162-0bea-4a94-8f2c-b6e4179f8d01" width = 200 height =170/>
</div>

## 📚 About Data
LoanTap is an online platform committed to delivering customized loan products to millennials. They innovate in an otherwise dull loan segment, to deliver instant, flexible loans on consumer friendly terms to salaried professionals and businessmen.

The data science team at LoanTap is building an underwriting layer to determine the creditworthiness of MSMEs as well as individuals.

LoanTap deploys formal credit to salaried individuals and businesses 4 main financial instruments:

1. Personal Loan
2. EMI Free Loan
3. Personal Overdraft
4. Advance Salary Loan

This case study focuses on the underwriting process behind Personal Loan only

## 🎯 Objective
The company wants to know:

As a data scientist at LoanTap, company wants to know if a credit line should be extended to them. If so, what should the repayment terms be in business recommendations?

## 📃 Features of the dataset:

- Column Profiling:
  
| Feature | Description |
|:--------|:------------|
|loan_amnt| The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value|
| term | The number of payments on the loan. Values are in months and can be either 36 or 60|
| int_rate | Interest Rate on the loan|
| installment | The monthly payment owed by the borrower if the loan originates|
| grade | LoanTap assigned loan grade|
| sub_grade | LoanTap assigned loan subgrade|
| emp_title |The job title supplied by the Borrower when applying for the loan|
| emp_length | Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years|
| home_ownership | The home ownership status provided by the borrower during registration or obtained from the credit report|
| annual_inc | The self-reported annual income provided by the borrower during registration|
| verification_status | Indicates if income was verified by LoanTap, not verified, or if the income source was verified|
| issue_d | The month which the loan was funded|
| loan_status | Current status of the loan - Target Variable|
| purpose | A category provided by the borrower for the loan request|
| title | The loan title provided by the borrower|
| dti | A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LoanTap loan, divided by the borrower’s self-reported monthly income|
| earliest_cr_line |The month the borrower's earliest reported credit line was opened|
| open_acc | The number of open credit lines in the borrower's credit file|
| pub_rec | Number of derogatory public records|
| revol_bal | Total credit revolving balance|
| revol_util | Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit|
| total_acc | The total number of credit lines currently in the borrower's credit file|
| initial_list_status | The initial listing status of the loan| Possible values are – W, F|
| application_type | Indicates whether the loan is an individual application or a joint application with two co-borrowers|
| mort_acc | Number of mortgage accounts|
| pub_rec_bankruptcies | Number of public record bankruptcies|
| Address| Address of the individual|

</br>

## **🖋️ Performed the following tasks:**

1. **Problem Definition**  
   - Defined the problem based on the provided problem statement.  
   - Added additional context and assumptions wherever necessary to better understand the business objective and challenges.

2. **Initial Data Understanding**  
   - Observed the shape of the dataset and data types of all attributes.  
   - Converted relevant categorical attributes to `'category'` datatype to optimize memory usage and ensure efficient processing.  
   - Detected and reported missing values across all columns.  
   - Generated a statistical summary (mean, median, standard deviation, etc.) for all numeric features.

3. **Exploratory Data Analysis (EDA)**  
   - **Univariate Analysis:**  
     - Plotted distribution plots for all continuous variables.  
     - Created bar plots/count plots for all categorical variables.  
     - Provided detailed comments on each plot highlighting trends and anomalies.  
     
   - **Bivariate Analysis:**  
     - Analyzed relationships between key independent variables and the target variable using scatter plots, box plots, and grouped summaries.  
     - Provided insights for each bivariate plot to interpret relationships.

4. **Insights from EDA**  
   - Commented on the range, skewness, and distribution of variables.  
   - Identified outliers using box plots and statistical methods (e.g., IQR).  
   - Summarized key patterns and their possible business implications.  
   - Highlighted variables with strong influence on the target based on visual and statistical evidence.

5. **Data Preprocessing**  
   - Checked and removed duplicate records, if any.  
   - Treated missing values using appropriate techniques (e.g., mean/median imputation, mode imputation, or dropping).  
   - Handled outliers through capping or transformation techniques.  
   - Engineered new features to improve model performance based on domain logic.  
   - Prepared final dataset by encoding categorical variables and scaling numerical features as needed.

6. **Model Building**  
   - Built a Logistic Regression model to predict the target outcome.  
   - Interpreted and commented on the model's coefficients and statistical significance.  
   - Displayed model coefficients along with their corresponding feature names.

7. **Results Evaluation**  
   - Plotted and analyzed the **ROC AUC Curve**, commented on model discrimination ability.  
   - Plotted the **Precision-Recall Curve**, highlighted its importance in imbalanced datasets.  
   - Presented the **Classification Report** including accuracy, precision, recall, F1-score, and Confusion Matrix with interpretations.

8. **Trade-off Analysis**  
   - Answered strategic questions:
     - *How to reduce false positives while ensuring high recall*: Discussed adjusting thresholds, using precision-recall trade-off, and cost-sensitive learning.  
     - *How to minimize NPAs*: Recommended higher precision, stricter credit policy, and ensemble methods for better classification of potential defaulters.

9. **Actionable Insights & Recommendations**  
   - Shared key findings to guide business actions, such as:
     - Which features are highly predictive of default.  
     - Risk thresholds for approving or rejecting loans.  
     - Suggestions to improve data collection for better modeling accuracy.

</br>

## 📝 Business Insights & Recommendations : 
<p>- Includes patterns observed in the data along with what can infer from it.</p>

1. Customers with Grade A are the most reliable on the repayments. Bank can extend the credit line to these customers and should focus and adding more new customers to list of borrowers. 93% of these have a track record of repaying their loan.

2. The term period of 60 months is a trouble when it comes to Charged Off accounts. 32% of accounts from 60 months term period turned into NPA based on the data available. So, here needs to rethink on the repayment terms.
  
3. The median annual income of Charged Off customers is 59K which is 6K less than median annual income of Fully Paid customers (65K). Please revisit the annual income thresholds while extending the credit lines to the customers.
   
4. The median dti ratio of Charged Off customers is 19.34 which is 3 points higher than the fully paid customers. Please give it a thought. This feature tops in first 5 most impactful features.

5. 37% of the grade E and 28% of the grade D customers are defaulters from historical data. The needs to put
 more stringent criteria and the grade E and D customers.

6. Median interest rates of defaulter customers are 2.62% higher than those of regular. Median interest rate of regualr customers is 12.99% and for defaulters it's found that median interest rate is 15.61%. If the customer interest rates crawl above the alarming thresholds then that account is more probably more prone to
 become an NPA

7. Apart from this, the bank needs to focus more on improving the precision of correctly identifying the Charged Off customer. Becuase the current historical data trend shows that the bank is not so accurate in classifying the Charged Off customers. However these customers often get the green pass as a result of high FPR (False Positive Rate).

### Description about file in repository <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Hand%20gestures/Backhand%20Index%20Pointing%20Down%20Light%20Skin%20Tone.png" alt="Backhand Index Pointing Down Light Skin Tone" width="30" height="30" />:

<a href="LoanTap Logistic Regression Case Study.pdf">**LoanTap Logistic Regression Case Study.pdf** </a>- PDF containing the code for analysis
