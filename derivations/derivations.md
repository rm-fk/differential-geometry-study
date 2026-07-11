# Differential Geometry Notes

## sketch of the proof:

let $\gamma(t) = p + r(\cos t + \sin t)$, such that

$$\gamma(t) = p + r \cos t \, \vec{x} + r \sin t \, \vec{y}$$

the derivative is then:

$$\gamma'(t) = -r \sin t \, \vec{x} + r \cos t \, \vec{y}$$

so

$$|\gamma'(t)| = \sqrt{r^2 (\cos^2 t + \sin^2 t)} = r$$

This means the integral would then be

$$\int_0^{2\pi} r \, dt = 2 \pi r$$

---

## differentiating $\sigma(\tau(s)) = 1$

a regular curve $\gamma$ is said to parameterize if $|\dot{\gamma}| = 1$. This means the unit speed is constant, such that the arc length of $\gamma$ $L(\gamma)$ is simply $b - a$

### Proving Theorem 2.6

Let $\gamma : I (a,b) \to \mathbb{R}^n$ be a regular $C^1$-curve in $\mathbb{R}^n$. Then the image $\gamma(I)$ of $\gamma$ can be parameterized by its arc length.

definition $\gamma(a,b) = (0, L)$ is simply because

$$\int_a^{(a, b)} \to \int_a^a + \int_a^b$$

Let $\tau : (0, L) \to (a,b)$ be the inverse of $\sigma$, such that $\sigma(\tau) = s$.

Differentiating, we have

$$\frac{d}{ds}\sigma(\tau(s)) = \frac{d\sigma}{d\tau} \frac{d \tau}{ds}$$

$$= \sigma'(\tau) \dot{\tau}$$

$\sigma'(\tau) = 1$ by definition,

and $\dot{\tau} = 1$ by definition of inverse function, $\dot{f^{-1}} = 1 / f'(f^{-1})$, such that

$$\dot{\tau} = 1 / \sigma'(\tau)$$

so that

$$\frac{d}{ds}\sigma(\tau(s)) = \sigma'(\tau) / \sigma'(\tau) = 1$$

---

## Introduction to Frenet theory for $\mathbb{R}^2$

For a regular planar curve $\gamma: I \to \mathbb{R}^2$ parametrised by arc length, we define its tangent $T$ along $\gamma$ by

$$T(s) = \dot{\gamma(s)}$$

and its normal $N$

$$N(s) = R \circ T(s) = R(T(s))$$

where $R: \begin{bmatrix} a \\ b \end{bmatrix} \mapsto \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \cdot \begin{bmatrix} a \\ b \end{bmatrix}$

by definition, the set $\{T,N\}$ is orthonormal

Let $\gamma$ be a regular $C^2$ curve parameritized by arc length. The curvature $\kappa : I \to \mathbb{R}$ is

$$\kappa(s) = \langle\dot{T}, N\rangle = \ddot{\gamma^i} N_i$$

such that we can define the Frenet frame

$$\begin{bmatrix} \dot{T} \\ \dot{N} \end{bmatrix} = \begin{bmatrix} 0 & \kappa \\ -\kappa & 0 \end{bmatrix} \begin{bmatrix} T \\ N \end{bmatrix}$$

### Proof:

use natural decomposition

$$\dot{T} = \langle\dot T, T\rangle T + \langle\dot T, N\rangle N$$
$$\dot{N} = \langle\dot N, T\rangle T + \langle\dot N, N\rangle N$$

We can pull the definition such that

$$2 \langle\dot T, T\rangle T = \frac{d}{ds} \langle T,T\rangle = 0$$
$$2 \langle\dot N, N\rangle T = \frac{d}{ds} \langle N,N\rangle = 0$$

We are left with
$$\dot{T} = \langle\dot T, N\rangle N$$
$$\dot{N} = \langle\dot N, T\rangle T$$

We recall that due to orthonormality, $\langle T, N\rangle = 0$. This means

$$\frac{d}{ds} \langle T,N\rangle = 0$$

$$\langle\dot T, N\rangle + \langle\dot N, T\rangle = 0$$

$$\langle\dot T, N\rangle = -\langle\dot N, T\rangle$$

using $\langle\dot T, N\rangle = \kappa$, then

$$\dot{T} = \kappa N$$
$$\dot{N} = -\kappa T$$

---

## Proof of $\kappa(s) = \frac{\det(\gamma', \gamma'')}{|\gamma'|^3}$

We start with the definition of $\gamma(s)$. Now define point vector $Q(s) = \gamma(t(s))$

$$T(s) = \frac{d \gamma}{d t} \frac{dt}{ds}$$

use inverse function rule:
$$\frac{dt}{ds} = 1 / \left(\frac{ds}{dt}\right)$$

so that

$$\gamma'(t(s)) / |\gamma'(t(s))|$$

(also a sidenote now i see how the metric component in GR or QFT just surface naturally. wow)

$$K(s) = \left(\gamma'(t(s)) / |\gamma'(t(s))|\right)'$$

use chain rule
$$\frac{d}{ds} T$$

$$\frac{dT}{du} \frac{du}{ds}$$

$$\frac{dT}{du} = 1/ |\gamma'|$$

so that

$$\frac{dT}{du} \frac{du}{ds} = \frac{1}{|\gamma'|} \cdot \frac{\gamma'' |\gamma'| - \gamma' |\gamma'|'}{|\gamma'|^2}$$

---

use the fact that $|\gamma'(t(s))|' = s''$, such that

$$s' = |\gamma'|$$

$$s'' = |\gamma'|'$$

$$dy \, dx = \frac{dy}{du} \frac{du}{dv} \frac{dv}{d\gamma}$$

$$|\gamma'|' = \sqrt{\gamma' \gamma'}'$$

$y = \sqrt{u}$
$u = \gamma' \gamma'$
$v = \gamma$

$$\frac{dy}{du} = \frac{1}{2\sqrt{u}}$$
$$\frac{du}{d\gamma'} = 2 \gamma'$$
$$\frac{d\gamma'}{d\gamma} = \gamma''$$

$$|\gamma'|' = \gamma' \gamma'' / |\gamma'|$$

such that now

$$K(s) = \left(\gamma''(t(s)) |\gamma'(t(s))| - \gamma'(t(s)) \cdot (\gamma' \gamma'' / |\gamma'|)\right) / |\gamma'(t(s))|^3$$

$$= \left(\gamma''(t(s)) / |\gamma'(t(s))|^2\right) - \left(\frac{\gamma''}{|\gamma'(t(s))|^2} \frac{\gamma'}{|\gamma'(t(s))|}\right) \frac{\gamma'}{|\gamma'(t(s))|}$$

then the curvature:

$$\kappa(s) = |K(s)|$$

$$= \sqrt{|\gamma'| |\gamma''| - ((\gamma')(\gamma''))^2} / |\gamma'|^3$$

term above is simply the definition of cross product, so

$$\kappa(s) = \det[\gamma', \gamma''] / |\gamma'|^3$$
