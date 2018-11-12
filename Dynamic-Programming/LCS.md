**Longest Common Subsequence (LCS)**

Input: 2 strings
X = x~1~...x~n~
Y = y~1~...y~n~

Goal: Find the length of longest string which is a subsequence of both X and Y

*Fact* Unix diff function utilizes the solution to LCS problem

Step 1
Design subproblem  in words. Try same problem on the prefix of input

For i where 0 <= i <= n
Let L(i) = length of LCS in x~1~...x~n~, y~1~...y~n~

Step 2
Define recurrence

Can't find solution this way - reformulate subproblem

DP design attempt 2
Two indices i & j (a 2-dimensional table)

For i & j where 0 <=i <=n & 0<=j <=n
Let L(i,j) =length of LCS in x~1~...x~n~, y~1~...y~n~

Recurrence
L(i,0) = 0, L(0,j) = 0

If x~i~ != y~j~ either x~i~ and/or y~j~ are not in the optimal solution

L(i,j) = max {L(i-1,j), L(i, j-1)}

LCS(x,y):

For i: 0->n, L(i,0) = 0

   For j: 1->n L(0,j) = 0
(like finding first row and first column)

For i: 1-> n

For j: 1->n

if x~i~ = y~j~ then
L(i,j) = 1+ L(i-1, j-1)

else
L(i,j) = max{L(i, j-1), L(i-1,j)

return L(n, n)

Time complexity O(m,n)

**Substring with the largest sum**

For 0<=i<=n

Let S(i) = max susbtring of a~1~...a~i~ which includes a~i~

S(i) = a~i~ + max { 0, S(i-1)}

return Max S(i)

**Hotel problem**

a~1~...a~n~
You try to travel 200 miles a day

C~i~ = min 0 <=k < i (C~k~ + 200 - (a~i~ - a~k~)^2^)

**Longest Common Substring**

For i:0->m LIS(i,0) = 0

For j:0->n LIS(0,j) = 0

LIS (i,j) = 1 + LIS (i-1, j-1) if a~j~ = a~i~

0 if a~j~ != a a~i~

return max LIS(i,j)




