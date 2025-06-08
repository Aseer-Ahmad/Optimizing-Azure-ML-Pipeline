# Optimizing an ML Pipeline in Azure

## Overview
In this project we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
**In 1-2 sentences, explain the problem statement: e.g "This dataset contains data about... we seek to predict..."**

**In 1-2 sentences, explain the solution: e.g. "The best performing model was a ..."**

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**

**What are the benefits of the parameter sampler you chose?**

**What are the benefits of the early stopping policy you chose?**

## AutoML
AutoML pipeline chose a VotingEnsemble comprised of 10 models. Each model is combined with a scaler or a normalizer. These models are LightGBM, XGBoost, SGD and Logistic regression. 

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**

The hyperparameters of logistic regresison as optimized by HyperDrive are : 
```
Max Iterations : 128
Regularization strength : 0.167
```
This resulted in an accuracy of 0.91527. 

The best accuracy from AutoML comes from the VotingEnsemble with an accuracy of 0.91818. The architecture of this ensemble contains 6 XGBosst, 2 LightGBM, 1 Logistic and 1 SGD. The highest ensemble weights are assigned to XGBosst and LightGBM and the rest of the models have similar weights.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**

## Proof of cluster clean up
**If you did not delete your compute cluster in the code, please complete this section. Otherwise, delete this section.**
**Image of cluster marked for deletion**
