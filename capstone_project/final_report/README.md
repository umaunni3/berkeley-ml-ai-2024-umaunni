This is my capstone project for the Berkeley ML/AI professional certificate course.

# Intro

**Research question:** Can we predict how well a video game will sell based on factors like genre, platform, publisher, and so on?

 

**Data source:** https://www.kaggle.com/datasets/gregorut/videogamesales

 

**Techniques:** Basic linear regression, Lasso, ridge regression, decision tree regression, neural networks



**Expected results:** Identification of key factors that drive video game commercial success. Development of a model to predict global sales performance (in $USD) for a new game based on key attributes such as genre, developer, platform, etc. 

 

**Why this question is important:** The video game development industry has grown significantly over the last few decades, and especially in the years following 2020. Development studios have a clear interest in identifying which types of games are most likely to bring in revenue. Knowing how much revenue a game can be expected to earn can also help studios determine what kind of development budget they should allocate to upcoming games. _This is critical to commercial success for game studios, because developing a game requires a huge investment of resources._ The market for video games is also becoming more and more oversaturated, which makes it especially costly for a studio to release a game that ends up underperforming. Being able to tell which games are worth investing into or not could play a huge role in helping up-and-coming studios (as well as established ones) avoid wasting their limited resources and time, and maximize profit.



# Results

I trained the following models on my dataset: Linear Regression, Ridge Regression, Lasso, Decision Tree Regression, and a neural network (built with Keras). Below is a summary of each model's test and training performance, as well as the best parameters I found for the model (if applicable). The first row of the table contains the baseline MAE, as a reference point. (More info on the baseline computation can be found in the analysis notebook.)

|   | Train MAE   | Test MAE  | Best Parameters  |
|---|---|---|---|
| Baseline | N/A | 0.54956 | N/A |
| Lasso  | 0.53209 | 0.57472  | alpha=0.1  |
| Linear Regression  | 0.44305  | 0.49230  | N/A  |
| Ridge Regression  | 0.44708  | 0.49071  |  alpha=4.0 |
| DT Regression  | 0.35469  | 0.45565  | max_depth=14, min_samples_leaf=3, min_samples_split=4  |
| Neural Net  | 0.3328  | 0.4269  | 1 hidden layer, 2 dropout layers, lr=0.003, ReLU activation  |

Out of all the models, I found that the neural net performed the best, with the decision tree regressor in second place. 



# Important findings
I observed some interesting trends in sales data when analyzing the dataset, which I've captured in some graphs below. Below each graph is a discussion of the findings from that graph, and at the end of this section is a short summary/TLDR of the main findings.
<br>
<br>

![agg_sales_by_genre](https://github.com/user-attachments/assets/20ef3fe3-3849-4469-90a4-2488239d9b8d)

It appears that the most popular genre by far is action, followed by sports and shooter games. These genres (particularly sports) notably have some very popular franchises with annual release schedules (such as NBA2k and FIFA). This characteristic may partially explain why we see such high sales numbers from these genres in particular.
<br>
<br>

![agg_sales_by_publisher](https://github.com/user-attachments/assets/81bdc7ab-dc12-4513-b814-2c50040ef113)

Although this information cannot be directly used by game studios to shift their strategies when choosing which games to develop, it does provide some insight into the market share taken up by different major studios. An interesting thing to note is that Nintendo and Electronic Arts are major purveyors of action games and sports games respectively--which lines up nicely with action and sports being the top two highest-selling game genres.
<br>
<br>

![agg_sales_by_platform](https://github.com/user-attachments/assets/dabc57b1-b4f8-40c0-99fd-d552284e8c6c)

(Note: This dataset was missing a lot of data from 2015 onwards, hence the absence of currently popular consoles like the Nintendo Switch, PS5, and others).

Since it appears that sales are fairly spread out among the different consoles (as well as being spread out across console series--XBox vs Playstation vs Nintendo), I would conclude that developers might improve their odds by aiming to release cross-platform games whenever possible, rather than prioritizing any single console.

Summary:
* Action, sports, and shooter games are top performers
* Developers should aim to release cross-platform games when possible 


# Next steps
I think that an important step for improvement in these results would be the incorporation of additional sources of data on games. In particular, it would be useful to have more numerical metrics--possibly things like average playtime, frame rate, number of achievements available to earn in-game, etc. Some of these metrics are available online already (e.g. via [HowLongToBeat](https://howlongtobeat.com/)), and future work could benefit greatly from an investment of time into aggregating these data sources and joining them with the data I worked with in this analysis.

In terms of future model development, that using neural networks for this task is a great pathway to keep exploring. I think it would be interesting to explore NLP techniques for encoding the many text-based features in this data (especially game titles), and see how this impacts the ability of models to reason about what games are like.

Another NLP-related idea worth exploration would be to incorporate game description blurbs into the dataset (sourced from game listings on online retailers, potentially), and see if NLP could help us parse these descriptions and map the appearance of key words or phrases to game sales performance. 
