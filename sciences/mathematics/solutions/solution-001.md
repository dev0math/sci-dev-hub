# Solution 001

**Matching Problem:** [problem-001.md](../problems/problem-001.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

Translate each "coefficient is a root of the reduced equation" condition into an algebraic equation, then eliminate variables using the fact that $a, b, c \neq 0$.

---

## Step-by-Step Solution

### Step 1: Write the three conditions

- $a$ is a root of $bx + c = 0$: $ab + c = 0$
- $b$ is a root of $ax^2 + c = 0$: $ab^2 + c = 0$
- $c$ is a root of $ax^2 + bx = 0$: $ac^2 + bc = 0$

### Step 2: Solve for $b$

Subtracting the first two equations: $ab^2 - ab = 0 \Rightarrow ab(b-1) = 0$.

Since $a, b \neq 0$, this forces $b = 1$.

### Step 3: Solve for $a$ and $c$

With $b = 1$, both the first and second equations reduce to $a + c = 0$, so $a = -c$.

The third equation becomes $ac^2 + c = 0 \Rightarrow c(ac + 1) = 0$. Since $c \neq 0$, $ac = -1$.

Substituting $a = -c$: $-c^2 = -1 \Rightarrow c^2 = 1 \Rightarrow c = \pm 1$, and correspondingly $a = \mp 1$.

### Step 4: Evaluate both cases

**Case $c = 1$, $a = -1$:** $p(x) = -x^2 + x + 1 = 0$, i.e. $x^2 - x - 1 = 0$.
Sum of roots (Vieta's formula, $-b/a$ with $a=1, b=-1$) $= 1$.

**Case $c = -1$, $a = 1$:** $p(x) = x^2 + x - 1 = 0$.
Sum of roots $= -1$.

Both cases satisfy all three original conditions and give two real, distinct roots (discriminant $= 5 > 0$ in both cases), so both are valid.

---

## Final Answer

$$
\boxed{\text{(d) 1 or } -1}
$$

---

## Verification

Alternative shortcut: dividing $p(x)$ by $a$ gives $x^2 + (b/a)x + (c/a) = 0$. Since $c/a = -1 < 0$, the product of the roots is negative, guaranteeing two real roots of opposite sign, and the sum of roots is $-b/a = \mp 1$, matching both cases above.

## References

SVSU Math Olympics 2022 Level I Solutions, Problem 1.
