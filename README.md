# Amazon_Vine_Analysis

## Purpose

The purpose of this project was to extract, transform and load the Amazon dataset stored in AWS S3 bucket in a RDS database to Google Colab Notebook. Then, use PySpark to perform the analyses of data. 

For this analysis the Home Entertainment Amazon Review dataset was chosen.

Once we extracted the valuable data from the original dataset, the purpose was to determine if there was any bias towards favourable reviews from Vine members in the dataset.


## Results

Upon the criteria, that the total votes must be greater or equal to 20, and helpful_votes/total_votes are 50% or higher, the following vine_table was created:

![vine_table](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/vine_table.png)

* The table contains 24301 reviews with 11005 of 5-star reviews. 


### How many Vine reviews and non-Vine reviews were there?

#### Total Vine reviews

![paid_vine](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/paid_vine.png)


The table has 261 reviews which makes only 1.07 percent from total number of reviews.


#### Total Non-Vine reviews

![unpaid_vine](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/unpaid_vine.png)


The table has 24040 reviews which makes 98.93 percent of total reviews.


### How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?


![5star](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/5star.png)

* The number of 5-star Vine reviews is 106 and non-Vine is 10899.


### What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?


![5star_percentage](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/5star_percentage.png)

* The percentage of 5-star reviews out of the total Vine users' reviews subset is 40.61%
* The percentage of 5-star non-Vine users' reviews is 45.34%


![5star_pct_against_total](https://github.com/AlekseiPronin/Amazon_Vine_Analysis/blob/main/Resources/5star_pct_against_total.png)

* Other percentages to consider are the percentage of Vine 5-star reviews to total 5-star reviews. The Vine 5-star reviews make up 0.96% of the total of all 5-star reviews, while the non-Vine 5-star reviews make up the remaining 99.04%


## Summary

Based on the analysis outcome it cannot be concluded that there is a positive bias in reviews in the Vine program. Only 40.61% of Vine reviewer's gave a five star review  compared to 45.34% of five star reviews given by non Vine reviewers. From this data, we can extrapolate that there is no positive bias and that Vine reviewers seem to be more likely to give a non-positive review to a product than non-Vine users.

Despite this, before drawing a final conclusion, we should consider that the sample of Vine users in current dataset is a fraction of the size of a non-Vine users set. It would be a good idea to collect reviews over time to confirm whether it was a trend within products' niche.


An additional analysis to perform on this data set would be to establish the measures of central tendency (mean, median, mode) on the star_rating variable. This would be useful to see if the data was skewed either way. We could then see what the average star ratings were for Vine and non-Vine reviewers. This would likely to support our summary that Vine reviewers were more likely to give a lower rating.

It would also be useful to compare the mean, median to a mean, median of the population of all Home Entertainment reviews (or even amazon reviews) to determine if the conclusion from this dataset could be reproduced.

After receiving more data, we could run a two sample t-test to determine if the mean and medians of the two sets (vine/non vine) were also statistically significant.
