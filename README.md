# Statistical-Analysis-on-Drug-trail-to-reduce-recovery-time-after-Surgery
1
STATISTICAL REPORT FOR DRUG TRIAL 
Drug company named Developo is producing a new drug called Vunder to reduce the recovery time 
for patients after undergoing a surgery. There is an existing drug in the market called Vunder given to 
the patients after surgery. The drug company Developo wishes to carry out certain analysis to support 
his clam that Vunder can be an improvement of Xanadu for the recovery time of patient after surgery.
This report has been made to perform analysis for certain tasks given by the company. 
Developo has provided all the necessary data needed to perform the analysis of the task. The data 
consist of 7 variables (Recovery time, sex, age, height(cm), weight(kg),smoker, hospital ) and 172 
observation. We are also provided with a sample dataset for our population which consist of the 
recovery time for patients who ever involved in the trial of Vunder at Atesta hospital.



PART 1
There is already an existing drug in the market named Xanadu (existing drug). Xanadu (existing drug)
is currently prescribed to the patient to reduce the recovery time after surgery. The recovery time 
of Xanadu (existing drug) follows a normal distribution with mean of 122 hours and standard 
deviation of 24 hours.
Early trial of Developo shows that the mean recovery time for patient after taking Vunder (new 
drug) is 113 hours. As this is analysed from an early trial this mean is independent of the dataset 
that we will be using in the clinical trial.



TASK 1
Calculate the sample size required to reject the null hypothesis in favour of the alternative 
hypothesis with the given level of significance and power.
The objective of this task is to determine the correct sample size ānā for our population. While 
conducting a study we always consider a sample of the population rather than considering the entire 
population. In most cases, a population can be too large to collect accurate data and cannot be 
practically possible. Samples offer a representation of the whole population if sampled correctly. It is 
important to identify the correct sample size before sampling the population as it may affect the result 
of the analysis. There are various factors that we should consider while determining the sample size. 
In case of sample size calculation, we need to consider the Type I and Type II errors. 
Type I ā We reject the null hypothesis, even if it is true.
Type I error is also known as significance level (Ī±). Lower value of Ī± makes it hard to reject the null 
hypothesis, so choosing a lower value can reduce the probability of having a Type I error. Ideally, in 
case of clinical trials we always consider Ī± to be 5%.
Type II -We reject the alternative hypothesis, even if it is true. 
Type II error is related to power of the test. Power of the test is one minus the probability of Type II 
error (P= 1- Ī²). The smaller the probability of Type II error, more powerful the test. Power is the 
probability of rejecting the null hypothesis when it is false.
As the sample size increases, the errors are in control.



Letās define the null hypothesis and alternative hypothesis
š»0 = šāš šššš ššššš£ššš¦ š”ššš ššš šššššš¢ šš  122.
š»š = šāš šššš ššššš£ššš¦ š”ššš ššš šš¢šššš šš  113.

where, 
n - Sample size
Āµ0 - Mean recovery time for Xanadu (existing drug). 
Āµ1 - Mean recovery time for Vunder (new drug). 
Ļ ā Standard deviation for recovery time.


ā¢ If there is more variability in the observations, we need a larger sample size.
ā¢ Ideally, Ī± and Ī² should be as small as possible. So š§1āš¼ will be greater than zero and š§š½ will be 
less than 0. In this case we will get a large value for (š§1āš¼ ā š§š½). Smaller errors need large 
sample size.
For the sample size of 51, we get š§1āš¼ as 1.6448 and š§š½ as -1.036. So (š§1āš¼ ā š§š½) will be 2.681. 
Substituting these values in the above equation (1) we get the sample size as 51.113.
We are given that the standard deviation is 24 hours, significance level is 5% and power is 85%. So Ī± 
is 0.05 and power is 0.85. We calculate the sample size using the below mentioned formula in R. We 
use the āqnorm ()ā function in R which gives an area and finds the boundary value which determines 
that area. We get 51.12 sample size using R.
((qnorm(1-alpha)-qnorm(1-power)) *sigma/mu)^2
Where mu= Āµ0 ā Āµ1.



CONCLUSION
The sample size for the population is 51. So, 51 values from the population can be sampled for the 
study. Sample size of 51 is large enough to control the Type I and Type II errors.




PART 2
A trail of Vunder (new drug) drug was conducted in the hospital Atesta. 80 patients were involved 
in this trial. Here, the number of patients involved is independent of the sample size that we 
calculated in the above task. 
Let šš be the recovery time for patient.

