# <center>AIM</center>

The aim of the project is to explain the Central Limit theorem to interested students of the MSDS program, and demonstrate
the applicability of the theorem through simulations

# Central Limit Theorem

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/CLT_img.png)


The theorem states that the sampling distribution of the sample means follows a normal distribution with a mean equal to the population average and a standard deviation equal to the population standard deviation by the square root of sample size.

The conditions under which the theorem hold are:
  1) The observations drawn from the population must be independent
  2) The parent distribution should have a finite mean and variance
  3) Each observation is randomly selected, and the aggregate sample should be representative of the population
  4) The samples taken should be at least of size 30 and less than 10% of the population



# The Process
 
 Based on user input, we can draw from four population distributions: the normal distribution, uniform distribution, Poisson distribution, and lastly, the binomial distribution. The code outline is as follows:

  1) We take samples from a population distribution and calculate its mean. This is called the sampling mean
  2) We do the above step for many iterations. This results in a distribution of sample means
  3) We visually check if the distribution approaches a normal distribution
  4) We can vary the parameters in step1 and step2 using a slider and obtain different distributions of sample means  



# Function descriptions​

## The population_dist function

We explored the sampling distribution of averages for four different population distributions: the uniform distribution, which models the outcome on a fair sided die, the Poisson distribution, which describes the goals scored in a football game; the Binomial distribution, which represents the number of heads on n tosses of a coin, and lastly the normal distribution which describes the adult male heights in the US.
​
Based on user input, we generate samples from one of the four distributions.
​
## The sampling_dist function  ​

The function takes the whole population data as a parameter. We can tune the function for different sample sizes and the number of sample iterations. 
We first pick some observations from the original population, calculate their mean and repeat this process n times. The distribution of means then decides the number of bins.  Lastly, we pass the output to the plotter function.
​
## The plotter function 

This function is used to visualize the distributions generated. This function takes the sample mean data, the distribution name, and two parameters to set the plot.  If the distribution is discrete, we plot a bar chart. While if it is continuous, we will plot a histogram. Since the mean is approximately normally distributed, we always use the continuous distribution type. 
​
​
# Visualization 
​
Understanding the Central Limit Theorem is not straightforward, hence some visualizations would help with understanding the intuition. As mentioned earlier, you can select among the four distributions listed below:

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Choosing_Distribution.png)

        
You can use the slider to set the population size and then click on the "Create Population" button to initiate the population and plot the frequency distribution histogram for the selected population. The next step is to generate a large number of samples from the chosen population distribution. You can use the "sample size" and "number of samples" sliders to set the size of each sample and the number of samples that need to be generated from the population. Click on the "Create Sampling Distribution" button to plot the sample means for all the sampling distributions.

![alt text](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Sample_Params.png)


# In summary
  1) We choose a non-normal population distribution.
  2) We take repeated samples to get a data set of sampling means 
  3) We visualize the distribution of the sample means using a histogram
    
Population Distribution             |  Sampling Distribution of Sample Means
:-------------------------:|:-------------------------:
![](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/population_dist.png)  |  ![](https://github.com/ashwanirajan/Central-Limit-Theorem-USF-MSDS610/blob/main/Images/Sample_dist.png)


# Installation

## Viola
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
 
