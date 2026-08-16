# Problem 003

**Source:** IMO 2026, Problem 1 (Shanghai, China)

**Difficulty:** ★★★★☆

**Field / Subfield:** Number Theory — GCD/LCM, Invariants

**Keywords / Tags:** gcd, lcm, invariant, p-adic valuation, blackboard game

---

## Problem Statement

There are 2026 integers greater than 1 written on a blackboard, not necessarily different.

In a move, Confucius chooses two integers $m > 1$ and $n > 1$ from different places on the blackboard and replaces these two integers with

$$
\gcd(m,n) \quad \text{and} \quad \frac{\operatorname{lcm}(m,n)}{\gcd(m,n)}
$$

He continues to make moves while it is possible to do so.

**(a)** Prove that, regardless of the choices of Confucius, after finitely many moves, exactly one integer $M$ on the blackboard is greater than 1.

**(b)** Prove that the value of $M$ does not depend on the choices of Confucius.

---

## Notes

A move requires two numbers strictly greater than 1; once a number becomes 1, it can never be chosen again.
