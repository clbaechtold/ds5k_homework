# Final Project Proposal
---

My problem statement is: can I predict the rating score of a beer I am about to drink?  I am going to do so using a database of ~2700 craft beers from CraftCans.com, joined on average ratings scores from RateBeer.com.

My hypothesis is that geography, style, and *beer metrics*, or facts about the beer such as ABV, IBUs, etc. will contribute most to a beer's average rating.  It would be useful if the data lended itself to predicting quality based on the individual brewer- for example, if there are only a dozen or so breweries, there might be clear stratification in quality of beer from these various brewers.  Part of the challenge in the diversification of the craft beer market with the introduction of new, microbreweries, is that such clear stratification does not exist.  While it may be the case that certain breweries' products are much higher quality than their competitors', this does not lend itself to predicting the quality of future beers.  Instead, I plan to use more broadly defined geographic characteristics of the breweries as an input feature.

The goal of incorporating geography in this way is that the model might implicitly capture geographic forces such as:
* access to quality local ingredients
* climate impact on fermentation/brewing process
* maturity of craft brewing market

while still maintaing some flexibility in interpreting new or 'first-seen' brewers.  This should contribute meaningfully to the model's robustness in predicting the quality of future beers. 

