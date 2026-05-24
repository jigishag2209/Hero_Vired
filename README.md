# Hero FinCorp Project- Comprehensive Data-Driven Analysis
## Tool: Python (pandas, matplotlib, seaborn)
 
### 1.  Introduction
This report summarises a data analysis project on Hero FinCorp's loan and customer data. The aim was to use Python to clean, explore and analyse six datasetsa and then draw insights to help Hero FinCorp reduce defaults, improve branch efficiency and grow profitability.
All 20 analysis tasks were completed in a single Jupyter Notebook. This report explains what was done in each task and what was found.

### Datasets Used
•	customers.csv  -  139,615 customer records with income, credit score, demographics  
• loans.csv  -  90,000 loan records with amount, interest rate, term, status  
•	applications.csv  -  82,600 application records with approval status and rejection reasons  
•	transactions.csv  -  495,000 transaction records including EMI payments and penalties  
•	defaults.csv  -  9,000 records of customers who defaulted on loans  
•	branches.csv  -  50 branch records with regional performance metrics   

### Python Libraries Used
•	pandas  -  loading, merging, cleaning, and grouping data    
•	numpy  -  numerical calculations and handling edge cases  
•	matplotlib and seaborn  -  creating all charts and visualisations  

### Data Cleaning & Preparation  (Task 1)
Before doing any analysis, the data needs to be cleaned. Raw data almost always has problems such as missing values, duplicate rows, improper date format. All such issues were fixed all of these in Task 1.

### ■  Steps 
•	Missing values: Credit scores and annual income were filled using the median value. Blank rejection reasons were filled with the text 'Not Rejected' assuming that a blank means the application was not rejected.  
•	Duplicates: All six datasets were checked for identical duplicate rows and removed the duplicates found.    
•	Date columns: Converted from plain text to proper Python datetime format so it coule be used in later tasks.  
•	Outliers: Interquartile range was calculated then the outliers were removed from Loan_Amount, Interest_Rate, and Default_Amount  


## Analysis Tasks  
### Task 2  Descriptive Analysis

Plotted the distribution of Loan Amount, EMI Amount, and Credit Score. Also looked at regional loan disbursement and monthly application volume. Loan amounts follow a roughly normal distribution. Some regions disburse significantly more loans than others, showing geographic variation in the business.

### Task 3  Default Risk Analysis
Merged loans and defaults datasets on Loan_ID to create a Default_Flag column (1 = defaulted, 0 = not). Calculated correlations between loan attributes and default behaviour. Higher interest rates are slightly linked to more defaults. Higher credit scores are linked to fewer defaults. This shows us the importance of credit checks in the approval process.

### Task 4  Branch & Regional Performance
Ranked branches by total loan disbursement volume, average processing time, and default rate. Compared performance across all regions. Default rates change across regions. Some branches process loans much faster than others which suggests differences in internal processes.  

### Task 5  Customer Segmentation
Split customers into income groups and credit groups. Then calculated the default rate for each combination to identify the riskiest and safest segments. Customers with low income and low credit scores have the highest default rates.

### Task 6  Advanced Statistical Analysis
Extended the correlation analysis to include Age, Annual Income and Overdue Amount. Also produced a branch-level correlation heatmap to understand which branch metrics are linked. Overdue amount is strongly associated with defaults which means customers with overdue balances are far more likely to default. Branches with more delinquent loans also tend to have lower overall efficiency.

### Task 7  Transaction & Recovery Analysis
Analysed transaction types, calculated the overdue fee ratio, and evaluated recovery rates broken down by default reason and legal action status. Penalty transactions represent a small but notable share of total transaction value. Recovery rates differ significantly by default reason - some reasons are harder to recover from than others.

### Task 8  EMI Analysis
Verified EMI amounts using the standard formula. Divided loans into EMI quartile bins and compared default rates across each group. Very high EMI loans carry a slightly elevated default risk. This may indicate customers taking on more repayment than they can comfortably afford.

### Task 9  Loan Application Insights
Calculated approval and rejection rates, found the most common rejection reasons, and compared processing fees between approved and rejected applications. A significant proportion of applications are rejected. The top rejection reasons are credit and income related. Interestingly, rejected applications still generate processing fees for Hero FinCorp.

### Task 11  Loan Disbursement Efficiency
Calculated actual processing time as Approval_Date minus Application_Date. Compared across approval statuses and used branches.csv for branch-level comparison. Rejected applications take longer on average - possibly because edge cases need more review. Branches vary significantly in their processing speed.

### Task 17  Customer Behaviour Analysis
Categorised customers as On-Time, Occasional Delay, or Frequent Defaulter based on total overdue fees. Cross-referenced with gender and income group. The large majority of customers pay on time. A small segment generates most of the overdue fees and can be targeted for early intervention or tighter loan terms.

### Task 18  Risk Assessment
Built a risk matrix by binning Loan Amount and Interest Rate into Low/Medium/High groups and calculating average default rate per combination. High loan amount combined with high interest rate produces the highest default rates. These combinations should trigger extra checks during the approval process.

### Task 19  Time to Default Analysis
Calculated days from Disbursal_Date to Default_Date for every defaulted loan. Compared this across default reasons. Most defaults happen within the first half of the loan term. Job loss defaults tend to occur earlier than other reasons, suggesting less financial cushion in this group.

### Task 20  Transaction Pattern Analysis
Created an irregularity score per customer (overdue fees divided by total amount paid). Identified the most irregular customers and compared transaction sizes for overdue vs non-overdue loans. Most customers have very low irregularity scores. The top irregular customers stand out clearly and could benefit from a restructuring conversation before they formally default.

### Recommendations
•	Apply stricter checks for Low Income + Low Credit Score applicants before approving loans.  
•	Set EMI limits reasonable to a customer's monthly income.  
•	Escalate to legal action earlier in the collection process    
•	Understand the reasons why some branches have long average processing time    
•	Share best practices from top-performing branches across the network.   
•	Target high-income, high-credit-score customers  



