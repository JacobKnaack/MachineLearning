# Methology

## Tensors

What is a tensor? - These are data structures that are used to store large amounts of date for machine learning purposes.  Often time these are linear or 1 dimensional, in which they are referred to as **Vectors**.  If they are multidimensional they are called **Matrices**.

## Linear Regression

What is Linear Regression? - Simply defined as the plotting of large group of data points along a line of "best fit".   Think of this as a quick method of finding the general direction that data is trending.  This is foundational to predictive modelling.
It is best to think of this as a method for modeling a relationship between I**ndependant(predictors / features)** and **Dependant(the outcome)** variables.

Depending on the complexitiy of the outcomes we are trying to predict, we can differentiate between **Single** and **Multiple** linear regression.  The difference being the number of predictors we are trying to account for in predicting our target / outcome.
We can distill this method down to an equation: y = mx + b.  With y being the outcome we want to reach, and x being the predictor(s) we would like to vary:

- **y**: our dependant variable, representing our predicted output.
- **x**: our independent variable, this represents our input or feature variable.
- **m**: the slope of our regression line, represents how much our line changes for each unit increase in x.

## Activation Functions

In order to introduce non-linearity in a Neural Network, activation functions are used to determine weighted sums for range of input data.  Within a complex network, there can be multiple layers of activation functions used.
A neural network can be broken down to a **Network of Nodes** (similar to a tree/directional graph) where the beginning of the graph are the **inputs**, followed by a layers of activation functions, each of which recieve weighted values starting from **all the nodes** in the previous layer.

## Feedforward Neural Networks

These types of neural networks receive inputs values and direct outputs in a single direction (from input to output).  Typically utilized a number of hidden layers (levels) without loops or feedback.  Often seen in image and speech recognition.

## K-Nearest Neighbor

A supervised machine learning algorithm.  Attempts to use similar data points to predict the lable or value of a new data point.

## Training Set vs Validation Set vs Test Set

When testing a models ability to predict outcomes, there is a need to seperate data into discree sets.  The **Training Set** is the data that the algorithm will learn from.  Once the model is trained, the **Validation Set** is used to compute the accuract or error.  Think of this as a data set in which we already now the true label / value for each point, but we are going to pretend like we don't.  Typically we split our data values, using about 80% of our data as training and 20% as validation data.  When data sets are too small to split our values in this manner, we simply perform our analysis **n-times** and **cross-validate**.

Once we are happy with our performance between the Training and Validation sets, we can introduce the **Test Set**: a set of values we partitioned at the beginning as a substitute for the data in the real world.  This will be used for classifcation now that our model has undergone some training.

## Pipelines

A machine learning pipeline represents a set of automated tasks that can be repeated to train or build a machine learning model.   Doing so typically requires a variable number of steps:

1) **Data Ingestion**: this step is collecting data from relavent sources, things like databases, APIs, logs, files, or streaming resrouces.  The goal in this step is to get raw data in a usable form.
2) **Data Cleaning & Preprocessing**: This step is for preparing the data for modeling.  Tasks often include how to handle missing values from the previous step, normalizing or scaling numerical features, removing outlying values, deduplicating, and encoding categorical/qualitative variables.  This step is performed to ensure high data quality and consistency.
3) **Feature Engineering**: Transform the raw data into meaningful signals for the machine learning model.  This step can include actions like creating ratios or aggregates of data values.  Extracting text features that may be important, generating time-based values, reducing data dimensionality.  These are down to improve model performance by giving it better inputs.
4) **Data Splitting**: Dividing the data into 3 seperate sets - training set, validation set, test set.  Once the features have been created, the data is split into sets so that we can assess the model performance.  **Training set** is used to train the model.  **Testing set** is used to evaluate the model's performance after it has been trained.  The **Validation set** is used to fine-tume the model hyperparameters.   The goal is to prevent overfitting and evaluate generalization.
5) **Model Training**: Train one or more models using the prepared **training set**.  This step takes the previous steps data sets and chooses an algorithm to best train the model using the values from the data (random forest, neural network, etc.).  This step also accounts for tuning hyperparameters, and tracks metrics and artifacts for performance.  The goal is to produce a model that learns from patterns from the data.
6) **Model Evaluation**: Once the model is trained it is time to assess performance using the **Validation** and **Testing** data.  The metrics for evaluation depend on the task, things like is the model designed to predict classification, regression, rankning, or clustering to name a few examples.  The goal is to determine whether the model is good enough for predicting.
7) **Model Selection & Optimization**: Choosing a model that best fits your use case and make possible refinements.
8) **Model Packaging**: Deciding how to prepare your model for deployment.  What steps are involved with making your model portable and reproducible.
9) **Deployment**: Put the model into your production environment (REST APIs, Steaming Interfaces, Edge Deployment). The goal here is to make your model availabel to end users or systems.
10) **Monitoring & Maintenance**: Once deployed, it's time to track your models behavior and evaluate for a new iteration of pipeline.  How are the model's predictions?  What is the latency and throughput of the model?  How might we retrain / update features / roll back model behavior.  The goal in this step is to ensure long-term reliability and performance.
