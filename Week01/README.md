# Week 01 Solution

### 912A-Tricky Alchemy

[Question](http://codeforces.com/contest/912/problem/A)|[Answer](http://codeforces.com/contest/912/submission/42297123)

Objective of problem 912A-Tricky Alchemy is to find how much yellow and blue crystals Grisha lacks in order to create a specified number 
of christmas balls. She will need a fix amount of 2 yellow crystals, 1 yellow and 1 blue, and 3 blue crystals to create 1 yellow, green 
and blue balls respectively. To solve this problem we need to first find the amount of yellow or blue crystal she lacks, in this case we
find yellow first. The amount of yellow crystal she lacks will be the amount of yellow crystals she has subtracted by the yellow crystals
she needs to create the specified amount of yellow (2 crystals) and green (1 crystal) balls she needed. If the result is a positive number,
then that means that she doesn't lack any yellow crystal. If the result is a negative number, then that is the amount of yellow crystals
that she lacks, or have in excess. Doing the same with the blue crystal, this time blue (3 crystals) and green (1 crystal), will result 
in the amount of blue crystal she lacks. The amount of crystals she lack will be the absolute value of the yellow or blue crystals she
lacks, or in the case where she lacks both will be the sum of the absolute value of yellow and blue crystals.


### 854A-Fraction
[Question](http://codeforces.com/contest/854/problem/A)|[Answer](http://codeforces.com/contest/854/submission/42413745)

Objective of problem 854A-Fraction to find a numerator and denominator with the highest possible proper irreducible fraction such that
when summed together results in a positive integer n. There are 4 criterias that needs to be fulfilled the find the answer:
* Numerator is greater than denominator.
* GCD (Greatest Common Divisor) of numerator and denominator is 1.
* Sum of numerator and denominator is n.
* Its has the highest possible value as a fraction.

To solve this problem we test for GCD from 1 to n/2, and n-1 to n/2 for numerator and denominator respectively to find only the pair with
GCD of 1. The endpoint of the test is set at n/2 is because the numerator should be greater than the denominator to produce a proper 
fraction. The pair of numerator and denominator is set as such because the sum of the 2 will always result in n. GCD of 1 between 
numerator and denominator is to find pairs that can form an irreducible fraction. Finally, the highest possible fraction is found by
overlapping previously stored pairs and only printing after the test is done. 


### 988A-Diverse Team
[Question](http://codeforces.com/contest/988/problem/A)|[Answer]
