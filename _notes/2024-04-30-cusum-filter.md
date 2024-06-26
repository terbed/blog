---
title: "CUSUM Filter"
tags: data
comments: true
---

In financial machine learning (finML), filtering time series data is crucial. It allows us to train our models only on significant events, effectively discarding the noise hindering accurate predictions. 

The CUSUM filter was originally used as a quality-control method, designed to **detect a shift in the mean value** of a measured quantity away from a target value. In finML, we can use it to detect significant events in time series data.

We define the cumulative sums the following way:

$$ S_t = \max\left\{0, S_{t-1} + y_t - \mathbb{E}_{t-1}[y_t] \right\} \tag{1}$$

where $$y_t$$ is the IID observation at time $$t$$ arising from a locally stationary process, and $$\mathbb{E}_{t-1}[y_t]$$ is the expected value of $$y_t$$ at time $$t-1$$.

This procedure would recommend an event any time $$S_t$$ exceeds a certain threshold $$h$$. This is designed to detect upside divergences as $$S_t$$ is zero floored. Every time $$S_t$$ exceeds $$h$$, we can flag an event and reset $$S_t$$ to zero.

The concept of run-ups can be extended to run-downs, this way, we can detect significant events in the opposite direction as well.

$$ S_t^+ = \max\left\{0, S_{t-1}^+ + y_t - \mathbb{E}_{t-1}[y_t] \right\} \tag{2.1}$$

$$ S_t^- = \min\left\{0, S_{t-1}^- + y_t - \mathbb{E}_{t-1}[y_t] \right\} \tag{2.2}$$


$$ S_t = \max\left\{S_t^+, -S_t^-\right\} \tag{2.3}$$

<div class="block question-block">
  <strong>QUEST 1:</strong> Why not simply use $$ S_t = S_{t-1} + y_t - \mathbb{E}_{t-1}[y_t] $$ and inspect whether $$|S_t| > h $$ ?
</div>

Implementing and playing with this method makes it much easier to understand and permits a deeper understanding of its mechanics.
So, let's implement it with the following expected value term definition: $$ \mathbb{E}_{t-1}[y_t] = y_{t-1} $$. This means that the expected value of $$y_t$$ at time $$t-1$$ equals to the latest observation($$y_{t-1}$$). This results in the cumulative sum of returns (price change): $$ S_t =S_{t-1} + y_t - y_{t-1} = S_{t-1} + r_t $$

<div class="block question-block">
  <strong>QUEST 2:</strong> Why is it important to use the previous observation as the expected value? What would happen if we would use a rolling ema to estimate the expected value?
</div>

```python
def cusum_filter(price: np.array, threshold: np.array):
    """
    CUSUM filter for price series.
    :param price: raw price series
    :param threshold: threshold for the filter (array, can be calculated as volatility or ATR)
    :return: event index list
    """
    
    # calculate log returns
    log_ret = np.diff(np.log(price))
    
    # Insert a NaN at the beginning of the log_ret array to match the length of the price array
    log_ret = np.insert(log_ret, 0, np.nan)
    
    t_events = []
    s_pos = 0.0
    s_neg = 0.0

    for i in range(1, len(price)):
        thresh = threshold[i]
        pos = s_pos + log_ret[i]
        neg = s_neg + log_ret[i]

        s_pos = max(0.0, pos)
        s_neg = min(0.0, neg)
        
        S_t = max(s_pos, -s_neg)
        
        if S_t >= thresh:
            s_pos = 0.0
            s_neg = 0.0
            t_events.append(i)

    return t_events
```

<div class="block question-block">
  <strong>QUEST 3:</strong> Why do we use the log returns instead of the raw price series?
</div>

The following figure shows the CUSUM filter applied on dollar bar close prices along with volatility calculated with the exponentially weighted moving average (EMA) of the absolute 60 point lagged returns with an EMA span of 60 points. On the second axe, we can see the used threshold for the filter (0.1% return) along with the S values. Every time the S value exceeds the threshold, we flag an event.
<figure>
  <iframe src="/assets/figs/cusum/cusum.html" width="100%" height="750" frameborder="0"></iframe>
  <figcaption><strong>Figure 1:</strong> CUSUM filter applied on dollar bar close prices.</figcaption>
</figure>

We can see that in case of sideways movements the method filters out the noise effectively. CUSUM filter (aside from ML applications) can be successfully employed to eliminate multiple Bollinger Band crossing signals.

## Answers
### QUESTION 1
<div class="block question-block">
  Why not simply use $$ S_t = S_{t-1} + y_t - \mathbb{E}_{t-1}[y_t] $$ and inspect whether $$|S_t| > h $$ ?
</div>
It is more sensitive to handle the two sides separately. In case of a simple cumulative sum, if it goes negative approaching the bottom threshold and then turns in positive direction, first it has to reach 0 and then exceed the threshold. With separate positive and negative sums, at direction change we start right from 0.

To see the difference we can replot the previous figure with the not-sided CUSUM filter:
```python
def cusum_filter_(price: np.array, threshold: np.array):
    """
    CUSUM filter for price series.
    :param price: raw price series
    :param threshold: threshold for the filter (array, can be calculated as volatility or ATR)
    :return: event index list
    """
    
    # calculate log returns
    log_ret = np.diff(np.log(price))
    
    # Insert a NaN at the beginning of the log_ret array to match the length of the price array
    log_ret = np.insert(log_ret, 0, np.nan)
    
    t_events = []
    s = 0.0
    
    for i in range(1, len(price)):
        thresh = threshold[i]
        s = s + log_ret[i]
        
        S_t = s
        
        if abs(S_t) >= thresh:
            s = 0.0
            t_events.append(i)

    return t_events
 ```

<figure>
  <iframe src="/assets/figs/cusum/cusum_.html" width="100%" height="750" frameborder="0"></iframe>
  <figcaption><strong>Figure 2:</strong> Not sided CUSUM filter applied on dollar bar close prices. The main difference is at sideways market price reversals.</figcaption>
</figure>

### QUESTION 2
<div class="block question-block">
Why is it important to use the previous observation as the expected value? What would happen if we would use a rolling ema to estimate the expected value?
</div>
The proposed formula calculates the compounding log return when applied on log prices. This way we can set a threshold in percentage return terms that is universal across assets. We mark an event every time the cumulative return exceeds the threshold both in the upward or downward direction.

If we were to define the expected value as a rolling EMA, the filter would be tailored to mark events where the price diverges from the EMA. This setup could be useful for example to the return series of the ML model or trading strategy to detect performance divergences from the expected value -- similarly to its original quality control application.

### QUESTION 3
<div class="block question-block">
  Why do we use the log returns instead of the raw price series?
</div>

If we were using raw price and calculate percentage returns then with the sum we would compute the rebalancing cumulative return, while with log returns we compute the compounding cumulative return (the log return is additive, while the raw return is multiplicative). Furthermore, here we calculate the absolute return $$y_t - y_{t-1}$$ (and not the percentage change), applying the logarithm makes it relative.  In general, the log return is more stable and easier to work with. 

If this is not clear, I recommend you to read the following outstanding blog post in this topic: [Returns and Log returns](https://gregorygundersen.com/blog/2022/02/06/log-returns/){:target="_blank"}.

### References
- Advances in Financial Machine Learning by Marcos Lopez de Prado
- [https://gregorygundersen.com/blog/2022/02/06/log-returns/](https://gregorygundersen.com/blog/2022/02/06/log-returns/){:target="_blank"}