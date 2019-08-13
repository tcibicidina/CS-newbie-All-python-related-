#Importance of Indexing a panda series
<!-- I was running a self-made survival km plot function today, which automatically deal with missing values, mark categorical feature's low-frequency categories as 'rare' and group continous features based on their quantiles. I ran into a several errors of course, and edited my code fixing bugs. 

One bug I constantly encountered is that  -->
I ran into an interesting error today. When I ran the code 
```python
test1 = somefun()
mydata['test1']=test1
print(test1.isnull().sum())
print(mydata['test1'].isnull().sum())
```
I got two very different numbers! I finally realized that *my fun* returns a pd.series transformed from a list, as below


```python
pd.Series([fun2(x) for x in my[somevar]])
```

The code however, didn't index the panda series.

It looks like when you do 
```python
pdSeriesA = pdSeriesB
```
Python automatically matches the indexes. In this case, pdSeriesB is not indexed as pdSeriesA, therefore Python
decides to put some elements in pdSeriesA as nan.

Lessons I learnt today:
1. Always index a pd series, especially if it is generated from some other pd series which has indexes.
2. In my case, it might be better for me to use pd.Seies.apply, which allows automated index generation.