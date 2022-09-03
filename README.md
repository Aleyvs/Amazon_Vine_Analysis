# Amazon_Vine_Analysis


## Overview of the analysis

During this project we will be analyzing Amazon reviews written by members of a paid Amazon program called Vine. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

For this project we received access to 50 different datasets, out of these we selected one and used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we used PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in our dataset. 


## Results

The dataset we selected is the Digital Video Games Dataset.  Using PySpark and Amason AWS RDS the results were the following:

- To start, a filter for the products that recieved more than 20 reviews was made, this to make the list more relevant as we are looking at reviews.
- Form this DataSet we filtered to see only the reviews marked as 'helpful_reviews' are more than the 50% of the reviews received.
- From this filtered DataSet we divided by reviews done by users with Vine and users without Vine, the results here were surprising as all the reviews provided were without Vine. 
- Results form the previous filter tell us that all 5 star reviews provided are from users without Vine. 
    - 5-star Vine reiviews = 0
    - 5-star non-Vine reviews = 631 votes
    - % Vine 5-star reviews = 0
    - % non-Vine 5-star reviews = 100%


## Summary: 

As we can see there is zero bias towards people using Vine, since there is none. So for an extra analysis I decided too see if the filtered DataSet on step 2 how many have a verified purchase and of those what is the percent of 5 Star reviews.

![image](/Resources/image.png)

As we can see above, out of the 1685 reviews 830 have a verified purchase, and out of those only 336 actually give a 5 star review. That sums up to 40%. But looking deeper into it and getting the percentages of all 4,3,2 and 1 star reviews. We noticed that out of the remaining 60%, 28% were 1 star reviews.

![image2](/Resources/image2.png)

So we can safely deduce that people not reviewing through Vine are providing honest reviews. Unless we go deeper and search for the actual words used on the 1 star reviews, analyse if the rating is provided because of the actual product or something else.
