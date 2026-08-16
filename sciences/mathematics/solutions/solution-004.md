# Solution 004

**Matching Problem:** [problem-004.md](../problems/problem-004.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

Fix the value $k = (a^2+b^2)/(ab+1)$ and suppose, for contradiction, that some pair $(a,b)$ achieves a non-square $k$. Among all such pairs, take one minimizing $a+b$. Treating the defining equation as a quadratic in one variable, Vieta's formulas produce a *second* root that is a smaller positive integer solution with the same $k$ — contradicting minimality, unless that second root is $0$, which forces $k$ to be a perfect square after all.

---

## Step-by-Step Solution

### Step 1: Set up the minimal counterexample

Suppose, for contradiction, that there exists a positive integer $k$ that is **not** a perfect square, and positive integers $a, b$ with

$$
\frac{a^2+b^2}{ab+1} = k \quad\Longleftrightarrow\quad a^2 + b^2 - kab - k = 0
$$

Among all positive integer pairs $(a,b)$ satisfying this equation for this fixed non-square $k$, choose one with $a + b$ **minimal**. Without loss of generality, assume $a \ge b$.

### Step 2: View the equation as a quadratic in one variable

Fix $b$ and $k$, and regard

$$
x^2 - (kb)x + (b^2 - k) = 0
$$

as a quadratic in $x$. By construction, $x = a$ is one root. Let $x'$ be the other root. By Vieta's formulas:

$$
a + x' = kb \quad\Rightarrow\quad x' = kb - a \ \ (\text{an integer})
$$

$$
a \cdot x' = b^2 - k \quad\Rightarrow\quad x' = \frac{b^2-k}{a}
$$

### Step 3: Show $x'$ is a non-negative integer

From $x' = kb - a$, $x'$ is clearly an integer. Since $(x', b)$ satisfies the same equation as $(a,b)$, if $x'$ is also a **positive** integer, then $(x', b)$ is another solution with parameter $k$.

**$x' \ge 0$:** Suppose $x' < 0$. Then $x'^2 - kbx' + (b^2-k) \ge x'^2 + kb\cdot|x'| + b^2 - k > 0$ for $k \geq 1, b\geq 1$, which would need to equal $0$ — contradiction unless the expression can't vanish for negative $x'$; concretely, if $x' \le -1$, then $x'^2 - kbx' + b^2 - k \ge 1 + kb + b^2 - k > 0$ (since $k\ge 1$), so the quadratic cannot vanish at a negative $x'$. Hence $x' \ge 0$.

**$x' \ne 0$:** If $x' = 0$, then from $a \cdot x' = b^2 - k$ we get $b^2 - k = 0$, i.e. $k = b^2$ — but $k$ was assumed **not** a perfect square, contradiction. So $x' \neq 0$, meaning $x' \geq 1$, a positive integer.

### Step 4: Show $x' < a$, contradicting minimality

From $x' = \dfrac{b^2-k}{a}$ and using $a \ge b \ge 1$:

$$
x' = \frac{b^2-k}{a} \le \frac{b^2 - 1}{a} < \frac{b^2}{a} \le \frac{a^2}{a} = a
$$

(using $k \geq 1$ and $b \le a$). So $0 < x' < a$, meaning $x' + b < a + b$.

But $(x', b)$ is a positive-integer solution to the same equation with parameter $k$, and $x' + b < a+b$ — this **contradicts the minimality** of $a+b$ chosen in Step 1.

### Step 5: Conclude

The contradiction shows no such minimal counterexample can exist. Hence, whenever $ab+1 \mid a^2+b^2$ for positive integers $a,b$, the quotient $k = (a^2+b^2)/(ab+1)$ must be a perfect square.

---

## Final Answer

$$
\boxed{\dfrac{a^2+b^2}{ab+1} \text{ is always a perfect square of an integer.}}
$$

---

## Verification

Concrete check: $a=8, b=2$. Then $ab+1 = 17$, and $a^2+b^2 = 64+4=68 = 4 \times 17$, so $k = 4 = 2^2$, a perfect square, consistent with the claim. Note also that Vieta jumping from $(8,2)$ with $k=4$: solving $x^2-8x+0=0$ (since $b^2-k=4-4=0$) gives roots $x=0$ and $x=8$ — matching the descent terminating at $x'=0$ exactly as described in Step 3's boundary case, which is where the chain of solutions for a fixed $k$ bottoms out.

## References

IMO 1988, Problem 6. One of the most celebrated problems in IMO history; this solution uses the standard "Vieta jumping" technique first popularized by this problem.
