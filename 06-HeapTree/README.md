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
A new node is then created which stores the topic ID and the increase popularity score as its Key. After adding every topic into the heap tree,
it is then max heapified to get the topic with the highest increase popularity score as the root of the heap tree. The process of extracting
the root of heap and heapify is done 5 times to get the 5 topics with the highest increase in popularity score.

Worst time complexity: O(nlogn)

### Find the Running Median

[Question](https://www.hackerrank.com/challenges/ctci-find-the-running-median/problem)

Objective of the problem "Find the Running Median" is to find the median of a list every time a new number is added. The median of an odd
sized list will be the element in the middle of the sorted list. While the median of an even sized list will be the average of the 2 elements
in the middle of the sorted list. 

The solution to this problem can be found using a 2 heap tree with the number as the key for the node. 
The first tree will be a min heap that stores numbers that are bigger than the current median, and the second tree will be a max heap that
stores the numbers that are smaller than the current median. The median will start out as 0 and will be updated as nodes are inserted. 
After inserting a node, the size of the trees will be compared, and if their size difference is greater than 1, the root of the max heap
will be moved to the min heap and vice versa depending on which tree is larger with the larger tree having its root node transfered. This 
is done to keep the size of the trees balanced which will be used to find which scenario of median calculation is used. If the size of 
the max heap is larger than the min heap, the root of the max heap will be the new median and vice versa. However, if the size of the 
heaps are similar, then the average of the root of the max and min heap is used as the new median. 

Worst time complexity: O(nlogn)
