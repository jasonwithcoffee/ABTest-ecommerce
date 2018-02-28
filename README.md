# ABTest-ecommerce
## Table of Contents
Introduction <br>
Part I - Probability <br>
Part II - A/B Test <br>
Part III - Regression

## Introduction
For this project, I analyze the results of an A/B test run by an e-commerce website. My goal is to help the company understand if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.
<br>
The company and the dataset is not real. This is an exercise A/B Test.

## Part I - Probability
By examining our data in ab_data.csv, an individual in the control group has a probability of 0.0016 more likely to convert to the new landing page more than an individual in the treatment group. From this investigation, a 0.0016 probability difference seems too small of a margin to suggest one page leads to more conversions.

## Part II - A/B Test
Hypothesis stated in terms of  poldpold  and  pnewpnew , which are the converted rates for the old and new pages. <br>
![alt text](https://github.com/jasccyang/ABTest-ecommerce/blob/master/AB_hypothesis.png?raw=true) <br>
Null hypothesis: experiment does equally or worse than the control. <br>
Alternative hypothesis: experiment does better than the control. <br> <br>
I used statsmodels.api package to compute a p-value of about 0.9 and a z-score of -1.31. A z-score of -1.31 represents our convert rate of users receiving new pages is 1.31 standard deviations below the mean convert rate. This z-score matches the graph in part j. From the graph, we can see that the red vertical line marking the observed difference is about 1.3 times below the mean. A p-value of 0.9 is much greater than 0.05, which suggests strong evidence for the null hypothesis. Our computed z-scores and p-values suggest strong evidence for the null hypothesis.

## Part III - A Regression Approach
In this part, I applied statsmodel regression to achieve the results that was acheived in the previous A/B Test. <br>
The p-value associated with statsmodel regression is 0.190. The p-values are different because the hypotheses are different. From Part II, the hypotheses were: <br>
Null hypothesis: experiment does equally or worse than the control. <br>
Alternative hypothesis: experiment does better than the control. <br>
In the regression model, the hypotheses are: <br>
Null hypothesis: experiment performs equally to the control. <br>
Alternative hypothesis: experiment performs unequally than the control. <br>
In other words, the regression model marks better and worse performance as significant changes between the control and treatment; whereas, the model in Part II only counts better performance for the treatment group. <br>
Both the regression model and A/B Test model have p-values greater than 0.05, which suggest strong evidence for the null hypothesis.

## Files
ab_data.csv: A/B test data <br>
Analyze_ab_test_results_notebook.ipynb: Jupyter notebook for investigation <br>
countries.csv: regional data for A/B test
