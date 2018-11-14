# Week 10 Solution

### 601A The Two Routes

[Question](http://codeforces.com/problemset/problem/601/A)|[Answer](http://codeforces.com/contest/601/submission/45708855)

Problem 601A The Two Routes asks us to find which vehicle takes the least time to travel from town 1 to n and its time. We are given the routes that
a train will take, and the rest will be for the bus. Traveling to each town will take 1 hour for both train and bus.

The solution to this problem can be done using BFS Algorithm. In this solution, we will first traverse the path followed by the train and
calculate its minimum time taken. This is done by making a queue of all the possible paths taken by the train and traversing it by its breadth,
marking each of the town it has already passed, and the accumulated time to reach it. If at any point the queue reaches town n, then we will have the shortest time taken by
the train. On the other hand, if by the end of the queue we have not reach town n, then it is not possible for the train to reach town n.
Then we repeat the same process for the bus, and finally comparing which of its time taken is shortest or if there is no way to reach town
n.

Time Complexity: O(n+m)

