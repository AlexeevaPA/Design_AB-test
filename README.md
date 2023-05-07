# Design_AB-test
![A-B-test](https://user-images.githubusercontent.com/104028421/236695859-03a62ad5-329f-4c69-8d26-81007763e8e4.png)

**Overview**

**Data**

The original dataset is from kaggle.com from a marketing company. Marketing companies want to run successful campaigns, but the market is complex and several options can work. 
So normally they tun A/B tests, that is a randomized experimentation process wherein two or more versions of a variable (web page, page element, banner, etc.) 
are shown to different segments of people at the same time to determine which version leaves the maximum impact and drive business metrics
It contains information:

- Index: Row index

- user id: User ID (unique)

- test group: If "ad" the person saw the advertisement, if "psa" they only saw the public service announcement

- converted: If a person bought the product then True, else is False

- total ads: Amount of ads seen by person

- most ads day: Day that the person saw the biggest amount of ads

- most ads hour: Hour of day that the person saw the biggest amount of ads

**Processing data**

The data were filtered. The highest numbers of maximum watched ads were filtered based on distribution. The lowest numbers such as 1-5 were filtered too, 
because they don't illustrate influential of ads on people.

**A/A-test**

According to the data analysis, it is possible to use 5 features for A/B-test. But, first of all, it is important to check whether these features and their numbers 
(which were given in the task(len of "psa")) are suitable for A/B-test. And for this aim the A/A test will be useful. A/A-test helps us to find out 
the right metrics and estimate the representation of the sample. In our case in data there are already two groups 
without data before the experiment. That is why let's just imitate A/A experiment. We will take just one group and divide it by two and analyze 
the illustrated metrics. 

During A/A-test for each metric the p-value was generated and if the meaning value of p-value is 0.5, it means that data is suitable for A/B-testing.

**A/B-test**

There were a few steps in A/B testing. The first one is checking whether the distribution is normal using the Shapiro method. If it is normal then the 
homogeneity checked using Levene's test. After that, the t-test checked the difference in distributions. If the distribution is not normal then the 
Mann-Whitney U test is used to define the p-value.

**Conclusion**

Based on the majority of metrics the A/B-test illustrates that there is a significant difference in distribution (p-values < 0.05) so it is supposed, 
that adv influences on buying goods.
