# Congratulations!
Congratulations on getting to the next stage in the application process. As part of this next stage, we ask you complete the QuantSpark Machine Learning assessment. We hope the test will only take 2-3 hours - please don’t feel obliged to continue past that. It’s okay if you cannot completely finish the test, simply give us some details of what you would have done when notifying us of your submission.

Please send us your submission either as a link to a Git repo hosted in a platform of your choice (e.g. GitHub, Bitbucket or GitLab), or alternatively by uploading a zipped folder of your submission to the following link:
LINK

# Tasks
1. Please follow the task instructions written below, we have provided a dataset (dataset.csv) for this task.
2. We have provided a set of questions (questions.md), please answer them as best you can. They relate to the problem described below.

# Churn Prediction Task

## Problem area
- A B2B SaaS business is looking to build a predictive model to detect customer churn. They have provided a renewals dataset that contains monthly data on their customers, consisting of a mix of profile, usage, and engagement data.
- The client wish to detect customer churn up to twelve months from renewal to provide their customer success team enough time to action preventative measures.
- The model needs to be able to effectively provide a risk score for customers representing propensity to churn. The client also wishes to understand why a customer has been classed as high/low risk, to guide customer success in the conversations they have with the customer / action they take to mitigate.
- The client is also keen to ensure the model is well validated, so they can be confident in the model outputs.

## Task objectives
- Your task is to develop a model and outputs in line with the requirements above.
- Please provide all the work you conduct towards the task, and ensure it is well commented/documented for easy interpretation.
- We also encourage detailing your thought process behind the decisions you make throughout.

# Dataset
## Identifiers and date fields
- SALESFORCEACCOUNTID : Customer unique identifier 
- ACCOUNTING_MONTH : Accounting Month
- RENEWAL_MONTH : Date the customer's contract renews
- CONTRACT_START_DATE : Date the customer contract started 

## Profile information
- REGION : Customer's region
- SECTOR : Customer's sector
- TENURE_MONTHS : Number of months tenure
- DNB_GLOBAL_SALES_REVENUE : Global sales revenue (third-party data)
- DNB_GLOBAL_EMPLOYEE_COUNT : Global employee count (third-party data)
- CONTRACT_LENGTH : Contract length (days)

## Customer size
- ARR : Annual Recurring Revenue
- SEATS : Number of seats purchased
- COMPETITOR_SEATS : Number of seats with competitor

## Customer products
- PRODUCT_ONE : Binary encoding for if the customer has this product
- PRODUCT_TWO : Binary encoding for if the customer has this product
- PRODUCT_THREE : Binary encoding for if the customer has this product
- PRODUCT_FOUR : Binary encoding for if the customer has this product
- PRODUCT_FIVE : Binary encoding for if the customer has this product
- PRODUCT_SIX : Binary encoding for if the customer has this product
- PRODUCT_SEVEN : Binary encoding for if the customer has this product
- PRODUCT_EIGHT : Binary encoding for if the customer has this product
- PRODUCT_NINE : Binary encoding for if the customer has this product
- PRODUCT_TEN : Binary encoding for if the customer has this product
- PRODUCT_ELEVEN : Binary encoding for if the customer has this product
- PRODUCT_TWELVE : Binary encoding for if the customer has this product
- PRODUCT_THIRTEEN : Binary encoding for if the customer has this product
- PRODUCT_FOURTEEN : Binary encoding for if the customer has this product
- PRODUCT_FIFTEEN : Binary encoding for if the customer has this product
- PRODUCT_SIXTEEN : Binary encoding for if the customer has this product
- PRODUCT_SEVENTEEN : Binary encoding for if the customer has this product
- PRODUCT_EIGHTEEN : Binary encoding for if the customer has this product
- PRODUCT_NINETEEN : Binary encoding for if the customer has this product
- PRODUCT_TWENTY : Binary encoding for if the customer has this product
- PRODUCT_TWENTYONE : Binary encoding for if the customer has this product
- PRODUCT_TWENTYTWO : Binary encoding for if the customer has this product
- PRODUCT_TWENTYTHREE : Binary encoding for if the customer has this product

## Service Account Management
- LICENSINGSPECIALIST_CHANGE : Licensing Specialist changes
- SALESREP_CHANGE : Sales Rep changes
- UPSELLMANAGER_CHANGE : Upsell Manager changes
- ACCOUNTMANAGER_CHANGE : Account Manager changes

## Events / Engagements
- CHURN_RISK_DISCUSSION : The customer attended a churn risk discussion engagement
- CUSTOMER_HEALTH_CHECK : The customer attended a health check
- CS_EVENT_ATTENDED : The customer attended an engagement with customer success

## Account Movements
- CROSS_SELL_RECENCY : Number of months since last cross-sell (products)
- SEATS_DOWNSELL_RECENCY : Number of months since last downsell (seats)
- PRODUCT_DOWNSELL_RECENCY : Number of months since last downsell (products)
- SEATS_UPSELL_RECENCY : Number of months since last upsell (seats)

## Product usage
- DETECTEDSEATSCOUNT : Number of seats detected to be in use
- CUSTOMER_BEHAVIOUR_ONE : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_TWO : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_THREE : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_FOUR : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_FIVE : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_SIX : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_SEVEN : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_EIGHT : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_NINE : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_TEN : Usage of a particular product feature
- CUSTOMER_BEHAVIOUR_ELEVEN : Usage of a particular product feature

## Product configuration settings
- PCT_PRODUCT_TWO_ENABLED : Percent of product features enabled
- PCT_PRODUCT_THREE_ENABLED : Percent of product features enabled
- PCT_PRODUCT_FOUR_ENABLED : Percent of product features enabled
- PCT_PRODUCT_FIVE_ENABLED : Percent of product features enabled
- PCT_PRODUCT_SIX_ENABLED : Percent of product features enabled
- PCT_PRODUCT_NINE_ENABLED : Percent of product features enabled
- PCT_PRODUCT_TWO_BEST_PRACTICE : Percent of product features best practice
- PCT_PRODUCT_THREE_BEST_PRACTICE : Percent of product features best practice
- PCT_PRODUCT_FOUR_BEST_PRACTICE : Percent of product features best practice

## Support cases
- MAX_SUPPORT_CASE_DAYSTOCLOSE : Maximum number of days to close a support case
- MAX_SUPPORT_CASE_TIMETOFIRSTRESPONSE : Maximum minutes to first response on a support case
- AVG_SUPPORT_CASE_PRIORITY_SCORE : Average support case priority score
- SUM_SEVERE_CASES : Sum of support cases at severe severity
- SUM_HIGH_CASES : Sum of support cases at high severity
- SUM_MEDIUM_CASES : Sum of support cases at medium severity
- SUM_LOW_CASES : Sum of support cases at low severity
- SUM_STANDARD_CASES : Sum of support cases at standard severity
- SUPPORT_CASE_NUMBEROFSLABREACHES : Number of support case SLA breaches
- BACKLOG : Number of non-closed cases more than 60 days old

## Surveys
- SURVEY_AVG_CXI_SCORE : Average product CXI survey score
- SURVEY_AVG_NPS_SCORE : Average NPS score
- SURVEY_AVG_CASE_MOOD_SCORE : Average support case mood score

## Target fields
- CHURN : Binary encoding of whether the customer churned that month