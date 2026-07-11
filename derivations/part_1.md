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

a regular curve $\gamma$ is said to parameterize if $|\dot{\gamma}| = 1$. This means the unit speed is constant, such that the arc length of $\gamma$, $L(\gamma)$, is simply $b - a$.

### Proving Theorem 2.6

Let $\gamma : I = (a,b) \to \mathbb{R}^n$ be a regular $C^1$-curve in $\mathbb{R}^n$. Then the image $\gamma(I)$ of $\gamma$ can be parameterized by its arc length.

definition $\gamma(a,b) = (0, L)$ is simply because

$$\int_a^b \to \int_a^a + \int_a^b$$

Let $\tau : (0, L) \to (a,b)$ be the inverse of $\sigma$, such that $\sigma(\tau) = s$.

Differentiating, we have

$$\frac{d}{ds}\sigma(\tau(s)) = \frac{d\sigma}{d\tau} \cdot \frac{d\tau}{ds} = \sigma'(\tau) \cdot \dot{\tau}$$

$\sigma'(\tau) = 1$ by definition,

and $\dot{\tau} = 1$ by definition of inverse function, $\frac{d}{ds}f^{-1} = \frac{1}{f'(f^{-1})}$, such that

$$\dot{\tau} = \frac{1}{\sigma'(\tau)}$$

so that

$$\frac{d}{ds}\sigma(\tau(s)) = \frac{\sigma'(\tau)}{\sigma'(\tau)} = 1$$

---

## Introduction to Frenet theory for $\mathbb{R}^2$

For a regular planar curve $\gamma: I \to \mathbb{R}^2$ parametrised by arc length, we define its tangent $T$ along $\gamma$ by

$$T(s) = \dot{\gamma}(s)$$

and its normal $N$

$$N(s) = R \circ T(s) = R(T(s))$$

where $R: \begin{bmatrix} a \\ b \end{bmatrix} \mapsto \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} a \\ b \end{bmatrix}$

by definition, the set $\{T,N\}$ is orthonormal.

Let $\gamma$ be a regular $C^2$ curve parameterized by arc length. The curvature $\kappa : I \to \mathbb{R}$ is

$$\kappa(s) = \langle \dot{T}, N \rangle = \ddot{\gamma}^i N_i$$

such that we can define the Frenet frame

$$\begin{bmatrix} \dot{T} \\ \dot{N} \end{bmatrix} = \begin{bmatrix} 0 & \kappa \\ -\kappa & 0 \end{bmatrix} \begin{bmatrix} T \\ N \end{bmatrix}$$

### Proof:

use natural decomposition

$$\dot{T} = \langle \dot{T}, T \rangle T + \langle \dot{T}, N \rangle N$$
$$\dot{N} = \langle \dot{N}, T \rangle T + \langle \dot{N}, N \rangle N$$

We can pull the definition such that

$$2 \langle \dot{T}, T \rangle = \frac{d}{ds} \langle T,T \rangle = 0$$
$$2 \langle \dot{N}, N \rangle = \frac{d}{ds} \langle N,N \rangle = 0$$

We are left with

$$\dot{T} = \langle \dot{T}, N \rangle N$$
$$\dot{N} = \langle \dot{N}, T \rangle T$$

We recall that due to orthonormality, $\langle T, N \rangle = 0$. This means

$$\frac{d}{ds} \langle T,N \rangle = 0$$

$$\langle \dot{T}, N \rangle + \langle \dot{N}, T \rangle = 0$$

$$\langle \dot{T}, N \rangle = -\langle \dot{N}, T \rangle$$

using $\langle \dot{T}, N \rangle = \kappa$, then

$$\dot{T} = \kappa N$$
$$\dot{N} = -\kappa T$$

---

## Proof of $\kappa(s) = \frac{\det(\gamma', \gamma'')}{|\gamma'|^3}$

We start with the definition of $\gamma(s)$. Now define point vector $Q(s) = \gamma(t(s))$

$$T(s) = \frac{d\gamma}{dt} \cdot \frac{dt}{ds}$$

use inverse function rule:

$$\frac{dt}{ds} = \frac{1}{\frac{ds}{dt}}$$

so that

$$T(s) = \frac{\gamma'(t(s))}{|\gamma'(t(s))|}$$

(also a sidenote now i see how the metric component in GR or QFT just surface naturally. wow)

$$K(s) = \frac{d}{ds}\left(\frac{\gamma'(t(s))}{|\gamma'(t(s))|}\right)$$

use chain rule

$$\frac{dT}{ds} = \frac{dT}{du} \cdot \frac{du}{ds}$$

$$\frac{dT}{du} = \frac{1}{|\gamma'|}$$

so that

$$\frac{dT}{du} \cdot \frac{du}{ds} = \frac{1}{|\gamma'|} \cdot \frac{\gamma'' |\gamma'| - \gamma' |\gamma'|'}{|\gamma'|^2}$$

---

use the fact that $|\gamma'(t(s))|' = s''$, such that

$$s' = |\gamma'|$$

$$s'' = |\gamma'|'$$

$$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dv} \cdot \frac{dv}{d\gamma}$$

$$|\gamma'|' = \left(\sqrt{\gamma' \cdot \gamma'}\right)'$$

let

$y = \sqrt{u}$
$u = \gamma' \cdot \gamma'$
$v = \gamma$

then

$$\frac{dy}{du} = \frac{1}{2\sqrt{u}}$$

$$\frac{du}{d\gamma'} = 2\gamma'$$

$$\frac{d\gamma'}{d\gamma} = \gamma''$$

$$|\gamma'|' = \frac{\gamma' \cdot \gamma''}{|\gamma'|}$$

such that now

$$K(s) = \frac{\gamma''(t(s)) |\gamma'(t(s))| - \gamma'(t(s)) \cdot \frac{\gamma' \cdot \gamma''}{|\gamma'|}}{|\gamma'(t(s))|^3}$$

$$= \frac{\gamma''(t(s))}{|\gamma'(t(s))|^2} - \left(\frac{\gamma''}{|\gamma'(t(s))|^2} \cdot \frac{\gamma'}{|\gamma'(t(s))|}\right) \cdot \frac{\gamma'}{|\gamma'(t(s))|}$$

then the curvature:

$$\kappa(s) = |K(s)|$$

$$= \frac{\sqrt{|\gamma'|^2 |\gamma''|^2 - (\gamma' \cdot \gamma'')^2}}{|\gamma'|^3}$$

term above is simply the definition of cross product, so

$$\kappa(s) = \frac{\det[\gamma', \gamma'']}{|\gamma'|^3}$$
