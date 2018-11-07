# Week 09 Solution

### SuperSale

[Question](https://uva.onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&category=24&page=show_problem&problem=1071)|[Answer](https://github.com/AAlab1819/JohnyHuang-01082170004/blob/master/09-ClassicDP/SuperSale)

This is a case of classic 0/1 Knapsack problem, the objective of this problem is to find the optimal way to fill your sack given a list of
items, its weight and price, and 1 of each items. This case also adds an extra condition where we have to find the optimum way to fill
the sack for each family member in a family, given they each can carry a specified max weight. 
The solution to this problem can be found using 

DP, where we store the maximum value we can get in a table of item weight x max sack weight. To find the value to input into each table
element, we have 3 case. The first case is if either item weight or max sack weight is 0, then we will input 0. Second case
is if the weight of the current item is less than the current max weight, then we will find the maximum value between the element above it
or the current price + optimal price of remaining weight. Third case is if current item weight is greater than max weight, then it directly
takes the value from the element above. As there is varying max weight in respect to each family member, we take the values that is at the
last item x max weight of family member, and add them all together, but since I'm lazy so i just repeat the DP process for each family member
and its still AC.

Example:

```
200   240   140   150   | Value/Price
1     3     2     5     | Item Weight
0     1     2     3     | Index

Let Max Weight = 5

Table

  | 0 | 1 | 2 | 3 | 4 | 5 | w Row
0 | 0 | 0 | 0 | 0 | 0 | 0 |
1 | 0 |200|200|200|200|200|
3 | 0 |200|200|240|440|440|
2 | 0 |200|200|340|440|440|
5 | 0 |200|200|340|440|440|
i Column

Finding of (2 (i=3),3)
2 <= 3 
K[i][w] = max(val(i-1) + K[i-1][w-wt[i-1], K[i-1][w]
K[3][3] = max(val(3-1) + K[3-1][3-wt[3-1], K[3-1][3]
        = max(val(2) + K[2][3-2], K[2][3])
        = max(val(2) + K[2][1], K[2][3])
        = max(140 + 200, 240)
        = max(340, 240)
        = 340
```
