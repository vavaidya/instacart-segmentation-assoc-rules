# instacart-segmentation-assoc-rules
![Instacart](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Instacart_Img.jpg)
## INTRODUCTION
Instacart, a grocery ordering and delivery app, is one of my favorite tech platforms. As a graduate student with a busy academic schedule, I simply don’t have the time to do grocery shopping. Instacart aims to make it easy to do the shopping online with the touch of a button.
Back in 2017, the company announced its first public dataset release, which is anonymized and contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. 

## PROBLEM TO SOLVE
The task at hand for Instacart is two fold.
1. Customer Profiling - Understanding the different mix of your customers is the key to any successful business. What are the different customer segments? How do their behaviour patterns differ from each other? 
2. Customer Targetting - Which segments to target to maximise profitability?
3. Product Recommendations - Once you've identified your target customers, what products to recommend?

## APPROACH AND CONCEPTS
* **Data merging and data matrix creation** - Joined multiple tables to get final dataframe at a customer level with all individual product aisles as columns and values under those columns represeting the number of times customer bought from those aisles
* **PCA** - Reduced data across 134 columns to 6 principal components explaining 51% of the original variance
* **K-means clustering** - Used pc's to cluster segments into 3 distinct clusters backed by business intution and elbow plot
* **Association based Recommender System 1** - Implemented the apriori algorithm using python generator functions, setting min support to 0.01 and filtering for lift values more than 10
* **Recommender System 2** - Created a heuristic recommendation based on a products repeat ordering frequency from the ideal customer segment. Suggesting such products to target customers buying products with less repetition

## RESULTS
* Target customers make up to 81% of the customer population and buy 3 times less often with half the basket size of the ideal customer
* Recommender System 1 - Suggested complimentary products based on lift scores. Limitation - over 31% of transactions were coming from 4 aisles only namely Fresh Fruits, Fresh Vegetables, Packed Veg and Fruits and Yogurt

## LEARNINGS
* Unlike in toy examples, you'd rarely ever be able to capture about 90% variance of the high dimensional data in 4-5 components. Need to make sound judgement on how many to keep, scree plot helps, but still only an approximation
* Number of clusters to choose is anybody's guess. There is no right or wrong answer. What is important is to keep the business context in mind and relate it back to the cluster attributes.
* Apriori algorithm is computationally expensive and python generator functions provide a neat trick to avoid memory and computation overload

## REPOSITORY DETAILS
Access -
1. [Final Presentation - Summary of Approach and Results](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Instacart%20-%20Customer%20Segmentation%20%26%20Association%20Rule%20Mining.pdf)
2. [EDA](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Instacart_EDA.ipynb)
3. [PCA and kmeans](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Customer_Segmentation%20-%20Instacart.ipynb)
4. [Association Rule Mining - Generators](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Association_rule_mining%20-%20Generators.ipynb)
5. [3 Customer Segments](https://github.com/vavaidya/instacart-segmentation-assoc-rules/blob/master/Customer_Segments%20-%20v2%20-%203Clusters.txt)
