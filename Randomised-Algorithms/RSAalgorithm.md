**Ext-Euclid(x,y)**

If y = 0, return (x,1,0)

(d, α', β') = Ext-Euclid(y, x  mod y)

Return (d, β', α' - [y/2]β')

O(n^3^) time

**Fermat's Little Theorem**

If p is prime then for every 1<=z <= p-1 (gcd (z,p) =1)

z^p-1^ ≡ 1 mod p

- Basis of RSA algorithm
- Test if number z is prime

**Euler's theorem**- generalisation of Fermat's Little Theorem

For any N,z where gcd(z,N) = 1 then z^Ф(N)^ ≡ 1 mod N

Where Ф(N) = number of integers between 1 & N which are relatively prime
to N = { x: 1<= x <= N, gcd(x, N) = 1}

Ф(N) - Euler's totient function

For prime p = Фp = p-1

Z^(p-1)(q-1) ≡ 1 mod pq

For primes p & q, let N = pq

Take d,e where de≡1 mod (p-1)(q-1)

z^de^ ≡ z x (z^(p-1)(q-1)^)^k^ ≡ z mod N

(p-1)(q-1) --> only sender knows p and q which ha can use Ext Euler's
algorithm on to compute and decrypt the message

e, N - publicly available

z^(p-1)(q-1)^ --> Because the reminder of devision is 1 therefore de =
1+ k(p-1)(q-1)

Take b,c where bc ≡ 1 mod p-1

bc = 1 + k(p-1 for some integer k

*Example of RSA public-key cryptosystem*

Alice ---------------------------> Bob

1. Bob picks 2m-but random numbers p and q
2. Bob chooses e relatively prime to (p-1)(q-1)
3. Try e = 3,5,7...
4. Bob publishes his public key (N,e)
5. Bob computes his private key d ≡ e^-1^ mod (p-1)(q-1) using
   Ext-Euclid

*RSA pitfalls*

- Gcd(m, N) needs to be exactly 1
- M can't be too large nor too small
- Sending same message many times makes it prone to decryptying

Algorithm requires we come up with a random number - how?

- Generate random number
- Check whether it is prime

Probability that number is prime = 1/n number of bits

prime != composite

**Fermat's test**

If r is prime then for all z∈ {1, ..., r-1} z^r-1^ ≡ 1 mod r

Find z where z^r-1^ !≡ 1 mod r --> proves that r is composite-->
Fermat's witness

Does every composite r have a Fermat's witness? Yes, usually many.

Trivial Fermantt's witness -a where gcd(a,b)>1

Non-trivial = gcd(a,b) =1

Carmichael numbers = pseudoprimes = composite with NO nontrivial Fermat
witness, for example 561, 1105, 1729 etc

*Simple Primality testing*

For n-bit r

1. Choose z randomly prom {1, 2, ...r-1}
2. Compute z^r-1^ mod r
3. If the above isn't 1 then output r is composite else r might be prime

Repeat k times

Probability of false positive - (1/2)^k^