TASK 2
Given the above data, lets construct a 99% confidence interval for Āµ.
The objective of the study is to determine whether the recovery time of patient who took the Vunder 
(new drug) drug is less than that of the patient who took the Xanadu(existing drug) drug. Letās define 
our Null hypothesis and alternative hypothesis. 


š»0 = šāš šššš ššššš£ššš¦ š”ššš ššš šš¢šššš šš  š ššš šš  š”āšš” šš šššššš¢.
š»š = šāš šššš ššššš£ššš¦ š”ššš ššš šš¢šššš šš  ššš š  š”āšš š”āšš” šš šššššš¢.
Construct a 99% confidence interval manually.
For the sample, the sum of recovery time which is 9688 and sum of the squares of the sum of recovery 
time which is 1227382 is given. Letās used this data to calculate the best estimate of the recovery time 
required for patients.
Let X denote the recovery time for patients. X is a continuous random variable which takes values on 
[0, ā).


Letās calculate the 99% confidence interval for Āµ=E[X].
1. Identify the best guess.
Since the true population mean is unknow we calculate a best estimate of the true population mean 
using the sample set. 

The sample mean for n=80 using the above equation is 121.1 hours. We can say that the sample mean 
can be equal to true population mean. But since it is an estimate, it cannot be exactly same as true 
population mean. The sample mean value of 121.1 hours is our best guess. But since this is just an 
estimate there can be uncertainty. Uncertainty is the quantitative error that occurs in the data. While 
performing an analysis it is important to acknowledge the uncertainty present.


2. Evaluate uncertainty about the guess. 
Letās determine the uncertainty in our best estimate for true population mean i.e., sample mean. 
Variability can be used to determine the uncertainty. Sample variance can be used to calculate the 
uncertainty of the estimate. Variance defines the range of estimate for sample mean. It gives a 
measure of amount of variability in the recovery time of patients. 


Substituting n=80, in the above equation (3), we computed sample variance to be 685.63 hours which 
is equal to 26.182 hours. Hence the standard deviation for the above sample variance is 26.18 hours.
3. Construct an interval such that there is probability p that the interval contains true value.
We can construct the interval by using either normal distribution or T-distribution. T- distribution has 
a greater chance for extreme values than the normal distribution as it has heavier tail. Tail heaviness 
is determined by the degree of freedom, with smaller values having a heavier tail.



Let T ~ š”79. 
Then P (-2.6395 < T <2.6395) = 0.99
We got the value 2.6395 using the t score table for 79 degree of freedom and 0.01 Ī±(2 tail ).

Where šĢ = 121.1 , š = 26.18 ššš š = 80.
Since Āµ is unknown, after rearranging the above equation we get 
121.1 - 2.6395 (2.918) < Āµ < 121.1 + 2.6395 (2.918) 
113.398 < Āµ < 128.802
We get (113.398,128.802) as 99% confidence interval for Āµ. 


Construct a 99% confidence interval using R.
To test the hypothesis that the Vunder (new drug) drug and Xanadu(existing drug) drug were 
associated with statistically significant different mean recovery time for patient who were given the 
drug after surgery, letās perform a t-test.


For this study we have considered the sample size of 80 where ānā represents the sample size to 
estimate the true population. This sample size is independent of the one we calculated in the above 
task. Using t.test() function in R we can calculate the confidence interval by setting the data and 
confidence interval parameters.


We get (113.3728,128.8272) as 99% confidence interval for Āµ.
The result by manually calculating the confidence interval is same as that of above R output.



CONCLUSION
Thus we can say that (113.398, 128.802) is a 99% confidence interval for Āµ. The 99% confidence 
interval will contain the true value of Āµ. As the sample size n increases, variability decreases and thus 
we get a better estimate.
Does the data from hospital Atesta, support Developoās claim that Vunder (new drug) is an 
improvement on Xanadu (existing drug)?
The p-value for the t-test in 0.79 which is greater than the significance level of 0.05. As the p-value is 
greater, we do not reject the null hypothesis. Thus the data from hospital Atesta doesnāt support 
Developoās claim that Vunder (new drug) is an improvement of Xanadu (existing drug).



PART 3
The performance of Vunder (new drug) could depend upon a wide range of covariates. Across m
hospitals M patients were given Vunder (new drug) and the response šš
(recovery time) for patient 
i was recorded along with covariate information:
ā¢ Age (in years)
ā¢ Sex (male=1/female=0)
ā¢ Weight(kg)
ā¢ Height (cm)
ā¢ Smoker (yes=1/no=0)
ā¢ Hospital (coded 1, 2, . . ., m)


