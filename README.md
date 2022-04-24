# Amazon_Vine_Analysis

## Overview:
In this challenge we are analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.
We pick a review dataset and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we’ll use PySpark to determine if there is any bias toward favorable reviews from Vine members in your dataset. 

For this analysis we picked the watches dataset: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Watches_v1_00.tsv.gz

## Results

### Paid reviews
![paid_reviews](/images/paid_reviews.PNG)

### Unpaid reviews
![unpaid_reviews](/images/unpaid_reviews.PNG)

How many Vine reviews and non-Vine reviews were there?
  - Vine reviews: 47
  - Non-Vine reviews: 8362
  
How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

  - 5-star Vine reviews: 15
  - 5-star non-Vine reviews: 4332
  
What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  
  - 5-star Vine reviews pct: 31.91%
  - 5-star non-Vine reviews pct: 51.81%

## Summary

It appears that paid reviews did not positively bias customer opinions since 5-star reviews were only 32% of total paid reviews. Compare that to 52% for non-paid reviews.

We should check however whether paid reviews resulted in less negative opinions. We can re-run the analysis and filter by 1-star reviews for both paid and non-paid reviews and check whether there is a material difference proportionaly.
