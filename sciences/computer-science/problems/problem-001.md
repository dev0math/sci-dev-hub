# Problem 001

**Source:** Original — the classical Josephus problem ($k=2$ elimination step), composed in the style of informatics olympiad problems

**Difficulty:** ★★★★☆

**Field / Subfield:** Algorithms — Recurrence Relations & Bit Manipulation

**Keywords / Tags:** Josephus problem, recurrence relations, binary representation, O(log n) algorithm

---

## Problem Statement

$n$ people stand in a circle, numbered $1$ to $n$. Starting from person 1 and moving clockwise, every 2nd remaining person is eliminated, continuing around the circle, until only one person remains.

1. Derive a closed-form expression for $J(n)$, the position (1-indexed) of the last remaining person, in terms of $n$.
2. Describe an $O(\log n)$ algorithm to compute $J(n)$ for very large $n$ (up to $10^{18}$), and implement it.

---

## Notes

For example, with $n = 5$: eliminate 2, 4, 1, 5, leaving person 3 — so $J(5) = 3$.
