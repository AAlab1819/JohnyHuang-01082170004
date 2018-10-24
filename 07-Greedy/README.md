# Week 07 Solution

### 946A Partition

[Question](http://codeforces.com/problemset/problem/946/A/)|[Answer](http://codeforces.com/contest/946/submission/44720815)

The objective of problem 946A Partition is to find the optimal way to partition an array into 2 partition, partition **B** and partition **C**,
to get the maximum possible value when subtracting sum of **B** and sum of **C**. The solution to such problem can be easily found by checking
every number if it is greater than or less than 0. This is because the maximum value will be attained by adding all positive numbers and subtracting
all negative numbers, subtracting a negative number results in a positive sum. 

Worst Time Complexity: O(n)

### 978B File Name

[Question](http://codeforces.com/problemset/problem/978/B)|[Answer](http://codeforces.com/contest/978/submission/44720957)

The objective of problem 978B File Name is to find the number of "X" to be deleted so that there is no occurance of "xxx" in a given string.
This is done by iterating through the string, then incrementing a counter if "X" is found and reseting the counter to 0 if non "X" is found.
After every iteration if the x counter is greater than or equal to 3, then the X to be deleted counter is incremented and x counter is decremented.

Worst Time Complexity: O(n)

### 731B Coupons and Discount

[Question](http://codeforces.com/problemset/problem/731/B)|[Answer](http://codeforces.com/contest/731/submission/44737882)

THe objective of problem 731B Coupon and Discount is to find if it is possible to buy pizzas using only discount and coupons given **n** days and **n** teams each day.
Discounts are used to buy 2 pizzas in a day, and coupons are used to buy 1 pizza in 2 consecutive days. The number of discounts and coupons
that can be used each days is unlimited. The solution to this problem can be found by iterating through the days and checking whether the number of teams that day is odd 
or even. Optimally, all pizzas in a day will be bought using discounts, unless the teams is odd which then a coupon will be used. If a coupon is used in
the previous day then a pizza will be subtracted from today. If at any point there is an odd number of teams and no pizza is needed the next day then
it is impossible to buy pizzas using only discount and coupons.

Worst Time Complexity: O(n)
