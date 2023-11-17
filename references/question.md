# Instructions

Below are a set of questions in relation to the churn prediction task. Please do your best to answer them and don't be afraid to add detail to your responses.

# Questions

1. The client uses Snowflake for storing a majority of their customer data. They wish to use the churn predictive model to make daily predictions on their customers and use derived output tables in Snowflake to build dashboards in Tableau for end-user interaction and wider stakeholder reporting. What would you recommend for deploying the model you have built / will build?


## Making predictions
alternative 1
The model can be contsainerized with Docker and deployed on a cloud service of their choice (AWS/Azure/GCP), comntainerization will ensure consistency across environments. 
For batch prediction: Snowflake connectors can be used to pull data from the client tables to the cloud environent, undertake the predictions and write back to another snowflake table. 
For online predictions: n API interface (flask or FastAPI) can be built to expose the model, allowing users to pass in new data and make instant predictions. These predicitons can then be passed back to the user for investigation, written to the snowflake prediuction table, or both. 

alternative 2
Alternatively, Snowflake's Snowpark allows the model development ot be undertaken completely with thin Snowflake ecosystem. This may reduce inference latency vs hosting on a seperate cloud provider, however latency rquirements vs cost implications would need to be assessed for this option. Using Snowpark would allow for easy integration with Snowflake tables and may ease complications around security. 

## Tableau Integration
Tableau can be easily integrated with Snowflake with Snowflake connectors. Once predictions are made and saved to a new table, these connectors allow tableau to read both the data provided to the model, and the predicted output. 


2. The client is cautious of needing to maintain the model after project completion. In particular, they are worried the model will gradually lose predictive capability due to changes in data over time. What systems and processes do you recommend implementing to support model maintenance? How can the client retain their confidence in the model and its outputs?

a. Data drift can be an issue when models are in production for an extended period. In order to detect changes, you can periodically make predictions on new data and setup monitoring to detect changes in performance metrics. There are also statistical methods for detecting whether a sample of data comes from the same distribvution as that the model has been trained on. The most basic would look at mean/median/variance, however more sophisticate dmethods such as the the Kolmogorov–Smirnov test also exist. 
If model appears to be suffering from data drift the simplest solution is to retrain on the entire dataset, alternatively you could assume data drift is inevitable and retrain peroidically regardless. 



4. During the delivery of the churn prediction project you will need to provide progress updates on model development. How would you seek to validate the model performance from a development perspective, and how would you use these results to inform wider non-technical stakeholders?

a.


3. The client is investing in capturing more data points on their customers with the intention of using this new data in the model at some point in the near future. What recommendations would you make to the client in regards to including these new features? For context, they have limited expertise in machine learning, but do have resource in business analytics and analytics engineering.

a.