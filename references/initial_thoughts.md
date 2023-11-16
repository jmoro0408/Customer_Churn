1. Churn prediction = supervised binary classification task (target feature provided)
2. Provide a risk score -> Need to output a probability of likelihood to churn
3. Explainable -> Focus on explainable methods, i.e decision tree and feature importance techniques
4. Need to predict 12 months in advance -> transform monthly features to "months since joining" or similar?
5. Validated for confidence -> cross validation

Questions
1. Do I need to stratify traintest on unique customer ID as well?