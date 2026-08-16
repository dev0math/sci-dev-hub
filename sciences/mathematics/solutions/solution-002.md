# Solution 002

**Matching Problem:** [problem-002.md](../problems/problem-002.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

$N \equiv 1 \pmod 5$ and $N \equiv 1 \pmod 6$ can be combined into a single condition mod $\mathrm{lcm}(5,6) = 30$, which sharply narrows the candidates before applying the mod 7 condition.

---

## Step-by-Step Solution

### Step 1: Combine the mod 5 and mod 6 conditions

$N$ leaves remainder 1 when divided by both 5 and 6. This means $N - 1$ is divisible by both 5 and 6, hence by $\mathrm{lcm}(5,6) = 30$.

So $N = 30k + 1$ for some non-negative integer $k$.

### Step 2: Apply the bound $N \le 150$

Candidates: $N \in \{1, 31, 61, 91, 121\}$.

### Step 3: Apply the mod 7 condition

$N$ must satisfy $N \equiv 2 \pmod 7$. Checking each candidate:

- $1 \bmod 7 = 1$
- $31 \bmod 7 = 3$
- $61 \bmod 7 = 5$
- $91 \bmod 7 = 0$
- $121 \bmod 7 = 2$ ✓

So $N = 121$.

### Step 4: Find a valid row size

We need a row size that divides 121 evenly. Since $121 = 11^2$, its only divisors greater than 1 are 11 and 121.

Among the answer choices, only 11 divides 121.

---

## Final Answer

$$
\boxed{\text{(b) 11}}
$$

---

## Verification

$121 = 11 \times 11$: eleven rows of eleven members each, with none left over. Also check original conditions: $121 = 24\times5+1$, $121=20\times6+1$, $121=17\times7+2$. All match.

## References

SVSU Math Olympics 2022 Level I Solutions, Problem 2.
