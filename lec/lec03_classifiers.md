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

* Why is the gaussian distribution on the top right of page 142 squished? 
* Compare (non-mathematically) how the classification process for LDA with 1 predictor, is the same as the classification process for LDS with 2 predictors. 
* In the top right picture on page 143, what is the differnece between the dotted and solid lines?
* Label each line as `a` (between yellow and green), `b` (between yellow and blue) and `c` (between blue and green). Write out the decision rules in english using these labels. _E.g. if X1 is less than a, and less than c, then classify as green._
* Consider the debt example in the textbook (confusion matrix on top of page 145). Why does LDS do such a poor job of classifying the customers who default? 


#### Breakout group 1


#### Breakout group 2


#### Breakout group 3


#### Breakout group 4




## ISLR Ch 4.4.4 [Quadratic Discriminant Analysis and Naive Bayes](https://www.youtube.com/watch?v=6FiNGTYAOAA)(10:07)

* Why is this called QDA insead of LDA with more X's? What makes it different? 
* Which is the more flexible classifer? LDA or QDA? 
* Why does it matter whether or not we assume that the $K$ classes share a common covariance matrix? Explain this in terms of the bias-variance tradeoff and parameter estimation. 
* When would QDA be more accurate than LDA? 
* What are the take home messages for Figure 4.10 and 4.11? What can you learn from these plots?

#### Breakout group 1


#### Breakout group 2


#### Breakout group 3


#### Breakout group 4
