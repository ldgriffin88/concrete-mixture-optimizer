# concrete-mixture-optimizer
Completed as part of Johns Hopkins applied machine learning coursework. The project used instructor-provided starter infrastructure. The model implementations, analysis, and optimization were completed as part of the coursework.

## Overview

In this experiment, machine learning models are evaluated in order to predict concrete compressive strength and optimize concrete mixture performance. Six regression models are trained and compared using an initial dataset of 425 samples. The best performing model is then used to estimate additional strength values, broadening the dataset to 10,000 points. A generative adversarial network is used to create 40,000 more samples, resulting in a 50,000 point dataset. The best performing model is retrained, feature combinations are evaluated, and the final model is used to predict a mixture that optimizes concrete compressive strength-to-weight ratio, subject to constraints.

## Models

Six regression models were evaluated and compared based on their performance.

Linear Regression: works by minimizing the sum of squared differences between the known outputs in a dataset and the outputs predicted by the model in order to find a best fit relationship for estimating the regression output.

Support Vector Machine: learns how to estimate values by finding a hyperplane that fits closely to the data points. An epsilon value is used to represent a radius around the hyperplane. The data points lying on the radius of the hyperplane, or outside it, serve as the support vectors for the model, contributing error penalties that the model seeks to minimize over the fitting iterations. 

Decision Tree: built by splitting the data based on an input feature and threshold value at each level. The model chooses to split the data points on the feature that makes the output values within each child subset as similar as possible. This selection process is repeated to build out the tree. The leaves of the tree represent the prediction regression output values and each is an average of the output values for the data points contained within that leaf. 

Random Forest: consists of many decision trees that are each constructed using random subsets of the overall dataset and a random subset of features as well. The output from the forest of decision trees is then averaged to get a final output prediction.

Gradient Boosting: builds a sequence of decision trees, with each subsequent tree decreasing the residual prediction errors left by the previously built trees. The predictions from the trees are combined sequentially to produce the final regression output.

K-Nearest Neighbor: makes a prediction by averaging the output values of the k-nearest training data points to the given input features.

## Results

Of the initial models, gradient boosting produced the strongest overall regression performance and was chosen to be trained on the overall set of 50,000 points. The feature combinatory analysis showed that the best performing combination included all 7 input features, although fly ash and coarse aggregate appeared less frequently among the highest-ranked combinations compared to the other inputs. During optimization, the gradient boosting model proved sensitive to initial conditions. Many optimization runs terminated after relatively few iterations. To combat that, numerous random starting conditions were used to increase the optimizer’s chance of finding a good solution. Ultimately, the experiment demonstrated how regression modeling, synthetic data generation, feature analysis, and constrained optimization can be combined to identify a concrete mixture with a high strength-to-weight ratio.

## Repository Contents

FinalProject_LoganGriffin.ipynb: Model training, evaluation, data generation, and optimization workflow

FinalProject_ProgrammingReport.pdf: full project report including visuals, analysis, and results

README.md: project overview
