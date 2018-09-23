[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> My code follows:
```python
import nsfg
import thinkstats2
import thinkplot
import numpy

#generate 1000 random numbers using numpy
rand_nums = numpy.random.random(1000)

#plot the PMF of the random numbers
pmf = thinkstats2.Pmf(rand_nums)
thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='random numbers', ylabel='pmf')

#plot the CDF of the random numbers
cdf = thinkstats2.Cdf(rand_nums)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='random numbers', ylabel='cdf')
```

The PMF plot is not very helpful -- it just looks like a solid block and can't be interpreted visually. (I'm not sure why we were asked to generate this as a PMF of 1000 different items was never going to be useful. But perhaps that was the point!)
The CDF plot is much easier to read, and shows a generally straight diagonal line, which indicates that the distribution is uniform.
