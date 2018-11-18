Input: an unsorted list A = [a~1~, ...a~n~] of n numbers

Goal: Find th median / fith k^th^ smallest

*Easy algorithm*

Sort A & output the kth element --> mergesort O(n x logn)

*Quicksort*

1. Choose a pivot p (how?)
2. Partition A into A < p, A = p, A > p
3. Recursively sort A < p and A > p

*Search example: pivot*

A = [5,2,20,17,11,13,8,9,11]

Say p =11

A<p = [5,2,8,9]

A=p = [11,11]

A>p = [20,17,13]

If k <= 4 we want the k^th^ smallest in A < p

If 4 < k < = 6 then we output k

If k > 6 then we want the (k - 6th) smallest in A > p

So differently to quicksort, we only have to search in on of the three subsets

T(n) = T(n/2) + O(n), T(n) = O(n)

BUT

T(n) = T(3/4)n + O(n) (good pivot def) also = O(n)

and T(0.99)n + O(n) = O(n)

*Good pivot *

Pivot p is good if |A<p| <= 3/4n & |A>p| <= 3/4n

Goal: Find good pivot in O(n) time

Probability that number picked at random is a good pivot - 50%

If I can check whether it is a good pivot by dividing A < p, A > p, A =
p, and looking at how many elements belong to each one.

If pivot is bad --> repeat selection

Expected time is O(n) --> but worst case time is worse than that

T(n) = T(3/4)n + O(n) = O(n)

We have some slack room for the algorithm to still run in O(n) time ,
namely T(.24)n

T(n) = T(3/4)n + T(n/5) + O(n) --> acceptable time to find a good pivot

- Choose a subset S of A where size of (|S|) = n/5. Set p = median(S)
- Break A into group of 3 elements each (we get n/5 groups in total)
- Sort each group - O(n) time
- Take median of each group: this is our subset S!
- Take median of S recursively = this is our pivot

**FastSelect(A, k) Pseudocode**

1. Break A into n/5 groups G~1~,...G~n/5~ (O(n))
2. For i:1-> n/5 Sort G & let m~i~ = median(G~i~) (O(1) per group = O(n))
3. Let S = { m~1~, ...m~n/5~}
4. p = FastSelect (s, n/10) (T(n/5))
5. Partition A into A >p, A = p, A <p
6. If K <= |A<p| then return FastSelect(A<p, k); if k > |A<p| +|A=p|
   then return FastSelect(A>p, k-|A<p| -|A=p|) else output p (T(3/4)n))


   T(3/4)n + T(1/5)n + O(n) = O(n)



