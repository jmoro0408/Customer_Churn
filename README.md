# Customer_Churn

# Folder Structure 

├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.

# Answers to task based questions
## Problem area

- The client wish to detect customer churn up to twelve months from renewal to provide their customer success team enough time to action preventative measures.
* Logistic regression and XGBoost models are fitted with acceptable F1 scores being seen in both models. XGBoost performs well without additional sampling transformations and so is taken forward for model use. 

- The model needs to be able to effectively provide a risk score for customers representing propensity to churn. The client also wishes to understand why a customer has been classed as high/low risk, to guide customer success in the conversations they have with the customer / action they take to mitigate.
* Probabilities are used to assign a risk profile to predictions, if a customer is seen as having over 75% chance of churning they are designated High risk. This target value can be easily adjusted after discussions with the client. 
* Why a customer may churn is approached in the `notebooks/explainability.ipynb` notebook. Here I investigate feature importance of the dataset to gain insights into what is driving the predictions

- The client is also keen to ensure the model is well validated, so they can be confident in the model outputs.
* Model is built using 5x cross validation, and various metrics (F1, precision, recall, ROC_AUC) are collected throughout training. 

# Other Questions
See `/references/question.md`

# Other

## Future work
* Transform each feature according to it's distribution rather than applying a MinMax Scaler to all
* Tune hyperparameters
* Add additional feature highlighting if customer has previously left and has re-joined
* Attempt to use word embeddings for specific categorical features where it makes sense, rather than one-got encoding all
* Convert all working to .py scripts, add functions/classes, and include docstrings and type hints
