[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> Here's my code:
```python
import nsfg
import thinkstats2
import thinkplot


def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
    new_pmf.Normalize()
    return new_pmf
resp = nsfg.ReadFemResp()

#above is all copied from ThinkStats2, below is my solution

actual = thinkstats2.Pmf(resp.numkdhh, label='actual')
thinkplot.Pmf(actual)
thinkplot.Config(xlabel='Number of children', ylabel='PMF')
biased = BiasPmf(actual, label='biased')
thinkplot.PrePlot(2)
thinkplot.Pmfs([actual, biased])
thinkplot.Config(xlabel='Number of children', ylabel='PMF')
actual.Mean()
biased.Mean()
```

The mean of the unbiased distribution is `1.02 children per family` and the mean for the biased distribution is `2.40 children per family`. The code above will plot both distributions together for comparison purposes.
