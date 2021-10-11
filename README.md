## <center>AIM</center>

The aim of our project is to explain the Central Limit theorem to the students of the MSDS program and demonstrate the application of the theorem through some simulations of real world examples. We also discuss an interesting use case of the Central Limit Theorem in Linear Regression to explain its application from a data science perspective.

## The Central Limit Theorem

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/CLT_img.png)


The Central Limit Theorem states that given a population distribution, if we take a large number of equally-sized samples form it, the expectation values (means) of all these samples will follow a normal distribution centered close to the population mean. The population distribution could be something like a compilation of the height measurements of all people in the US. In other words, the distribution of the sample means follows a normal distribution with a mean equal to the population mean and a standard deviation equal to the population standard deviation divided by the square root of the sample size.

The conditions under which the theorem hold are:
  1) The observations drawn from the population must be independent
  2) The parent distribution should have a finite mean and variance
  3) Each observation is randomly selected, and the aggregate sample should be representative of the population
  4) The samples taken should be at least of size 30 and less than 10% of the population


## Visualizing the Central Limit Theorem 
​
Since the Central Limit Theorem is not a straightforward concept, some visual demonstrations would help with understanding the intuition better. We have created an interactive demonstration of the Central Limit Theorem for different population distributions. Based on user input, we can draw samples from five population distributions: 

  1) The uniform distribution, which models the outcome on a fair sided die.
  2) The Poisson distribution, which describes the goals scored in a football game.
  3) The Binomial distribution, which represents the number of heads on n tosses of a coin.
  4) The normal distribution which describes the adult male heights in the US.
  5) The exponential distribution, which describes the distribution of wait time between bus arrivals.


![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Choosing_Distribution.png)

You can use the slider to set the population size and then click on the "Create Population" button to initiate the population and plot the frequency distribution histogram for the selected population. The next step is to generate a large number of samples from the chosen population distribution. You can use the "sample size" and "number of samples" sliders to set the size of each sample and the number of samples that need to be generated from the population. Click on the "Create Sampling Distribution" button to plot the sample means for all the sampling distributions.

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Sample_Params.png)
  

## Understanding the Code

Here's an outline of the process:

  1) We take samples from a population distribution and calculate its mean. This is called the sampling mean
  2) We do the above step for many iterations. This results in a distribution of sample means
  3) We visually check if the distribution approaches a normal distribution
  4) We can vary the parameters in step1 and step2 using a slider and obtain different distributions of sample means



### Function descriptions​

#### The population_dist function

This function is used to create the population distribution. Based on user input, we create one of the five different population distributions listed above. The distribution type is taken as input from the radio button and the population size is taken as input from the first slider. It also triggers an in-function call to the plotter function to generate the histogram of the population distribution. We explored the sampling distribution of averages for four different population distributions:
​
Based on user input, we generate samples from one of the five distributions.
​
#### The sampling_dist function  ​

This function takes the whole population data as a parameter, and it generates random samples from the population and stores the sample mean. We can tune the function for different sample sizes and the number of sample iterations (n) using the sliders. We first pick some observations from the original population, calculate their mean and repeat this process n times. The distribution of means then decides the number of bins. Lastly, we pass the output to the plotter function.
​
### The plotter function 

This function is used to visualize the distributions generated. This function takes the sample mean data, the distribution name, and two parameters to set the plot.  If the distribution is discrete, we plot a bar chart. While if it is continuous, we will plot a histogram. Since the mean is approximately normally distributed, we always use the continuous distribution type. 
​

## Applications of the Central Limit theorem

Now that you have a basic knowledge of the Central Limit Theorem, Let's understand an implementation of the Central Limit Theorem in Data Science.

Here is a quote from Dr. David Kleinbaum. 
> "Only extreme departure of distribution of Y from normality yield suspicious results." 

We learned that non-normality is not a critical assumption violation in linear regression, as long as the sample size is large enough. Doesn't that sound familiar? Yes, this is similar to one of the conditions from the Central Limit Theorem.
We will do a simulation based on the model $𝑦=3+5·𝑥$. Our data is generated by adding a random error term 𝜀, which is uniformly distributed. The steps are:
  1) We generate a sample set with 100 observations and fit a linear regression model, which gives a single estimator of the coefficient for x 
  2) We repeat the first step 5000 times, resulting in 5000 estimators of the coefficient of x 
  3) Finally, we plot the histogram of these 5000 numbers and compare it against the normal distribution based on the sample mean and sample variance


The histogram is bell-shaped and symmetric about 5. The theoretical normal distribution seems to 
fit with the histogram.     

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Dist_errors2.png)

In a real hypothesis test situation, we usually use the theoretical distribution under the null hypothesis. For instance, in a regression process with known variance, we calculated the t-statistic, equal to 0.04. Since in the normal distribution N(0, \sigma^2) with a 5% significance level, 0.04 is in the red area, we should reject the null hypotheses at a 5% level of significance.

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Testing.png)

In the situation where the variance is unknown, we usually use sample variance to replace it. The distribution of \beta is at distribution rather than a normal distribution.


## In summary
  1) We choose a non-normal population distribution.
  2) We take repeated samples to get a data set of sampling means 
  3) We visualize the distribution of the sample means using a histogram
    
Population Distribution             |  Sampling Distribution of Sample Means
:-------------------------:|:-------------------------:
![](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/population_dist.png)  |  ![](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Sample_dist.png)


## Installations

### Viola
On your jupyter notebook, run 
```console 
!pip install voila
```

Setup the voila extension to Jupyter notebook using 
```console
!jupyter serverextension enable --sys-prefix voila
```

Restart the Jupyter notebook. you will be able to find the voila extension on the menu bar. 
 ![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/voila.png)
 
Click on it. It will redirect you to a version of your notebook which only shows markdowns and interactive ipython widgets. 
 
