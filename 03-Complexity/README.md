# Week 03 Solutions

### 492B-Vanya and Lanterns

[Question](http://codeforces.com/problemset/problem/492/B)|[Answer](https://codeforces.com/contest/492/submission/42955946)

Objective of problem 492B-Vanya and Lanterns is to find the minimum light radius each n number of lanterns should have to illuminate
l length of street. To solve this problem first sort the lanterns ascendingly, then we find the largest distance between 2 lanterns and 
divide it by 2. We then compare it to the distance of the first lantern to the beginning of the street to the previously obtained light 
radius, if the distance is larger then the new light distance will be the obtained distance. Doing the same but with the distance of the 
last lantern to the end of the street we will then obtain the collective minimum light radius required to illuminate the entire street.

Best case time complexity: O(1)

Average case time complexity: O(nlog(n))

Worst case time complexity: O(nlog(n))

Best case for this problem is O(1) which could be obtained if there is only 1 lantern in a 1 length street. In this case no loops occur,
hence the best case would be O(1).

### 148A-Insomnia Cure

[Question](http://codeforces.com/problemset/problem/148/A)|[Answer](http://codeforces.com/contest/148/submission/42937887)

Objective of problem 148A-Insomnia Cure is to find the number of dragons that suffered damage due to the princess. There are d amount of 
dragons and 4 ways to harm the dragon, l, k, m and n, with each method being applied on each method's multiples. To solve this problem
we simply attempt to input all the multiples of l, k, m and n to a set, then print out the size of the set to get the number of dragons
harmed. 

Best case time complexity: O(log(n))

Average case time complexity: O(nlog(n))

Worst case time complexity: O(nlog(n))

Best case for this problem is O(log(n)) which could be obtained if each of the 4 method are equal and occur only once. Insertion of a 
set takes O(log(n)) time and it would only insert once per loop, hence best case would be O(log(n)).

### 469A-I Wanna Be the Guy

[Question](http://codeforces.com/problemset/problem/469/A)|[Answer](http://codeforces.com/contest/469/submission/42940512)

Objective of problem 469A-I Wanna Be the Guy is to find if it is possible for the 2 boys to finish all the levels in a game given that
each boy can pass a set levels. To solve this problem we attempt to input all the levels each boys can pass into a set. If the size of 
the set is equal to the total number of levels, then it is possible to pass all the levels, otherwise it is not possible. 

Best case time complexity: O(log(n))

Average case time complexity: O(nlog(n))

Worst case time complexity: O(nlog(n))

Best case for this problem is O(log(n)) which could be obtained if each boy can only pass 1 level. Insertion of a set takes log(n) time
and it would only insert 1 time, hence the best case would be O(log(n)).
