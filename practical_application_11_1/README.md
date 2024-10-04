# Practical Application 11.1 - What Drives the Price of a Car?

## Questions I explored
What factors are the most significant drivers of price in the used car market?
Can we use this information to help inform used car dealerships when it comes to acquisition of inventory, or when setting prices for vehicles on the lot? And can we build a model to predict the sale price of a used car based on metrics available to the dealership and consumers?

Analysis notebook link: https://github.com/umaunni3/berkeley-ml-ai-2024-umaunni/blob/main/practical_application_11_1/prompt_II.ipynb

## Findings

After analyzing the dataset of used cars provided, I was able to extract some insights into what features drive used car pricing.

First, I will detail some of the key vehicle attributes that were significant drivers of sale price, as well as less strongly predictive attributes. Then, I will mention the results of modelling used car prices, and provide recommendations to dealerships interested in modeling car prices themselves.

### Key features that drive sale price

#### Car color
Car color can act as a decent indicator of sale price! Specifically, "neutral" car colors like white and black tend to sell for higher prices than cars with more unusual colors, such as green or purple. You can refer to the graph below to see more details. **I would recommend stocking more neutral colored cars when possible**, considering that they sell for more than other types of cars.

![paint_color_price](https://github.com/user-attachments/assets/27153a15-bede-474b-ba72-27fe6877c676)


#### Car condition
The condition of a car is naturally an important factor in sale price, but the relationship is not as clear-cut as one might expect. Cars that are in new or like-new condition sell the best, followed very closely by cars in good condition. Cars in fair condition, as well as salvage-worthy cars, sell very poorly. Based on this analysis, **I think it may not be worth stocking salvage-worthy or 'fair' cars in your dealership, unless they can be acquired for a very cheap sum.**

![condition_price](https://github.com/user-attachments/assets/eaa185a3-2565-4026-aee8-ecaf11062328)

#### Number of cylinders
Cars with 12 cylinders sell for significantly higher sums than any other number of cylinders. Apart from 12-cylinder engines, the differences between other numbers of cylinders are less significant--although one notable finding is that 5-cylinder engines sell the worst of all. This may be because 5 cylinder engines are a rather uncommon configuration, and may be harder to maintain and find parts for. **I would recommend that if you find yourself with a 12-cylinder engine on your lot, make sure to set the price appropriately high**--these can sell for an average of nearly $60k!

![cylinders_price](https://github.com/user-attachments/assets/2894f025-311f-47a5-a86f-b44946cb3ce8)

#### Odometer reading
As a standalone attribute, odometer readings are not an especially strong predictor of sale price for a car. While it is true that low odometer readings generally correlate with higher sale prices, the trend is not particularly strong. My analysis found that **the correlation coefficient between odometer reading and price was only -0.539, which indicates only a moderate correlation between odometer reading and sale price.**

### Modeling used car sale price
In my analysis, I was able to model the sale prices of used cars using a linear regression model. If you're interested in optimizing your pricing for cars on your lot, or predicting how much a car might sell for before acquiring it for your inventory, you might find such a model helpful. I would recommend a linear model, as it is relatively simple and interpretable, while still able to effectively model the intricacies of car pricing. Using a linear model, I was able to **predict used car prices within around $7.8k of the true vehicle price.** See the analysis in the [attached notebook](https://github.com/umaunni3/berkeley-ml-ai-2024-umaunni/blob/main/practical_application_11_1/prompt_II.ipynb) ("Deployment" section) for further details.

## Next steps
For dealerships interested in diving deeper into this type of analysis, I would recommend sourcing more complete and consistent data on cars. For instance, the vehicle model category in this dataset was very inconsistently labeled, which makes it hard for algorithms to reason about what a car model means for the sale price. Having more consistent labeling and/or grouping of related vehicle models in the dataset would likely make a big difference in the accuracy of any prediction models, because vehicle model (even in its current, messy form) was one of the biggest drivers of predicting vehicle price. Any improvements in data quality in that regard would likely be very beneficial.
