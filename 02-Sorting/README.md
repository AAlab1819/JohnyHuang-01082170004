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

Objective of problem 230A-Dragons is to find if it is possible to slay all the **n** dragons with strength **x** and bonus **y** given 
your strength **s** in any order. To solve this problem we must first sort the dragons in an ascending order according to their strength 
so that we will fight the weakest dragon first. The sorting algorithm used in this scenario is Insertion Sort. 

Insertion sort sorts a list by traversing the list per element and swapping the elements in the opposite direction until it is in the 
correct position. 

**Example:**

5 8 2 1 10 | First element

5 8 2 1 10 | Second element

2 5 8 1 10 | Third element

1 2 5 8 10 | Fourth element

1 2 5 8 10 | Fifth element

Now that the dragons are sorted per their strength we are now able to find if it is possible to slay the dragons. This is done by
checking if our strength is greater than the dragon's strength, if so then add its bonus to our strength. If at any point our strength
is less than the dragon's strength, then it is not possible to slay all the dragons. 

```
for i to n
  if s > dragon[i].strength
    s += dragon[i].bonus
  else if s < dragon[i].strength
    print("NO")
  if i == n
    print("YES")
```

### 768A-Oath of Night's Watch

[Question](http://codeforces.com/problemset/problem/768/A)|[Answer](http://codeforces.com/contest/768/submission/42602686)

Sorting Algorithm: Heap Sort

Objective of the problem 768A-Oath of Night's Watch is to find how many stewards have other stewards with strength **a** that is less 
than and greater than himself. This is done by sorting the list of **n** stewards in an ascending order and finding how many stewards 
have strength in-between the steward with the highest and lowest strength. The sorting algorithm used in this scenario is Heap Sort. 

Heap Sort works by repeatingly building a max heap from an array. The largest number which is found on the root of the heap is then 
swapped with the smallest number. The heap is then heapified to build a max heap again, but with every iteration the size is decreased
by one as the largest number is "removed" from the heap. This goes on until the size of the heap is smaller than 1 and the list is 
sorted.
 
Now that the list of stewards has been sorted in an ascending order it is possible to find how many stewards fulfills the criteria.
This is done by traversing the list by element and tallying up the number of stewards with strength that is not equal to the weakest
steward or the strongest steward.

```
for i to n
  if steward[i] != steward[i] && steward[i] != steward[n-1]
    counter++
print(counter)
```