TASK 3
Create a covariate BMI. The BMI of a patient is given by (weight in kg)/ (height in m) ^2 . There are 
four main categories of BMI underweight (< 18.5), healthy (18.5 ā 25), overweight (25 ā 30) and 
obese (> 30). Is the BMI category of a patient receiving Vunder (new drug) independent of hospital?
Letās define our null hypothesis and alternative hypothesis.
š»0 = šāš šµšš¼ šš ššš”šššš” šššššš£ššš šš¢šššš šš  ššššššššššš” šš š”āš š»šš ššš”šš.
š»š = šāš šµšš¼ šš ššš”šššš” šššššš£ššš šš¢šššš šš  ššššššššš” šš š”āš š»šš ššš”šš.
Test of independence using R.
First, we convert the āheight in cmā to āheight in mā for calculating BMI. We calculate BMI for the data
using āweight in kgā and āheight in mā.


We calculate the table of observed frequencies using the table () function in R.

Use qchiq () function in R and specify the 
desired area in tail and degree of freedom. We got 16.92 as an output of qchiq (1-0.05,9).

To calculate the test statistics, we use the chisq.test () function in R and pass the contingency table as 
a parameter. We get 14.812 with degree of freedom 9 and p-value of 0.09624.
Manual calculation for test of independence.

 
Degree of freedom (v) = (Number of rows -1) x (Number of columns -1).

CONCLUSION
Using R, the p-value 0.09624 is greater than the significance level of 0.05. Also, for the manual 
calculation as šššš 2 šš  ššš š  š”āšš Ļ9,0.052 and it does not satisfy the condition of šššš 2 ā„ ĻĪ½,Ī±2,we do not 
reject the null hypothesis. Hence, we conclude that the BMI of patient who received Vunder (new 
drug) doesnāt depend on the hospital they have been admitted to.


TASK 4
Find the most appropriate linear regression model for predicting the recovery time after surgery, y, 
in terms of the covariates provided, including bmi.
Hint: Check that categorical variables are correctly coded in your data.
A Multiple linear egression model is of the form
š¦š = š½0 + š½1š„1š + š½2š„2š + š½3š„3š+. . . . . +š½šš„šš + šš

We make a few assumptions when fitting a multiple linear model:
ā¢ Independence: Each observation in the dataset is independent of each other.
ā¢ Linearity: The relationship between x and y is a straight line.
ā¢ Normal errors: The residuals should have a š(0, š2) distribution.
ā¢ Homogeneity: The variance of the residuals should stay constant.

Letās plot a histogram for residual to check if the residuals are normally distributed.

The Histogram shows that the residuals are normally distributed with mean approximately 0.
We can further check our assumptions by plotting the fitted values against the residuals. To do this in 
R we use the plot () function. We draw a horizontal line at 0 residual to check how the data points are 
scattered.


The fitted values vs residual plot appears to have most values around 0 and therefore it appears that 
the assumptions are met for us to use a linear model for the data.
We will use R to create a multiple regression model. 
We can fit a multiple linear model by using ālm ()ā command. We pass the dependent variable and the 
independent variables to the ālm ()ā command.

From the above summary statistic we can say that smoker has a significant effect on the recovery time
as compared with the other covariates. We choose the parameters to minimise the residual sum of 
square (RSS).The more parameters in the model the lower the RSS. However, the more the parameters 
in the model the less easy it is to interpret. One way to achieve this is to use the Akaike Information 
Criterion (AIC). We choose the model with the lowest AIC.
AIC=2Ćnumber of covariates + n(log(2Ļ) +log(RSS/n)+1) (9)
where, L is the likelihood.

There are a lot of models we can create as we have 9 covariates. Calculating the AIC for each model is 
time consuming. In R, we have a function called āstep ()ā that considers the full model and tries to 
remove each covariate one by one. It removes the covariate which causes the biggest decrease in the 
AIC value till the step it finds a covariate which when removed increases the AIC value. The step 
function considers all covariates in the start with AIC 769.33. The function removes the covariates till 
AIC value becomes 760.73. After this step on removal of any covariate, the AIC value increases. 


CONCLUSION
We got our best fitted model which is dependent on two covariates sex and smoker.
So, our multiple linear regression model has intercept of 107.94 with -1.99 as slope of sex and 17.55 
as slope of smoker.
ššššš£ššš¦.š”ššš = 107.94 ā 1.99 š šš„ + 17.55 š ššššš. 
Use your model to predict the recovery time of a 41-year-old female who does not smoke in hospital 
4 given that their height is 155 cm and their weight is 67.7 kg.
We use the āpredict ()ā function to predict the recovery time for the above mentioned covariate values.
The predicted recovery time for 41 years old female who does not smoke and was admitted to hospital 
4, having weight 67.7kg and height 155cm is 107.9427 hours.
