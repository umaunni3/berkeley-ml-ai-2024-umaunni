This is my capstone project for the Berkeley ML/AI professional certificate course.

# Intro

**Research question:** Can we predict how well a video game will sell based on factors like genre, platform, publisher, and so on?

 

**Data source:** https://www.kaggle.com/datasets/gregorut/videogamesales

 

**Techniques:** Basic linear regression, Lasso, ridge regression, decision tree regression, neural networks



**Expected results:** Identifying key factors that drive video game commercial success, and possibly variations in these factors when looking at different markets  (US, JP, etc). Development of a model to predict global sales performance (in $USD) for a new game based on key attributes such as genre, developer, platform, etc. 

 

**Why this question is important:** The video game development industry has grown significantly over the last few decades, and especially in the years following 2020. Development studios have a clear interest in identifying which types of games are most likely to bring in revenue. Knowing how much revenue a game can be expected to earn can also help studios determine what kind of development budget they should allocate to upcoming games. _This is critical to commercial success for game studios, because developing a game requires a huge investment of resources._ The market for video games is also becoming more and more oversaturated, which makes it especially costly for a studio to release a game that ends up underperforming. Being able to tell which games are worth investing into or not could play a huge role in helping up-and-coming studios (as well as established ones) avoid wasting their limited resources and time, and maximize profit.



# Results

I trained the following models on my dataset: Linear Regression, Ridge Regression, Lasso, Decision Tree Regression, and a neural network (built with Keras). Below is a summary of each model's test and training performance, as well as the best parameters I found for the model.

|   | Train MAE   | Test MAE  | Best Parameters  |
|---|---|---|---|
| Linear Regression  | 0.44305  | 0.49230  | N/A  |
| Lasso  | 0.53209 | 0.57472  | alpha=0.1  |
| Ridge Regression  | 0.44708  | 0.49071  |  alpha=4.0 |
| DT Regression  | 0.35469  | 0.45565  | max_depth=14, min_samples_leaf=3, min_samples_split=4  |
| Neural Net  | 0.3328  | 0.4269  | 1 hidden layer, 2 dropout layers, lr=0.003, relu activation  |

Out of all the models, I found that the neural net performed the best, with the decision tree regressor in second place. All of the models (except Lasso) beat the baseline MAE of 0.54956 (see notebook for how this baseline was established).
