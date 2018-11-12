LIS = Longest Increasing Subsequence

subsequence = subset of elements in order (but one can 'skip')

Input: n numbers a~1~, a~2~...a~i~

Goal: Find length of LIS in a~1~, a~2~...a~i~

Let L(i) = length of LIS in a~1~, a~2~...a~i~ which **includes** a~i~

L(i) = 1 + max { L(j); a~j~ < a~i~, j < i

LIS(a~1~...a~n~):

For i= 1-> n
L(i) = 1 (because we need to include last element)

For j=1 -> i-1

if a~j~ < a~i~ & L(i) < 1+ L(j)

then L(i) = 1 + L(j)

We found LIS for all lengths - L(i) is the last one and includes all elements
But it doesn't have to! Therefore we look for max in the array of lengths

Max = 1
For i =2 -> n

If L(i) > L(max) then max = i

Return L(max)