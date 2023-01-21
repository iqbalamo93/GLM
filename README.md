# Gemofstats
This is one stop revison of stats

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
Consider a below output from fitting lm nd glm on discretae data.

![image](https://user-images.githubusercontent.com/32023419/213831264-0bd40167-5085-47f9-bf51-582ed4515bd5.png)

![image](https://user-images.githubusercontent.com/32023419/213831285-2c934dee-038d-46bc-92be-01d6d2e2c773.png)



