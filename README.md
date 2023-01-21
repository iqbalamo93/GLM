# GLM" Generalised Linear Models

This is one stop high level overview of GLMs

## Part 1: GENERALISED LINEAR  MODEL

Difference between  GLM AND Linear regression 
| No |  Linear Regression  | GLM |
|:-----:|:--------:|:------:|
| Inception   |  1809: By Gauss  | 1972: Nelder & Wedderburn  |
| Observations   | Y's or target observations are independent of each other. |The data  are independently distributed, i.e., cases are independent|
||Observations are from normal distribution Yi~N(µ,σ²)|Y's are from any exponential family distribution|
||Model is linear in nature|link function is used to get Y.A GLM does NOT assume a linear relationship between the response variable and the explanatory variables, but it does assume a linear relationship between the transformed expected response in terms of the link function and the explanatory variables; e.g., for binary logistic regression|
|Errors/Residuals|normally distributed|Errors need to be independent but NOT normally distributed.|
|Other| Assumes linear relationship betweeb Y and X||
|| Works better with continous response varaibles| Can also model discreate|
||![image](https://user-images.githubusercontent.com/32023419/213543774-67e5fa77-f948-46ab-b840-6af11edff039.png)| ![image](https://user-images.githubusercontent.com/32023419/213536545-d0d014d6-535d-4923-a529-e225d4ba28ed.png) |

> linear model/s is a special case of a generalized linear model (GLM).As, Normal distribution is a member of exponential family.

## Poisson Distribution
![image](https://user-images.githubusercontent.com/32023419/213757298-50bee756-b7b6-460e-a702-9e41dfca379c.png)


* For x = 0,1,2... inf .Discrete in nature.
* 1 parameter distribution : __λ__
* Bounded by 0 and ∞
* Events are random and Independent

`The number of events occurring in a given unit interval of time (read λ as average) is modeled by a Poisson distribution, and the time between the occurrence of each event follows an exponential distribution`

Assumptions:
* Rate at which event occurs is constant, λ doesn't change wrt to time intervals.
* Events are indeoendent 

### GLM are used for Poisson Regression

> `Requirements with performing with R`
> * Y to be discreate in nature
> * Define area and time
> * coefficients of the Poisson GLM are on the log scale
> * Non constant sample area or time (e.g., trees km<sup>-1</sup>)
> * Mean >30 (need another tool beside poisson)

#### Comparing linear and Poisson regression
Consider, below two outputs from fitting glm(Poisson) and glm(Gaussian) on discretae data.

![image](https://user-images.githubusercontent.com/32023419/213831264-0bd40167-5085-47f9-bf51-582ed4515bd5.png)

![image](https://user-images.githubusercontent.com/32023419/213831285-2c934dee-038d-46bc-92be-01d6d2e2c773.png)

Note when fitting a model with poission `we get feature's p value<0.05` which is significant i.e given a model our features were able to get the relation between
dependent and independent vialable. NOTE: p-value of features should be read w.r.t. to mode.

#### Poisson link
The Poisson link function. An intercept only equation might be *y* ~ Poisson(β) . We can convert β which is on link scale to raw data scale by expontiating it

### GLM for Logistic Regression

![image](https://user-images.githubusercontent.com/32023419/213840641-3a1222d6-4c7b-45d3-9f83-fa12513a719b.png)

* family: Binomial

The Logit function takes probabilities, which are bounded by zero and one, and transforms or links the probability to real numbers from negative to positive infiniity 

#### Bernoulli Distribution V/S Binomial Distribution
`Bernolli`
* Models a __single event__
* Expected pobability
  - *K* Outcomes: {0,1 usually
  - with *P* probabilities
  - ![image](https://user-images.githubusercontent.com/32023419/213881749-4a655c0f-144c-4155-8eaf-896836a5ccba.png)

`Binomial`
* Modells __N__ Bernoulli events.
* Expected probability 
  - *n* trials
  - *k* favorable outcomes
  - with *p* probability
  - ![image](https://user-images.githubusercontent.com/32023419/213883341-b6085c16-eb39-4a8d-9275-4ef9b5bfe8d0.png)

> I have mentioned Binomial is used as family parameter while fitting GLMs for logistic regression.


#### Probit and Logit

**Pro**bit : **Pro**bability un**it**
> Models may be known as probit analysis, probit regression, or probit model
* Probit assumes a binomial distribution
* The probit has a different link function, __The Probit__ , which is often denoted as inverse phi
*  ![image](https://user-images.githubusercontent.com/32023419/213884734-e115efec-3555-4c0d-8fe6-10a06c8de044.png)
    - ![image](https://user-images.githubusercontent.com/32023419/213884796-486d3d4a-acaa-44da-b327-9fa711f6deb6.png)
![image](https://user-images.githubusercontent.com/32023419/213885152-36a4380f-56dd-4e6b-8143-3845b2ea0339.png)

`Logit has a fatter tails ` that is to say left and right ends of the curve approach their limits a bit slower than a probit. This can make the logit a better at modelling outliers or rare events.

