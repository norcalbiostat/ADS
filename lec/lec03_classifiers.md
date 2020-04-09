---
tags: ADS
robots: noindex, nofollow
---

# Classifiers (ISLR Ch 4)



What are the main take home points from this chapter? 

## ISLR Ch 4.4 [Linear Discriminant Analysis and Bayes Theorem](https://www.youtube.com/watch?v=RfrGiG1Hm3M) (7:12)

#### Breakout group 1 (Irfan & Tanya)

* Discriminant Analysis is  a transformation of the Bayes thoerom which utilizes a "density" for for  each class and integrates a "prior" probability for each class.
* Discriminant analysis equation divides the probability density for class K over the sum over all the classes. 
* Assuming you have the right population model, Bayes is the best you can possibly do.:star:



#### Breakout group 2 (Kaleb & Brandon)

* In Discriminant Analysis, we break up the data into classes/groups and classify based on the density. The higher the density the more likely the value belongs to that group. Based on the density of each class, the point on X in which you change classifications moves (cut line).:star:
 * Parameter estimates are unstable for logistic regression when classes and well separated.
 * When n is small and the predictors are normally distributed, linear discriminant analysis is more stable. :star:
 *  Linear discriminant analysis is popular when we have more than 2 response classes, because it also provides low dimensional views of the data 
 *   Bayes Theorem is used in Discriminant Analysis
    
    
#### Breakout group 3 (Collin & Madeline)

* Discriminant Analysis is better suited than logistic regression for classification of many classes (more than 2)
    * In particular when the classes are well separated discriminant analysis is beneficial to prevent estimates from getting infinitely large:star:


#### Breakout group 4 (Olivia & Kris)
* Discriminant analysis
We model the distribution of X in each class separately, then using Bayes' Theorem (flipping that around) to obtain P(Y|X).

* Using normal distributions for each class leads to linear or quadratic discriminant analysis.
$P(Y=k|X=x) = \frac{\pi_kf_k(x)}{\Sigma\pi_lf_l(x)}$
** where $f_k(x)=P(X=x|Y=k)$ is the density of $X$ in class $k$
* When classes are well separated, logistic regression falls apart because the coefficients aren't made for fully separated classes
* If the sample size is small and the distributions are normal, linear analyses like descriminant analysis are more stable
* By providing low-dimensional views of the data, descriminant analysis is easier to use and more common when there are 2+ response classes




## ISLR Ch 4.4.2 [Univariate Linear Discriminant Analysis](https://www.youtube.com/watch?v=QG0pVJXT6EU) (7:37)



#### Breakout group 1 (Irfan & Tanya)
Disriminant scores are used to determine the largest probability class which wil be assigned to the x value?

Gaussian Density 
* important part that depends on x is in the exponential form
* Going to determine if it will be a linear or quadratic function
* If there are two classes (K=2) then mu,1 and mu,2 will be .5 meaning the equation will be (mu,1 + m,2)/2 :star:
* With real data there is no clean way to find decision boundary.


#### Breakout group 2 (Kaleb & Brandon)

