---
title: How I would improve Amazon’s ratings
layout: post
---

Introduction
============

In a recent conversation about online product ratings, I heard myself make the sweeping statement that “Amazon ratings are somewhat meaningless” (or something overly sweeping like that). In truth, the ratings are not completely meaningless. Millions of people (including myself) use them everyday to help with buying decisions. However, I think they could be much better. Customers look at ratings for a prediction of whether or not they will like a product. Using Amazon’s existing ratings data, I believe it is possible to make a better prediction than the current system.

Harry Potter vs. Twilight
=========================

Say for example, I am trying to decide which of two books to purchase: _Harry Potter and the Sorcerer’s Stone_ or _Twilight_. Amazon’s average star rating for each is close to four stars, with a slightly higher rating for Harry Potter. Glancing at these ratings (and assuming I’ve lived in a cave for the past 13 years), I might conclude that the probability of me liking either book is nearly equal.

![Harry Potter average star rating](/resources/images/harrypotter_stars.jpg "harrypotter_stars")
![Twilight average star rating](/resources/images/twilight_stars.jpg "twilight_stars")

When I click the reviews link, Amazon provides a more detailed breakdown of the data with a histogram depicting the total for each of the five possible ratings. This helps paint a better picture, but there is something strange about the Twilight data. Twilight’s histogram has two peaks: one in five-star ratings and the other in one-star ratings. This is a common occurrence in Amazon ratings. Am I really more likely to give one star than two stars to a book that majority of reviewers loved?  Intuitively, this does not make sense.

![Harry Potter histogram](/resources/images/harrypotter_histogram.jpg "harrypotter_histogram")
![Twilight histogram](/resources/images/twilight_histogram.jpg "twilight_histogram")

My guess, in this case, is that this bimodal distribution results from sample data that is not truly random. I suspect (though I cannot prove it) that customers with passionate feelings about a product are more likely to review it than others. This would explain why so many Amazon products have fewer three-star ratings than any other.

Solution: Gaussian distributions
================================

In an attempt to more accurately predict the likelihood of any given rating for an average customer, I used Amazon’s data to construct a Gaussian distribution for the ratings of each book. For those who have not recently taken a statistics class, these graphs show the probability (y axis) for every possible star-rating (x axis) between one and five. The total colored area under the curve represents 100% of the population (customers). As you can see, these graphs show a significant difference between the ratings of the two books. What I like about Gaussian distributions is that they communicate certainty. A steep pointed curve indicates more certainty in a prediction than a broad and flatter curve. As you can see from these examples, the prediction that you would rate Harry Potter 4-stars or higher is much more certain than for Twilight.

Harry Potter ratings distribution ![Harry Potter gaussian](/resources/images/harrypotter_gaussian.jpg "harrypotter gaussian")

Twilight ratings distribution ![Twilight Gaussian](/resources/images/twilight_gaussian.jpg "twilight gaussian")

I think these graphs are more useful than Amazon’s histograms, but I believe we can boil this information down even further to a single [Rotten Tomatoes](http://www.rottentomatoes.com/ "Rotten Tomatoes") style number representing the overall probability that you will like a product. Let’s say that any rating over three stars is equivalent to _liking_ a product. Using our Gaussian distributions we can sum the probability of all ratings over three stars.

| Book         | Chance you’ll like it   |
| ----         | ----------------------: |
| Harry Potter | 99%                     |
| Twilight     | 76%                     |

<br>
Now that I know there is a 99% chance I will like Harry Potter and only 76% chance I will like Twilight, my purchase decision is made easy.

Conclusion
==========

If my interpretation of the bimodal ratings patterns is correct, applying a bit of probability theory to Amazon’s existing ratings data would give customers a better prediction about whether or not they will like a product. What do you think? Would you prefer this approach over Amazon’s?
