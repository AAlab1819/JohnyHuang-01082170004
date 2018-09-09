# Week 02 Solution

### 291A-Spyke Talks

[Question](http://codeforces.com/problemset/problem/291/A)|[Answer](http://codeforces.com/contest/291/submission/42601780)

Sorting Algorithm: Shell Sort

Objective of problem 291A-Spyke Talks is to find how many pair of employees are using spyke. Employees in a pair are given the same call 
id, and employees not using spyke are given call id of 0. There may also be a case in which there is a mistake in the data which will
result in -1. To find the number of pairs of employees are using spyke, we must first sort the list of call ids in an ascending order.
Sorting algorithm used in this scenario is Shell Sort with a gap of n/2. 

Sorting of the list begins by comparing and swapping elements with gap of n/2 if elements are not in the correct position. The next gap
would be the gap/2 until gap is less than 0. 

**Example:**

5 8 2 1 10 | Gap: 5/2 = 2

2 8 5 1 10 | Compare elements index 0-2-4 | Swap index 0-2

2 1 5 8 10 | Compare elements index 1-3 | Swap index 1-3

1 2 5 8 10 | Gap: 2/2 = 1

1 2 5 8 10 | Compare elements index 0-1-2-3-4 

1 2 5 8 10 | Gap: 1/2 = 0 END

After sorting is completed we can now find how many pair of employees are using spyke. This is done by checking if 2 adjacent non zero
call ids are the same. However, if there are 3 adjacent non zero call ids that are the same, then the data is wrong as a call id should
be unique to only 2 people. 

**Example:**

0 1 1 7 7 10 | 2 Pairs

0 1 1 7 7 7  | -1 Not Possible

### 230A-Dragons

[Question](http://codeforces.com/problemset/problem/230/A)|[Answer](http://codeforces.com/contest/230/submission/42700338)

Sorting Algorithm: Insertion Sort

### 768A-Oath of Night's Watch

[Question](http://codeforces.com/problemset/problem/768/A)|[Answer](http://codeforces.com/contest/768/submission/42602686)

Sorting Algorithm: Heap Sort
