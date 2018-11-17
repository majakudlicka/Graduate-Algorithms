**Modular Arithmetic**

For integer x, x mod 2 = least significant bit of x = 1 if x is odd, 0
if x is even

For integer N >=1

x mod N = reminder when dividing x by N

x≡y mod N = means x/n amd y/n have same reminder

Example mod 3 3 equiv classes:

-6, -3, 0, 3, 6...

-5, -2, 1, 4, 7...

-4, -1, 2, 5, 8...

**Fact**

If x≡y mod N & a≡b mod N then

x+a ≡ y+b mod N & xa ≡ xb mod N

*Modular exponentiation*

n-bit numbers x,y,N. Compote x^y^ mod N

Repeated squaring:

Compute x mod N = a~1~

x^2^ ≡ a~1~^2^ mod N = a~2~

x^4^ ≡ (a~2~)^2^ mod N = a~4~

Etc

For even y, x^y^ = (x^y/2^)^2^

For odd y, x^y^ = x (x^[y/2]^)^2^

[y/2]--> we round it down

**ModExp(x,y,N)**

Input: n-bit integers x,y,N >=0
Output: X^y^ mod N

If y = 0, return 1

z = Modexp(x, [y/2], N) (refers to itself, recurrence)

If y is even then return z^z^ mod N

Else return xz^z^ mod N

**Multiplicative inverses**

ex. 3x 1/3 = 1

Def

x is a multiplicative inverse of z if xz ≡ 1 mod N

Notation

x ≡ z^-1^ mod N
z ≡ x^-1^ mod N

*Example*

N = 14

1^-1^ ≡ 1 mod N

2^-1^ mod N does not exist

3^-1^ ≡5 mod N

4^-1^ mod N does not exist

5^-1^ ≡3 mod N

6^-1^, 7^-1^, 8^-1^ do not exist

9^-1^ ≡11 mod N

13^-1^ ≡ 13 mod N

When does not exist? - If they have a common divider

**Theorem**

X^-1^ mod N exists if gcd(x, N) = 1 (x & N are relatively prime)

gcd = greatest common divider

Suppose x^-1^ mod N exists

Ex x=3, N=11

3^-1^ ≡ 4 mod 11

4=15=26=26=-7 mod 11

All these numbers are equal mod 11 BUT we always report the smallest
non-negative

Only one unique inverse in N-1 (if one exists)

**Euclid's rule**

For integers x,y where x>= y > 0, gcd(x,y) = gcd(x mod y, y)

**Euclid's GCD algorithm**

Euclid(x,y):

Input: integers x,y where x>= y >= 0

If y=0, return y

Else return Euclid(y, x mod y)

O(n^3^) running time

*Computing inverses*

Ext-Euclid(x,y)

Input: integers x,y where x>= y >= 0

Output: integers d, α, β where

d = gcd(x,y) & d = xα + yβ

Why? Ext-Euclid(x,N) want x^-1^ mod N. If gcd(x,N) =1 then x^-1^ mod N exists

d = 1 + xα + Nβ (apply mod N to both sides)

1 ≡ xα + Nβ mod N

1 ≡ xα mod N

x^-1^ ≡ α mod N

α = inverse of y mod y

β = inverse of y mod x












