# Week 04 Solution

### 268B-Buttons

[Question](http://codeforces.com/contest/268/problem/B)|[Answer](http://codeforces.com/contest/268/submission/43407975)

Objective of the problem 268B-Buttons is to find the worst amount of button presses to open a n  sequence combination lock given that the 
Manao is going to solve it optimally. To find the correct button to press Manao will make n-1 mistakes in the worst case scenario. However,
every time Manao tries finding the next button he has to press the previous correct button sequence. This gives us the equation __(n-i)*i__
with (n-i) as the remaining buttons to try and *i as the previous number sequence to press for each try. Finally we add n for the correct
button sequence.

Worst Time Complexity: O(n)

### 598D-Igor In The Museum

[Question](http://codeforces.com/contest/598/problem/D)|[Answer](http://codeforces.com/contest/598/submission/43394495)

Objective of the problem 598D-Igor In The Museum is to find the maximum number of paintings Igor will see during his tour around the museum.
It is given that Igor will see all the paintings in his cardinal directions and will tour each spot once. Solution to this problem is found
using flood fill method. We call the flood fill function to check if a tile is out of bound/painting/has been visited.

1.If tile is out of bound or has been visited, then the function will end.

2.If it is a painting then it will increment the number of paintings viewed by 1 and end.

3.If it is a path that hasn't been visited, then it will assign a key to the tile and hence changing its state to has been visited. 

4.Function will then call upon itself this time with its x coordinates reduced by 1, then increased by 1, and similarly for the y coordinates.

5.Function will then end and the number of paintings viewed in that path is assigned to the key.

6.Finally the number of paintings viewed is printed based on the assigned key of the inputted coordinates.

Worst Time Complexity: O(nm)