* Uses Gaussian Density Function
![](https://i.imgur.com/Nsq02BU.png)
    * After plugging it into Bayes Theorem, it simplifies into a linear function of x involving the mean, sigma, and the prior.
![](https://i.imgur.com/cX4ReeY.png)


* Assume that all $\sigma_k = \sigma$(are the same)  
* If there are two classes and the prior are the same, the cutoff point can be calculated using $\frac{\mu_1 + \mu_2}{2}$:star:
* Estimate the parameters:
$\pi_k$, $\mu_k$, and $\sigma^2$ when you have data instead of a distribution.
* To estimate the variance, you use the pooled variance estimate which finds the variance of each class and then has a weighted average for all classes.


#### Breakout group 3 (Collin & Madeline)
* Rather than evaluating probabilities you just need to see which class has the largest discriminant score in relation to x. The class with the highest resulting discriminant score is the one that x most likely belongs to. :star:

* With real data we estimate the distribution for our classes and use that for the analysis 

#### Breakout group 4 (Olivia & Kris)
We can combine the Gaussian distribution function with Bayes' theorem to produce p(x)
When we use descriminant functions, we classify the data by finding which p(k) classification function is largest.:star:
Reducing the function further results in a function for descriminant score, which is the simplified classification tool that is used for this analysis.1

* We are altering the forms of $f_k(x)$ giving us different classifiers.
* With normal, but differing $\Sigma_k$ (covariance matrix) in each class we have quadratic discriminant analysis. :star:
* The covariances $\Sigma_k$ are diagonal.
* We may use other densities and throw it into our Bayes' classifier.
* attractive for small $p$ (variables)




## ISLR Ch 4.4.3 [Multivariate Linear Discriminant Analsyis and ROC Curves](https://www.youtube.com/watch?v=X4VDZDp2vqw) (17:42)

1. Why is the gaussian distribution on the top right of page 142 squished? 
2. Compare (non-mathematically) how the classification process for LDA with 1 predictor, is the same as the classification process for LDS with 2 predictors. 
3. In the top right picture on page 143, what is the differnece between the dotted and solid lines?
4. Label each line as `a` (between yellow and green), `b` (between yellow and blue) and `c` (between blue and green). Write out the decision rules in english using these labels. _E.g. if X1 is less than a, and less than c, then classify as green._
5. Consider the debt example in the textbook (confusion matrix on top of page 145). Why does LDS do such a poor job of classifying the customers who default? 


#### Breakout group 1 (Tanya & Irfan)
1. The distribution is squished because the predictors are correlated. Another reason why this could happen is when the predictors have unequal variances.
2. They both are using the bayes classifier to determine the largest "group."
3. The dotted lines represent the Bayes decision boundaries. The solid lines are the LDA decision boundaries. 
4. If X1 is  greater than a and less b, then classify as yellow. If X1 is greater than a and less than b and greater than c classify as blue. If X1 is less than a, and less then c, classify as green.
5. LDS does such a poor job of classifying the customers who default because the initial threshold is too high (.5). Bayes classifier uses a threshold of .5 by default.



#### Breakout group 2 (Olivia & Kaleb) :joy: :joy: :joy:
1. The distribution is squished because the variables are correlated in the graph to the right.
2. They both utilize the Bayes classifier, and we assume the data is pulled from the Gauzian distribution. The only difference is the number of variables that we use to estimate the probabilities of an event belonging to a specific class. 
3. The solid line represents the 95% classification for each class (the LDA decision boundary) and the dashed line represents the Bayes decision boundary. 
4. If $x1$ is less than $b$ and greater than $a$, classify as yellow. If $x1$ is less than $b$ and less than $a$, classify as green. If $x1$ is greater than $a$ and greater than $b$, classify as blue.
5. LDS does a poor job of classifying defaulting customers because LDA is an attempt to approximate the Bayes classifier, which is tuned to minimize misclassifications, irrespective of which class they belong to. 


#### Breakout group 3 (Brandon & Kris)
1. The variables are correlated.

2. Still maintains linear (under normal assumption) relationship for classifying. For 2 predictors there is a boundary line in which you classify based on where the data is in relation to that boundary line. This is the same for 1 predictor when on an axis, classification is based on which side of the boundary line the data point is.

3. The dashed lines are the Bayes decision boundaries. Solid lines are linear discriminant analyis decision boundaries corresponding to observations.

4. If $X_2$ is greater than $a$ and $X_1$ is less than $b$, then classify it as yellow. If $X_2$ is less than $a$ and $X_1$ is less than $c$, then classify it as green. If $X_2$ is less than $b$ and $X_1$ is greater than $c$, then classify it as blue. 

5. Linear discriminant analysis is attempting to estimate the Bayes classifier, which should have the lowest total error rate out of all classifiers (if Normal model assumption holds),it will show the smallest total number of misclassified observations no matter which class the errors come from.




## ISLR Ch 4.4.4 [Quadratic Discriminant Analysis and Naive Bayes](https://www.youtube.com/watch?v=6FiNGTYAOAA)(10:07)

1. Why is this called QDA insead of LDA with more X's? What makes it different and thus, called "quadratic"? 
2. Which is the more flexible classifer? LDA or QDA? 
3. Why does it matter whether or not we assume that the $K$ classes share a common covariance matrix? Explain this in terms of the bias-variance tradeoff and parameter estimation. 
4. When would QDA be more accurate than LDA? 
5. What are the take home messages for Figure 4.10 and 4.11? What can you learn from these plots?


#### Breakout group 1 (Tanya & Olivia)
1. QDA assumes that each class has its own covariance matrix. The quantity x appears as a quadratic function.
2. QDA is the more flexible classifier.
3. The assumption that K classes share a common covariance matrix, such as in LDA's case, causes there to be lower variance. If this assumption is off, then there can be the issue of high bias. QDA is reocmmended if the training set is large, so the variance of the classifier is not a concern.
4. QDA will be more accurate than LDA in cases where LDA's assumption of a shared covariance matrix is badly off.
5. No method consistently dominates the others, but QDA is generally better in situations with boundaries that are moderately non-linear.

#### Breakout group 2 (Kris & Kaleb)
1. QDA assumes that each class has its own covariance matrix, and it assigns observations to class (largest). 
2. The quadratic quality of QDA makes it a more flexible classifier.
3. By sharing a common covariance matrix, we are able to reduce bias among individual classes. However, the trade off to this is that there is a much higher variance 
4. Useful for large amount of variables and variance of the classifier is not too much of a concern. Also useful when its unreasonable to make the assumption of common covariance matrices for your classes.
5. Linear scenarios: error rate smallest range at QDA, logistic, and LDA when data range is smaller. The amount of correlation between the predictors has a direct affect on the performance.

#### Breakout group 3 (Irf & Brandon)
1. QDA assumes that the variances for each class are not the same, which results in no cancellation meaning that there are square terms leftover in the function of the predictors. This results in a quadratic boundary line.
2. QDA is more flexible.
3. If we assume K classes share a common covariance matrix, which lowers variance, and that assumption is "badly off", it can suffer from High bias.
4. QDA is reccomended if the training set is very large, so the variance of the classifier is not a major concern. QDA is also better for when the assumption for an equal covariance matrix is not able to be made.
5. They both have varying levels of error rate, so choosing between QDA and LDA depends on the context of the data. There may be a slight increase in IQR of error rates for non-linear scenarios.

