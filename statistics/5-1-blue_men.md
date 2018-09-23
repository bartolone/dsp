[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> my code follows:
```python
import nsfg
import thinkstats2
import scipy.stats


#according to ThinkStats2, mean male height in the US is 178 cm and the stdev is 7.7 cm
mu = 178
sigma = 7.7
male_heights = scipy.stats.norm(loc=mu, scale=sigma)

#our desired height range is 70-73 inches (5 foot 10 to 6 foot 1)
#this corresponds to a range in cm of 177.8 to 185.42
#first we're going to find the percentile for each end of the range:

low_end = male_heights.cdf(177.8)
high_end = male_heights.cdf(185.42)

#finally, we get the difference between these percentiles,
#which represents the percentage of US males falling within this height range:

blue_elig = high_end - low_end
print(blue_elig)
```

The percentage of US males eligible to join the Blue Man Group (based on height, anyway), is `34.3%`.
