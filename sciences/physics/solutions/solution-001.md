# Solution 001

**Matching Problem:** [problem-001.md](../problems/problem-001.md)

**Author:** dev0math

**Date:** 2026-08-16

---

## Key Insight

By symmetry (equal masses, antiparallel equal-speed velocities perpendicular to the separation), each particle orbits the center of mass at half the separation distance. This reduces the problem to a standard one-body Coulomb (Kepler-type) orbit, where the given instant — zero radial velocity — is the point of closest approach (periapsis).

---

## Setup (shared by B1 and B2)

Since the particles have equal mass $m$, the center of mass sits at the midpoint of the separation, so each particle is at distance $50a_0$ from it. With speed $v_0$ (equal for both, by symmetry) and velocity perpendicular to the radius, the angular momentum of each particle about the center of mass is

$$
m v_0 (50a_0) = \mu\hbar \quad\Rightarrow\quad v_0 = \frac{\mu\hbar}{50\,m a_0}
$$

The total angular momentum of the system is $L = 2\mu\hbar$ (both particles contribute equally, same sense of rotation).

The total energy (kinetic of both particles + Coulomb potential) is

$$
E = 2\left(\tfrac12 m v_0^2\right) - \frac{ke^2}{100a_0} = \frac{ke^2}{a_0}\left(\frac{\mu^2}{50^2} - \frac{1}{100}\right)
$$

using $\hbar^2 = m e^2 k a_0$ (from the definition of $a_0$) to simplify $mv_0^2$.

---

## Part B1: $\mu = 4$

$$
E = \frac{ke^2}{a_0}\left(\frac{16}{2500} - \frac{1}{100}\right) = -\frac{9ke^2}{2500a_0}
$$

At the turning points of $r$ (max/min separation), the velocity is purely tangential, so $L = mvr$ and the energy can be written as

$$
E = \frac{L^2}{2mr^2} - \frac{ke^2}{r}
$$

With $L = 2\mu\hbar = 8\hbar$:

$$
-\frac{9ke^2}{2500a_0} = \frac{64\hbar^2}{mr^2} - \frac{ke^2}{r}
$$

Using $\hbar^2/m = ke^2a_0$, multiply through by $r^2$ and simplify:

$$
\frac{ke^2}{a_0}\left(\frac{9}{2500}r^2 - a_0 r + 64a_0^2\right) = 0
$$

Solving the quadratic in $r$:

$$
r = \frac{a_0 \pm \sqrt{a_0^2 - \tfrac{576}{625}a_0^2}}{9/1250} = \frac{1250}{9}a_0\left(1 \pm \frac{7}{25}\right)
$$

The larger root (plus sign) is the maximum separation:

$$
r_{max} = \frac{1250}{9}a_0 \cdot \frac{32}{25} = \frac{1600}{9}a_0
$$

**Answer:**

$$
\boxed{r_{max} = \frac{1600}{9}a_0}
$$

---

## Part B2: $\mu = \frac{15}{2}$

### Step 1: Energy and angular momentum

$$
E = \frac{ke^2}{a_0}\left(\frac{(15/2)^2}{2500} - \frac{1}{100}\right) = \frac{ke^2}{a_0}\left(\frac{56.25}{2500} - \frac{25}{2500}\right) = \frac{ke^2}{80a_0}
$$

$E > 0$ confirms the orbit is unbound (hyperbolic), consistent with the problem statement.

$$
L = 2\mu\hbar = 15\hbar
$$

### Step 2: Eccentricity

Using Hint 1, and $\hbar^2/(mke^2) = a_0$ to simplify:

$$
\frac{4L^2E}{k^2e^4m} = \frac{4(15\hbar)^2}{k^2e^4m}\cdot\frac{ke^2}{80a_0} = \frac{900\hbar^2}{80\,a_0\,k e^2 m} = \frac{900}{80}\cdot\frac{a_0}{a_0} = \frac{45}{4}
$$

$$
\varepsilon = \sqrt{1 + \frac{45}{4}} = \sqrt{\frac{49}{4}} = \frac{7}{2}
$$

### Step 3: Geometry of the trajectory

Since the initial radial velocity is zero, the given instant ($r=100a_0$) is the periapsis of the hyperbolic orbit — the only turning point an unbound attractive orbit has. Using the conic equation $r = a/(1-\varepsilon\cos\theta)$ with periapsis at $\theta = \pi$, the separation diverges ($r\to\infty$) when

$$
1 - \varepsilon\cos\theta_\infty = 0 \quad\Rightarrow\quad \cos\theta_\infty = \frac{1}{\varepsilon}
$$

Measuring the angular sweep from periapsis ($\theta=\pi$) to the outgoing asymptote ($\theta_\infty$), the position vector turns through

$$
\Delta\theta = \pi - \theta_\infty = \arccos\!\left(-\frac{1}{\varepsilon}\right)
$$

### Step 4: Relating position angle to velocity direction

At periapsis, the velocity is purely tangential — perpendicular to the radius vector — so the initial relative velocity direction is offset by $90°$ from the periapsis line.

As $r\to\infty$, the tangential velocity component ($\propto L/r$) vanishes while the radial component approaches a constant, so the asymptotic relative velocity $\vec u_\infty$ becomes **parallel to the position vector direction** at infinity, i.e. at angle $\Delta\theta$ from the periapsis line.

The angle between $\vec u_\infty$ and the initial velocity direction is therefore

$$
\phi = \Delta\theta - 90° = \arccos\!\left(-\frac{1}{\varepsilon}\right) - 90°
$$

which simplifies (using $\cos(x-90°)=\sin x$) to the clean closed form:

$$
\phi = \arcsin\left(\frac{1}{\varepsilon}\right)
$$

This matches the standard Rutherford-scattering relation $\sin(\Theta/2) = 1/\varepsilon$, since by time-reversal symmetry about periapsis, $\phi$ is exactly half the total scattering angle $\Theta$.

### Step 5: Numeric answer

$$
\phi = \arcsin\left(\frac{1}{3.5}\right) = \arcsin\left(\frac{2}{7}\right) \approx 16.6°
$$

**Answer:**

$$
\boxed{\phi \approx 16.6°}
$$

---

## Verification

Note the initial relative velocity of $e^+$ with respect to $e^-$ is parallel to $e^+$'s own velocity (since $\vec v_{e^-} = -\vec v_{e^+}$, so $\vec v_{rel} = \vec v_{e^+}-\vec v_{e^-} = 2\vec v_{e^+}$), so the angle computed for the relative motion is the same angle asked for between $\vec u_\infty$ and $e^+$'s initial line of motion. A numerical check of the algebra gives $\varepsilon = 3.4999996 \approx 3.5$ and $\phi = 16.6015°$, confirming the closed-form result.

## References

Physics Olympiad Theory Problem T1-B ("Electron-positron pair"), Parts B1 and B2.
