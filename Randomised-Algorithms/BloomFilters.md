*Balls into Bins*

N identical balls & n bins

B~1~, B~2~,....B~n~

Each ball is thrown into a random bin - independent of other balls

Let load(i) = number of balls assigned to B~i~

Probability that max load is >= logn = 1/n

*Power of 2 choices*

For i->n

- Choose 2 random bins
- If load(j) < load (k) then assign the ball to B~j~ - else to B~k~

Max load is O(lognlogn) with high probability

*Hashing setup*

Example- unacceptable passwords.

Huge set U - possible passwords

Maintain S ⊂ U of unacceptable passwords

Hash table H = [0.1...n-1], hash function

H[i] = linked list of elements x ∈ S where h(x) = i

*Power of two choices for hashing*

2 hash functions h~1~ & h~2~

To add x ∈ U into S:

- Compute h~1~(x) & h~2~(x)
- Add x to the less loaded of the above

To check if YES

- Compute h~1~(x) & h~2~(x)

*Bloom filters motivation*

- Faster queries 0(1) time
- Less space
- Simpler
- BUT - chance of a false positive

**Bloom filters**

H is a 0-1 array of size n

Initialize H to all O's - use random hash function h.

Insert (x): set H[h(x)] = 1

Query(x): if H[h(x)] = 1 then output YES else NO

False positive x ∉ S but y ∈ S where h(x) = h(y)

Instead of just one hash function, let's use k of them.

Initialse - set all H~i~[h(x)] to 1

Query - if all are 1s, it is a positive, if at least one is 0 - negative

Optimal k= cln2; c = ratio of size of hash table and the size of
database (words we insert)

False positive rate ~ (0.6185)^c^ for optimal choice of k

Issues: random k, k = cln2

