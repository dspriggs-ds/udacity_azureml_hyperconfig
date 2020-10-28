# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
This dataset contains data about bank marketing data perspective customer. We see to predict if a contact should receive marketing materials

The best performing model was a StandardScalerWrapper, ExtremeRandomTrees model.

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**
utilizing the dataset https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv used
a classification algorithm to determine poutcome label. Furthermore used the hyperconfig BanditPolicy and Random Sampling to 
tune the parameterss.


**What are the benefits of the parameter sampler you chose?** It provided most variety while being the best performance.

**What are the benefits of the early stopping policy you chose?**Any run that doesn't fall within the slack factor or slack amount of the evaluation metric with respect to the best performing run will be terminated.

## AutoML
The model choose StandardScalerWrapper, XGBoostRegressor using pdays,cons_price and duration

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**
The AutoML had a higher Accuracy than the the SciKit-learn experiment. This could be due to the number of interations by the AutoML.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?** Use AutoML as it eases the process of constructing Models.


