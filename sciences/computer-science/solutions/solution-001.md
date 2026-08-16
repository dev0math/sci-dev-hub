# Solution 001

**Matching Problem:** [problem-001.md](../problems/problem-001.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

Set up a recurrence for $J(n)$ by relating a circle of $n$ people to a smaller circle of $\lfloor n/2 \rfloor$ people after the first full pass of eliminations, then solve the recurrence. The closed form turns out to be a simple bit-rotation of $n$'s binary representation.

---

## Step-by-Step Solution

### Step 1: Base case

With one person, that person survives trivially:

$$
J(1) = 1
$$

### Step 2: Recurrence for even $n$

Suppose $n = 2k$. After the first pass around the circle, everyone in an even position (2, 4, 6, ..., 2k) has been eliminated, leaving the $k$ people originally in odd positions $1, 3, 5, \dots, 2k-1$, and the next elimination starts again from position 1 of this reduced circle (person 3 in the original numbering is eliminated next).

This reduced circle of $k$ people behaves exactly like the original problem, so the survivor's *position within the reduced circle* is $J(k)$. Mapping back to original labels, position $j$ in the reduced circle corresponds to original label $2j - 1$:

$$
J(2k) = 2J(k) - 1
$$

### Step 3: Recurrence for odd $n$

Suppose $n = 2k+1$. After the first pass, positions $2, 4, \dots, 2k$ are eliminated, and then person 1 is also eliminated (the pass wraps around: after eliminating $2k$, the next elimination targets person 1). This leaves the $k$ people originally at positions $3, 5, \dots, 2k+1$, and the next elimination starts from position 3, matching a fresh circle of $k$ people.

Reduced position $j$ maps to original label $2j+1$:

$$
J(2k+1) = 2J(k) + 1
$$

### Step 4: Solve the recurrence

Write $n$ in binary as $n = (1\,b_{m-1}\,b_{m-2}\cdots b_0)_2$ (leading bit is always 1). Applying the recurrence bit by bit from the most significant bit down (each bit doubles and adds $\pm1$ depending on parity, matching exactly a left-rotation of the binary digits), one finds:

$$
J(n) = (b_{m-1}\,b_{m-2}\cdots b_0\,1)_2
$$

In words: **write $n$ in binary, move the leading 1 to the end** — that binary number is $J(n)$.

Equivalently, in closed algebraic form: let $2^p$ be the largest power of 2 with $2^p \le n$, and let $l = n - 2^p$. Then

$$
J(n) = 2l + 1
$$

### Step 5: $O(\log n)$ algorithm

Both the bit-rotation and the $2l+1$ formula only require finding the highest set bit of $n$, which takes $O(\log n)$ time (or $O(1)$ with hardware bit-length instructions).

```python
def josephus(n: int) -> int:
    """Return the 1-indexed survivor position for n people, k=2 elimination."""
    if n <= 0:
        raise ValueError("n must be positive")
    p = 1
    while p * 2 <= n:
        p *= 2
    l = n - p
    return 2 * l + 1

# Example
print(josephus(5))    # 3
print(josephus(41))   # 19
print(josephus(10**18 + 7))
```

**Complexity:** $O(\log n)$ time, $O(1)$ space.

---

## Final Answer

$$
\boxed{J(n) = 2\left(n - 2^{\lfloor \log_2 n \rfloor}\right) + 1}
$$

computed in $O(\log n)$ time via the algorithm above.

---

## Verification

Brute-force simulation (elimination by direct list removal) confirms the formula for all tested cases, including $n = 1, 2, 3, 4, 5, 6, 7, 10, 14, 41$ — every value matches $J(n) = 2l+1$ exactly.

## References

Original derivation, composed for this archive. This is the classical Josephus problem with elimination step $k=2$.
