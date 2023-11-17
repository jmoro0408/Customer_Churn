1. Churn prediction = supervised binary classification task (target feature provided)
2. Provide a risk score -> Need to output a probability of likelihood to churn
3. Explainable -> Focus on explainable methods, i.e decision tree and feature importance techniques
4. Need to predict 12 months in advance -> transform monthly features to "months since joining" or similar?
5. Validated for confidence -> cross validation

Questions
1. Do I need to stratify traintest on unique customer ID as well?


Notes
1. When scaling - look at distribution and apply log where necessary - future work
2. Future work - Use word embeddings instead of OHE for categorical features
3. Future work - Hyperparameter tuning
4. Future work - Featur eenigneer is customer has previously churned 
5. Future Work - Convert all to .py scripts, convert to functions add type hunts docstrings 

Potential Qs:
1. Why normalization over scaling? -> better when distribution is non gaussian
2. Do I need to worry about CV sdplitting due to time component?
3. Why does seting class weights make it even worse?