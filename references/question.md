# Instructions



Below are a set of questions in relation to the churn prediction task. Please do your best to answer them and don't be afraid to add detail to your responses.



# Questions



1. The client uses Snowflake for storing a majority of their customer data. They wish to use the churn predictive model to make daily predictions on their customers and use derived output tables in Snowflake to build dashboards in Tableau for end-user interaction and wider stakeholder reporting. What would you recommend for deploying the model you have built / will build?


## Making predictions
Alternative 1
The model can be containerized with Docker and deployed on a cloud service of their choice (AWS/Azure/GCP), containerization will ensure consistency across environments.
For batch prediction, Snowflake connectors can be used to pull data from the client tables to the cloud environment, where the model will undertake predictions, before subsequently writing these to another snowflake table for storage and downstream processing.
For online predictions, an API interface (flask or FastAPI) can be built to expose the model interface, allowing users to pass in new data and make instant predictions. These predictions can then be passed back to the user for investigation, written to the snowflake predictions table for storage, or both.


Alternative 2
Alternatively, Snowflake's Snowpark allows the model development to be undertaken completely within the Snowflake ecosystem. While this may potentially reduce inference latency compared to hosting on a separate cloud provider, it's essential to evaluate the trade-off between latency requirements and cost implications. Using Snowpark would allow for easy integration with Snowflake tables and may ease complications around security.



## Tableau Integration
Tableau can be easily integrated with Snowflake with Snowflake connectors. Once predictions are made and saved to a new table, these connectors allow Tableau to read both the data provided to the model to make the prediction and the predicted output.




2. The client is cautious about needing to maintain the model after project completion. In particular, they are worried the model will gradually lose predictive capability due to changes in data over time. What systems and processes do you recommend implementing to support model maintenance? How can the client retain their confidence in the model and its outputs?



a. Data drift can be an issue when models are in production for an extended period. In order to detect changes, you can periodically make predictions on new data and set up automatic monitoring to detect and alert changes in performance metrics. There are also statistical methods for detecting whether a sample of data comes from the same distribution as the model has been trained on. The most basic would compare the mean, median, and variance between the two data distributions; however, more sophisticated methods such as the Kolmogorov-Smirnov test also exist.
If the model appears to be suffering from data drift, the simplest solution is to retrain on the entire dataset; alternatively, *continual learning* can be implemented, where the model automatically retrains when it receives a new batch of data. The size of the batch required to qualify for retraining depends on the time taken for the model to decay and the frequency of new data being received.
Depending on the amount of new data incoming and the specific task at hand, it may be beneficial to remove the oldest portions of the dataset and train only on the most relevant and up-to-date data. For example, if the initial model is trained on 10,000 data points from January to October, when receiving new data for November, it may be beneficial to retrain from February to November rather than from January to November.


Whether training a new model on the entire dataset or implementing continual learning, the old version should remain in production until the new model has been evaluated and proven to outperform the current model, allowing for continuous model uptime.
Alternatively, stateful training can be implemented, allowing the model weights to be updated with the new data only while maintaining the patterns learned from the previous entire data set training.



4. During the delivery of the churn prediction project, you will need to provide progress updates on model development. How would you seek to validate the model performance from a development perspective, and how would you use these results to inform wider non-technical stakeholders?



a. Model performance can be validated throughout development by undertaking cross-validation on the data. This splits the training data into *n* sets; the model is then trained on *n-1* of these sets and evaluated on the remaining hold-out data. Usually this is performed a number of times, and an average model score is produced. By averaging the scores from several data splits, the inherent randomness associated with ML algorithms is reduced, and confidence in the score increases. Finally, a separate portion of the data, known as a test set, should be put to one side during model development and only used at the end of training to gather an appreciation of how the model will perform in real life.



For communication of development to non-technical stakeholders, choice of performance metrics is key. For example, using visual aids such as confusion matrices and precision-recall curves can make it easier to grasp technical concepts.
Feature importance and explainability can also aid in building model confidence. The features driving the model predictions should be communicated to and discussed with the client subject matter experts to understand if they make sense and generally agree with how the model is making decisions, although it should be noted that these do not fully explain the model and are only a guide.
The methodology used and metrics seen throughout development should be communicated in regular, brief updates to the client to assure them of model progress.




3. The client is investing in capturing more data points on their customers with the intention of using this new data in the model at some point in the near future. What recommendations would you make to the client in regards to including these new features? For context, they have limited expertise in machine learning, but do have resource in business analytics and analytics engineering.



a. The client should approach the problem from a human-first perspective, i.e., if a human subject matter expert were going to attempt to predict customer churn, what metrics would they look at? These should be the first features to include in the model.
Further, they should focus on collecting data where they are confident in its quality and availability before undertaking the collection.
Finally, the client should be aware of any legal or privacy concerns with any data gathered.