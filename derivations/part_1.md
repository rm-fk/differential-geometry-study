# Differential Geometry Notes

---

# Arc Length of a Circle

## Sketch of the Proof

Let

$$
\gamma(t)=p+r(\cos t+\sin t),
$$

or equivalently,

$$
\gamma(t)
=
p
+
r\cos t\,\vec{x}
+
r\sin t\,\vec{y}.
$$

Differentiating,

$$
\gamma'(t)
=
-r\sin t\,\vec{x}
+
r\cos t\,\vec{y}.
$$

Hence,

$$
|\gamma'(t)|
=
\sqrt{r^2\left(\cos^2 t+\sin^2 t\right)}
=
r.
$$

Therefore,

$$
\begin{aligned}
L(\gamma)
&=
\int_0^{2\pi}
|\gamma'(t)|
\,dt \\[4pt]
&=
\int_0^{2\pi}
r
\,dt \\[4pt]
&=
2\pi r.
\end{aligned}
$$

---

# Differentiating $\sigma(\tau(s)) = s$

A regular curve $\gamma$ is said to be **parametrized by arc length** if

$$
|\dot{\gamma}|=1.
$$

Hence the speed is constant, and the arc length of $\gamma$ satisfies

$$
L(\gamma)=b-a.
$$

---

## Theorem 2.6

> Let
>
> $$
> \gamma:I=(a,b)\rightarrow\mathbb{R}^n
> $$
>
> be a regular $C^1$-curve in $\mathbb{R}^n$. Then the image
> $\gamma(I)$ can be parametrized by its arc length.

### Sketch

The interval

$$
(0,L)
$$

arises naturally since

$$
L
=
\int_a^b
|\gamma'(u)|
\,du.
$$

Hence,

$$
\sigma(a)=0,
\qquad
\sigma(b)=L.
$$

---

## Proof

Let

$$
\tau:(0,L)\rightarrow(a,b)
$$

be the inverse of $\sigma$, so that

$$
\sigma(\tau(s))
=
s.
$$

Differentiating both sides with respect to $s$,

$$
\frac{d}{ds}
\sigma(\tau(s))
=
\frac{d\sigma}{d\tau}
\frac{d\tau}{ds}.
$$

Applying the chain rule,

$$
=
\sigma'(\tau)\,\dot{\tau}.
$$

Since $\tau=\sigma^{-1}$,

$$
\dot{\tau}
=
\frac{1}{\sigma'(\tau)}.
$$

Therefore,

$$
\begin{aligned}
\frac{d}{ds}
\sigma(\tau(s))
&=
\sigma'(\tau)
\cdot
\frac{1}{\sigma'(\tau)} \\[4pt]
&=
1.
\end{aligned}
$$

This completes the proof.

---

# Introduction to Frenet Theory for $\mathbb{R}^2$

Let

$$
\gamma:I\rightarrow\mathbb{R}^2
$$

be a regular planar curve parametrized by arc length.

## Tangent Vector

The tangent vector is defined by

$$
T(s)
=
\dot{\gamma}(s).
$$

## Normal Vector

The normal vector is defined by

$$
N(s)
=
R\circ T(s)
=
R(T(s)),
$$

where

$$
R
=
\begin{bmatrix}
0 & -1\\
1 & 0
\end{bmatrix}.
$$

Consequently,

$$
R
\begin{bmatrix}
a\\
b
\end{bmatrix}
=
\begin{bmatrix}
0 & -1\\
1 & 0
\end{bmatrix}
\begin{bmatrix}
a\\
b
\end{bmatrix}.
$$

By construction,

$$
\{T,N\}
$$

forms an orthonormal basis along the curve.

---

## Curvature

Let $\gamma$ be a regular $C^2$-curve parametrized by arc length.

Its curvature is defined as

$$
\kappa(s)
=
\langle\dot T,N\rangle
=
\ddot{\gamma}^iN_i.
$$

The Frenet frame is therefore

$$
\begin{bmatrix}
\dot T\\
\dot N
\end{bmatrix}
=
\begin{bmatrix}
0 & \kappa\\
-\kappa & 0
\end{bmatrix}
\begin{bmatrix}
T\\
N
\end{bmatrix}.
$$
