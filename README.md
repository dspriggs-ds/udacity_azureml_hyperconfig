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
a classification algorithm and the following features, "marital", "default", "housing","loan","education","month","day_of_week" to determine poutcome label. Furthermore used the hyperconfig BanditPolicy and Random Sampling to tune the parameters. 


**What are the benefits of the parameter sampler you chose?** RandomParameterSampling parameter sampler supports discrete and continuous hyperparameters with a feature to discard poorly performing runs. 

**What are the benefits of the early stopping policy you chose?**Any run that doesn't fall within the slack factor or slack amount of the evaluation metric with respect to the best performing run will be terminated.

## AutoML
The model choose StandardScalerWrapper, XGBoostRegressor using pdays,cons_price and duration

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**
The AutoML  The AutoML detected data imbalance which warns of an overfit of the model. Looking at the runtime for both pipleines, the AutoML took nearly 30 minutes while the Hyperdrive pipline had an elapsed time of ~8 minutes. The reason for this is AutoML is testing multiple algorithms. The Hyperdrive run utilized a separate train.py file to construct the modelling task as opposed to the AutoML which incapulated the model constructing task.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?** For the hyperdrive model refine the features(adding credit rating and removing month and day_of_week to increase the accuracy or change the parameter sampling from Random to Grid sampling. Use AutoML as it eases the process of constructing Models.


