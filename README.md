## Lesson 4 - Tuesday 2/4/20

Tonight's topic is inference. Science is an enterprise that seeks generalizable knowledge. In other words, we want to estimate scientifically interesting parameters -- using finite data sets -- and apply what we have learned to a scientifically interesting population. Inference is the "apply that information to scientifically interesting populations" part of this exercise. Normatively, we expect a compelling scientific presentation to include a parameter estimate (or estimates) accompanied by a principled measure of uncertainty; this information becomes the basis for us to apply our results to some broader population. Reading that is useful for this discussion comes from Wasserman (2004, Chapters 6-9).

### Problem #1: Sampling Error

Let's suppose there is a large population (1 million people) of prison releasees. Each prison releasee has some number, *y*, which is a count of prior convictions. Here is the population distribution of *y*:

```R
y <- c(rep(0,721),
       rep(1,6328),
       rep(2,25187),
       rep(3,64254),
       rep(4,117711),
       rep(5,164136),
       rep(6,183155),
       rep(7,165408),
       rep(8,124012),
       rep(9,77863),
       rep(10,41700),
       rep(11,18928),
       rep(12,7299),
       rep(13,2356),
       rep(14,719),
       rep(15,175),
       rep(16,45),
       rep(17,3))
table(y)
```

and the output is:

```Rout
> y <- c(rep(0,721),
+        rep(1,6328),
+        rep(2,25187),
+        rep(3,64254),
+        rep(4,117711),
+        rep(5,164136),
+        rep(6,183155),
+        rep(7,165408),
+        rep(8,124012),
+        rep(9,77863),
+        rep(10,41700),
+        rep(11,18928),
+        rep(12,7299),
+        rep(13,2356),
+        rep(14,719),
+        rep(15,175),
+        rep(16,45),
+        rep(17,3))
> table(y)
y
     0      1      2      3      4      5      6      7      8 
   721   6328  25187  64254 117711 164136 183155 165408 124012 
     9     10     11     12     13     14     15     16     17 
 77863  41700  18928   7299   2356    719    175     45      3 
> 
```

Here is a barplot showing the empirical distribution of *y* in the population.

<p align="center">
<img src="yfig1.png" width="800px">
</p>

Now, suppose we want to answer the following question: "what is the mean value of *y* in this population?" The R code is:

```R
mean(y)
```

and the answer is:

```Rout
> mean(y)
[1] 6.247523
> 
```
