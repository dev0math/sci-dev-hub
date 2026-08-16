# Solution 003

**Matching Problem:** [problem-003.md](../problems/problem-003.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

Track two invariants: the total product of the "alive" (greater-than-1) numbers, which never increases; and, for part (b), the $p$-adic valuation of every prime, which turns each move into a step of the subtractive Euclidean algorithm.

---

## Step-by-Step Solution

### Part (a): Exactly one number survives

Call a number "alive" if it is currently greater than 1. A move consumes two alive numbers $m,n$ and produces $\gcd(m,n)$ and $\operatorname{lcm}(m,n)/\gcd(m,n)$.

**Claim 1: At least one output is always alive.** If $\gcd(m,n) = 1$, then $\operatorname{lcm}(m,n)/\gcd(m,n) = mn > 1$ (since $m,n>1$), so that output is alive. If $\gcd(m,n) > 1$, the first output itself is alive. Hence a move never sends both inputs to 1 — the alive-count decreases by exactly 0 or 1 each move, never by 2, and never increases.

**Claim 2: The total product $P$ of all alive numbers is non-increasing, and strictly decreases whenever $\gcd(m,n) > 1$.** The product of the two outputs is

$$
\gcd(m,n) \cdot \frac{\operatorname{lcm}(m,n)}{\gcd(m,n)} = \operatorname{lcm}(m,n) = \frac{mn}{\gcd(m,n)}
$$

which equals $mn$ if $\gcd(m,n)=1$ (product unchanged) and is strictly less than $mn$ if $\gcd(m,n) > 1$ (product strictly decreases). Since $P$ is always a positive integer, it can strictly decrease only finitely many times.

**Combining the claims:** Every move either keeps $P$ fixed and decreases the alive-count by 1 (the $\gcd=1$ case), or strictly decreases $P$ (the $\gcd>1$ case). The alive-count starts at 2026 and can decrease at most 2025 times before reaching 1; and $P$ can strictly decrease only finitely often. So only finitely many moves are possible in total. The process stops exactly when fewer than two alive numbers remain — and by Claim 1, the alive-count can never reach 0, so it must stop at exactly 1.

### Part (b): The surviving value $M$ is invariant

Fix a prime $p$. For each number $a$ on the board, let $v_p(a)$ denote its exponent of $p$ in its prime factorization. Since $v_p(\gcd(m,n)) = \min(v_p(m), v_p(n))$ and $v_p(\operatorname{lcm}(m,n)) = \max(v_p(m), v_p(n))$, a move transforms the pair of valuations $(\alpha, \beta) = (v_p(m), v_p(n))$ into

$$
(\min(\alpha,\beta),\ |\alpha - \beta|)
$$

This is exactly one step of the **subtractive Euclidean algorithm** applied to $\alpha$ and $\beta$ — and it is a standard fact that this operation preserves $\gcd(\alpha, \beta)$.

More generally, applying this pairwise operation repeatedly to the full multiset of valuations $\{v_p(a_1), \dots, v_p(a_{2026})\}$ (in any order, mixed with other primes' independent updates) preserves the **gcd of the entire multiset** at every step, since only two entries change at a time and their pairwise gcd is preserved. By part (a), this process for prime $p$ eventually leaves all valuations at 0 except one surviving value — and since the overall multiset gcd never changes, that surviving value must equal $\gcd(v_p(a_1), \dots, v_p(a_{2026}))$, the gcd of the *original* valuations.

Since this holds for every prime $p$ independently of the order of moves, the final surviving number is

$$
M = \prod_{p \text{ prime}} p^{\gcd(v_p(a_1), \dots, v_p(a_{2026}))}
$$

which depends only on the initial 2026 numbers, not on Confucius's choices.

---

## Final Answer

$$
\boxed{\text{Exactly one number survives, and its value } M = \prod_p p^{\gcd(v_p(a_1),\dots,v_p(a_{2026}))} \text{ is independent of the moves made.}}
$$

---

## Verification

Small case check: board $\{4, 6\}$. Move: $\gcd(4,6)=2$, $\operatorname{lcm}(4,6)/\gcd(4,6) = 12/2 = 6$. Board becomes $\{2, 6\}$. Move again: $\gcd(2,6)=2$, $\operatorname{lcm}(2,6)/\gcd(2,6)=6/2=3$. Board becomes $\{2,3\}$. Move again: $\gcd(2,3)=1$, $\operatorname{lcm}/\gcd = 6$. Board becomes $\{1, 6\}$ — exactly one survivor, $M=6$.

Checking against the formula: $v_2(4)=2,\ v_2(6)=1 \Rightarrow \gcd(2,1)=1$, so $v_2(M)=1$. $v_3(4)=0,\ v_3(6)=1 \Rightarrow \gcd(0,1)=1$ (using the standard convention $\gcd(0,n)=n$), so $v_3(M)=1$. This gives $M = 2^1\cdot 3^1 = 6$, matching the simulation exactly.

## References

IMO 2026, Problem 1. Statement confirmed via the official IMO problems archive and multiple independent solution write-ups (Evan Chen's IMO 2026 solution notes; AoPS Wiki, 2026 IMO Problems).
