# Solution 001

**Matching Problem:** [problem-001.md](../problems/problem-001.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

Identify the limiting reactant using the reaction's mole ratio, track how total moles of gas change as reactants convert to product, then apply the ideal gas law at the final temperature.

---

## Step-by-Step Solution

### Step 1: Identify the limiting reactant

The balanced equation requires a 2:1 ratio of $H_2$ to $O_2$. With 2.00 mol $H_2$, the reaction needs:

$$
2.00\ \text{mol } H_2 \times \frac{1\ \text{mol }O_2}{2\ \text{mol }H_2} = 1.00\ \text{mol } O_2
$$

Only 1.00 mol $O_2$ is required, but 3.00 mol is available — so $H_2$ is the limiting reactant.

### Step 2: Compute moles after reaction

- $H_2$ consumed: 2.00 mol (all of it)
- $O_2$ consumed: 1.00 mol → $O_2$ remaining $= 3.00 - 1.00 = 2.00$ mol
- $H_2O$ produced: 2.00 mol (from the 2:2 ratio in the balanced equation)

Total moles of gas after reaction:

$$
n_{total} = n_{O_2,\,remaining} + n_{H_2O} = 2.00 + 2.00 = 4.00\ \text{mol}
$$

### Step 3: Apply the ideal gas law at the final state

$$
P = \frac{nRT}{V} = \frac{(4.00\ \text{mol})(0.08206\ \text{L·atm/(mol·K)})(600\ \text{K})}{10.0\ \text{L}}
$$

$$
P = \frac{4.00 \times 0.08206 \times 600}{10.0} = \frac{196.94}{10.0} \approx 19.7\ \text{atm}
$$

---

## Final Answer

$$
\boxed{H_2 \text{ is limiting}; \quad n_{total} = 4.00\ \text{mol}; \quad P_{final} \approx 19.7\ \text{atm}}
$$

---

## Verification

Total initial moles $= 2.00 + 3.00 = 5.00$ mol. Since the reaction converts 3 mol of reactant gas into 2 mol of product gas for every "unit" reacted, and exactly 3.00 mol of reactant (2.00 $H_2$ + 1.00 $O_2$) reacted to form 2.00 mol $H_2O$, the total mole count should drop by exactly 1.00 mol: $5.00 - 1.00 = 4.00$ mol, which matches Step 2.

## References

Original problem, composed for this archive.
