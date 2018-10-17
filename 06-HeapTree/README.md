# Week 06 Solution

### Roy and Trendy Topics

[Question](https://www.hackerearth.com/practice/data-structures/trees/heapspriority-queues/practice-problems/algorithm/roy-and-trending-topics-1/)

Objective of the problem "Roy and Trendy Topics" is to find which top 5 topics has the highest increase in popularity score. Each topic
will be given a unique ID, previous popularity score, and number of post, likes, comments and shares. Each post earns the topic 50 points,
likes 5 points, comment 10 points, shares 20 points. 

The solution to this problem can be found using a maximum heap tree that is formed
using the increment in popularity score as the key for each node. Upon inputting the values of a post, the calculation for the increment
in popularity score is immidiately calculated using the formula 

```
Increase popularity score = (50 x posts) + (5 x likes) + (10 x comments) + (20 x shares) - popularity score
```
A new node is then created which stores the topic ID, old popularity, new popularity and the increase popularity score as its Key. After adding every topic into the heap tree,
it is then max heapified to get the topic with the highest increase popularity score as the root of the heap tree. The tree is then heap sorted to sort the heap ascendingly, after which the top 5 topics that has the most increase in popularity score can be easily found.

Worst time complexity: O(nlogn)

### Find the Running Median

[Question](https://www.hackerrank.com/challenges/ctci-find-the-running-median/problem)

Objective of the problem "Find the Running Median" is to find the median of a list every time a new number is added. The median of an odd
sized list will be the element in the middle of the sorted list. While the median of an even sized list will be the average of the 2 elements
in the middle of the sorted list. 

The solution to this problem can be found using a heap tree. After each number input, the number is inserted into the heap tree and
the tree is sorted using heapsort. It is then possible to find the median of the current list by finding the middle element of the 
sorted list. If the list is odd then middle element is median, however if it is event, then the 2 middlemost number is averaged to find
the median.

Worst time complexity: O(nlogn)
