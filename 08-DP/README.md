# Week 08 Solutions

### 433B Kuriyama Mirai's Stone

[Question](http://codeforces.com/problemset/problem/433/B)|[Answer](http://codeforces.com/contest/433/submission/45124896)

The objective of problem 433B Kuriyama Mirai's Stone is to find the sum of the numbers written on her stones, given one of the 2 possible
scenarios and the boundary from which the sum is taken. In the first scenario, the sum will be taken from the unordered list of
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

Time conplexity: O(nlogn)

### 913C Party Lemonade

[Question](http://codeforces.com/problemset/problem/913/C)|[Answer](http://codeforces.com/contest/913/submission/45141187)

The objective of problem 913 Party Lemonade is to find the cheapest combination of lemonade bottles given L liter of lemonade needed.
Each lemonade bottles will have the price c[i] and will contain 2^(i-1) liter, and there is an unlimited supply of each bottle.

The solution to this problem can be found by first making an optimal list from the given list. If the price of 2 1L bottles is cheaper
than 1 2L bottle, then it is optimal to buy 2 1L bottles instead, hence we will change the price of c[i] to c[i-1]. After doing so, we
then realize that the price at the end will be the most bang for your buck, regardless of whether it is made up of smaller bottles or
1 bottle. Naturally, we may think that we just need to grab the bottle with the most bang for your buck then, however that may not be 
the case. It is possible that we may find cheaper alternatives with enough L of lemonade for our needs, and so we will compare the 
previous price and the current price to find the cheaper price. Current price can be calculated by adding sum(previous sum + 
bottles needed x price) + L(liter of lemonade needed left after subtracting L of bottles needed) x price. Bottles needed is the maximum
amount of bottles i we can use to cover as much L of lemonade that is left, but not more than L. This will go on until we finally have 
our cheapest combination.

Take for example:
```
Optimization of sample:
3 L needed
10 100 1000 10000 - Original List
1   2   4     8   - Liters

10 20 40 80 - Optimal List
1  2  4  8 - Liters

Code:
int need = L / (1 << i);
sum += need * c[i];
L -= need << i;
ans = min(ans, sum + (L > 0) * c[i]);

Sample in Code:
i = 3
need = 3 / (1<<3) // 1<<3 -> 1000 in binary -> 8 in decimal
     = 0
sum = 0 + 0 * 80
    = 0
L = 3 - 0 << 3 // 0000 in binary -> 0 in decimal
  = 3
ans = minimum of (4e18, 0 + 1 * 80) // L>3 is true resulting in 1, if false results in 0

...

i = 1
need = 3 / (1<<1) // Can buy 1 bottle
     = 1
sum = 0 + 1 * 20
    = 20
L = 3 - 1<<1 // 10 -> 2 in decimal
  = 1
ans = minimum of (40, 20 + 1 * 20)
    = 40
    
i = 0
need = 3 / (1<<0) // Can buy 1 bottle
     = 1
sum = 20 + 1 * 10
    = 30
L = 1 - 1
  = 0
ans = minimum of (40, 30 + 0 * 10)
    = 30
```

Time complexity: O(n)

