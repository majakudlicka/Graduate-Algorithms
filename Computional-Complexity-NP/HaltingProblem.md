**Undecidability**

Undecidable = computationally impossible, no algorithm solves the
problem on every input. Unlimited time & space.

*Def - Halting problem*

Input: A program P (in any language) with an input I

Output: True if P(I) ever terminates, false if P(I) never terminates

*HP example*

Program P:

While x%2 == 1 {

x+=6

}

Let x = 5

Program never halts ==> Halting(P,5) = false

