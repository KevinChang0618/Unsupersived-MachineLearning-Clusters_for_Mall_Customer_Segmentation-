# Project Goal
This project tries to present how to <b>cluster</b> customers and help company to make special discount for different targets. 
In order to gain profits, company should set different coupon for different customers because every customers are individual and unique. However, customizing everyone is difficult
to reach so we can create some clusters to divide whole customers. We separate people into same group with similar traits so that we can satisfy most of people
with implementing strategies for different clusters.

# Method
I use <b>K-Means</b> and <b>Hierarchical</b> Clustering to demonstrate.  

<b> Data Preprocessing</b>  

At first, I plot scatters to understand each variables correlation. We can see that gender doesn't have any relation to segmenting customers, so I drop it.  
![1](https://user-images.githubusercontent.com/67025904/134706737-8d0f6e59-ce7e-45dc-a794-12a236bd7043.jpg)

<b>Modeling</b>  

- Kmeans  
Use <b>'KMeans()'</b> to fit data and create 1 to 10 clusters. Then, I plot the number of cluster against to WCSS(Within-Cluster Sum of Square) and use elbow method to check which cluster have siginificant change or fall gap. That cluster number might be best cluster. According to graph, I decide 3 and 5 to do further step.  
![2](https://user-images.githubusercontent.com/67025904/137165465-50679e6d-b2d9-4b79-882e-72b0d2aaa65b.jpg)

In 3 clusters graph, it is not very well because we can see left up, left down, and middle seems can be divide to three different groups.  
![3](https://user-images.githubusercontent.com/67025904/134712186-0fdce8cc-0f20-41f4-a6bf-4daec303d8c6.jpg)

In 5 clusters graph, it is better than 3 clusters because we can see five different groups were divided perfectly.  
![4](https://user-images.githubusercontent.com/67025904/134712632-e575e3b7-4736-4ea2-85cc-81c3ceebf569.jpg)

Therefore, I would choose 5 clusters to divide our data. However, it is unsupervised method, so it is hard to tell which one is the best. It is dependent on your demand and issues on that momnent.

- Hierarchical Clustering  
Also, we can use hierarchical plot to show our clusters. In hierarchical clustering, each leaves respensent each observations. Not like decision tree started from root, hierarchical clustering start from leaf. Similar data points would be gather in same group.  
We calculate each data points distance and start to fit hierarchical model.  
(Linkage: Which linkage criterion to use(Complete and average). The linkage criterion determines which distance to use between sets of observation. The algorithm will merge the pairs of cluster that minimize this criterion.)  

Linkage: Complete  
![complete](https://user-images.githubusercontent.com/67025904/134714568-40059a0f-ecd4-43f6-8ff7-dfd022f6564a.png)

Linkage: Average  
![average](https://user-images.githubusercontent.com/67025904/134714770-960de2ed-144f-4b18-9e93-9b24257d7c8e.png)

# Conclusion
In kmeans graph, we can easier to prepare our strategies because we have X-axis(AnnualIncome) and Y-axis(SpendingScore) to help us understand each groups' characteristics. On the other hand, in hierarchical graph, we can easier to find which data points are in same group because we can see the data points on the leaves.  

In short brief for the project goal, five clusters is the best and if the company want to create more profits, company can set the strategies as follow.  
1. For the group in right up, they have high annualincome and high spendingscore so company can give them little gift after they buy products. Because they already have high ability to purchase, company just need to keep them.  
2. For the group in right low, they have high annualincome but high spendingscore so company may send a survey to understand why they don't like to purchase in store. And fix the problems base on their survey.  
3. For the group in the middle, they have middle annualincome and spendingscore so company can send them some coupons to stimulate their buying.  
4. For the group in the left up, they have low annualincome and high spendingscore so company can give some discount to them to keep their customer loyalty.  
5. For the group in the left low, they have low annualincome and low spendingscore. Since we can't change their income, company can give them stronger discount such as buy one get one free or 60% off to attract them.  

# Resource
Data is from Kaggle: Popular Unsupervised Clustering Algorithms
