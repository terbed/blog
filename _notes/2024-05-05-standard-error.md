---
title: "Standard Error of the Mean"
tags: statistics
comments: true
---

Let's say we have $$ n $$ random sample of data points $$x_1, x_2, \ldots, x_n$$ from a population with a population mean $$\mu$$ and standard deviation $$\sigma$$. The standard error of the mean is the standard deviation of the sampling distribution's sample mean.   It estimates the standard deviation (error) of the sample mean from the exact population mean.

Formally, we can define the standard error of the mean as:

$$ SEM \equiv \sqrt{Var(\bar{x})} \tag{1} $$

where $$ \bar{x} $$ is the sample mean and $$ Var(\bar{x}) $$ is the variance of the sample mean.

Let's derive the formula for the standard error of the mean, with introducing the total sum of random sample data points:

$$ T = \sum_{i=1}^{n} x_i \tag{2} $$

where $$ T $$ is the total sum of the random sample data points, which is a random variable itself. It's variance can be calculated utilizing the Bienaymé formula, which states that the variance of the sum of random variables is the sum of the variances of the individual random variables, given that they are independent:

$$ Var(T) = \sum_{i=1}^{n} Var(x_i) = n\sigma^2 \tag{3} $$

as each $$ x_i $$ is an independent random sample exhibiting the population variance $$ \sigma^2 $$.

We can easily calculate the sample mean $$ \bar{x} $$ as:

$$ \bar{x} = \frac{T}{n} \tag{4} $$

And now, we can calculate the variance of the sample mean $$ \bar{x} $$ which will lead us to our goal, to calculate the standard error of the mean, eq. $$(1)$$. We can calculate the variance of the sample mean as follows:

$$ Var(\bar{x}) = Var\left(\frac{T}{n}\right) = \frac{1}{n^2}Var(T) = \frac{\sigma^2}{n} \tag{5} $$

here we used the variance property $$Var(cX) = c^2Var(X)$$, see derivation in appendix $$A.1$$. Finally, we can calculate the standard error of the mean as:

$$ SEM = \sqrt{Var(\bar{x})} = \sqrt{\frac{\sigma^2}{n}} = \frac{\sigma}{\sqrt{n}} \tag{6} $$

This formula is crucial in statistics as it allows us to estimate the standard deviation of the sample mean from the exact population mean. It's important to note that the standard error of the mean decreases as the sample size increases. This is due to the fact that the sample mean converges to the population mean as the sample size increases, resulting in a more accurate estimate of the population mean (the law of large numbers).

<div class="block info-block">
  <strong>NOTE</strong> 

   Note that sigma is the population standard deviation, not the sample standard deviation. If the population standard deviation is unknown, we can estimate it using the sample standard deviation. In this case, the standard error of the mean is calculated as $$SEM = \frac{s}{\sqrt{n}}$$, where s is the sample standard deviation.
</div>

## In Practice
We can back up this formula with a simple simulation. Let's generate data points from a normal distribution with a population mean of $$42$$ and a population standard deviation of $$3.6$$. We will calculate the sample mean and standard error of the mean for different random sample sizes and compare it with the theoretical value of $$\sigma/\sqrt{n}$$.

```python
mu = 42
sigma = 3.6

np.random.seed(42)
sample_sizes = [10, 100, 1000]

sample_mean_empirical_errors = []
sample_mean_estimated_theoretical_errors = []
sample_mean_theoretical_errors = []

n_resamples = 10000

for n in sample_sizes:
    sample_means = []
    # Resample the data n_resamples times and calculate the sample mean
    for _ in range(n_resamples):
        sample = np.random.normal(mu, sigma, n)
        sample_means.append(np.mean(sample))
    
    # Estimate the standard error of the mean
    sample = np.random.normal(mu, sigma, n)
    sample_mean_estimated_theoretical_errors.append(np.std(sample, ddof=1) / np.sqrt(n))
    
    # Calculate the theoretical standard error of the mean
    sample_mean_theoretical_errors.append(sigma / np.sqrt(n))
    
    # Calculate the empirical standard error of the mean
    sample_mean_empirical_errors.append(np.std(sample_means))
```
Output:
```
Sample size: 10
Empirical error: 1.16
Estimated Theoretical error: 1.15
Theoretical error: 1.14

Sample size: 100
Empirical error: 0.36
Estimated Theoretical error: 0.38
Theoretical error: 0.36

Sample size: 1000
Empirical error: 0.11
Estimated Theoretical error: 0.12
Theoretical error: 0.11
```

Here we examined our formula in case of 3 different random sampling size: 10, 100, and 1000. We calculated the standard deviation of the sample mean empirically with resampling the data 10000 times (given the random sample size) and calculating the standard deviation of the averages. Next, we calculated the estimated theoretical value of $$s/\sqrt{n}$$, where $$s$$ is the sample standard deviation. Finally, we also calculated the exact formula knowing the exact population standard deviation. As we can see, the empirical and theoretical values are very close to each other, which confirms our formula.

<div class="block info-block">
  <strong>NOTE</strong> 

   The estimated value of the standard error of the mean is less accurate compared to the empirical calculation, but the latter requires more computational resources and numerous resampling (in our example 10'000 repetitions) which is often not feasible in reality. The estimated value is a good approximation when the sample size is large.
</div>


## Appendix
Let $$X$$ be a random variable and $$c$$ a constant. We can calculate the variance of the random variable $$cX$$ as follows:

$$ Var(cX) = \mathbb{E}[(cX - \mathbb{E}[cX])^2] = \mathbb{E}[(cX - c\mathbb{E}[X])^2] = \mathbb{E}[c^2(X - \mathbb{E}[X])^2] = c^2\mathbb{E}[(X - \mathbb{E}[X])^2] = c^2Var(X) \tag{A.1}$$

here we utilized that the expectation of a constant is the constant itself:

$$ \mathbb{E}[cX] = c \cdot \mathbb{E}[X] \tag{A.2}$$

## References
- [https://en.wikipedia.org/wiki/Standard_error](https://en.wikipedia.org/wiki/Standard_error){:target="_blank"}