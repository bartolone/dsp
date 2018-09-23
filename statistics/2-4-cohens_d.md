[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> Here's my code:
```python
import nsfg
import math


df = nsfg.ReadFemPreg()
live = df[df.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]
totalwgt_firsts = firsts['totalwgt_lb']
totalwgt_others = others['totalwgt_lb']
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d
# everything up to this point is copied from ThinkStats2 (although with some variable name mods)
# below are my additions
CohenEffectSize(totalwgt_firsts, totalwgt_others)
totalwgt_firsts.mean()
totalwgt_others.mean()
```

Cohen's d for total birth weight is `-0.088672927072602` indicating that first babies are lighter than other babies -- and the means bear this out, with the mean weight of first babies `7.201094430437772 pounds` compared to `7.325855614973262 pounds` for other babies.
As noted in ThinkStats2, first babies are born about 13 hours earlier, on average, than other babies, and Cohen's d for this difference was `0.029` standard deviations. By comparison, first babies are, on average, `0.124` standard deviations lighter than other babies.
