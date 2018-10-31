# Week 08 Solutions

### 433B Kuriyama Mirai's Stone

[Question](http://codeforces.com/problemset/problem/433/B)|[Answer](http://codeforces.com/contest/433/submission/45124896)

The objective of problem 433B Kuriyama Mirai's Stone is to find the sum of the numbers written on her stones, given one of the 2 possible
scenarios and the boundary(境界) from which the sum is taken. In the first scenario, the sum will be taken from the unordered list of
stone. In the second scenario, the sum will be taken from the list sorted in an ascending order. 

The solution to this problem can be found by making a cummulative list for both scenarios. Then using the list we can find the sum 
within the boundary by subtracting cummulative sum at the right boundary by the cummulative sum before the left boundary(Sum[r]-Sum[l-1]).
This is because Sum[l-1] contains the sum before(beyond) the boundary exclusively, while Sum[r] contains both the sum before the boundary
and within the boundary. Subtracting Sum[r] by Sum[l-1] eliminates the like term which is the sum before the boundary and therefore resulting
in only sum within the boundary.

```
Sum[r] = Sum(Within)+Sum(Before)
Sum[l-1] = Sum(Before)

Sum[r] - Sum[l-1] = Sum(Within) + Sum(Before) - Sum(Before)
                  = Sum(Within)
```

