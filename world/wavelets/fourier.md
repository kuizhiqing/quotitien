# fourier analysis

#### Proposition.
The functions $\{\psi_k = e^{ikt\cdot\pi/L}, t\in\mathbb{R}\}_{k\in\mathbb{Z}} $, form a orthogonal basis for 
periodic functions on interval $[-L,L)$.

**proof**.
$$
\langle \psi_k,\psi_l \rangle = 
\int_{-L}^{L}e^{ikt\cdot \pi/L} e^{-ilt\cdot \pi/L}dt =
2L\cdot\delta_{k,l}
$$

---

### Fourier series

#### Complex form

For $2L$-periodic function $f$,
$$
f(t) = \sum_{k=-\infty}^{\infty} c_k e^{ikt\cdot \pi/L}
$$
where
$$
c_k = \frac{1}{2L} \langle f(t), e^{ikt\cdot \pi/L} \rangle
=  \frac{1}{2L} \int_{-L}^{L}f(t)e^{-ikt\cdot \pi/L}dt 
$$

#### From complex to real

Since $e^{i\theta} = \operatorname{cos}\theta + i\operatorname{sin}\theta $,
suppose $c_k= a_k + ib_k,\, a_k,b_k\in\mathbb{R}$, then
$$
\begin{aligned}
f(t) =& \sum_{k=-\infty}^{\infty} (a_k + ib_k) (\operatorname{cos}(kt\cdot \pi/L) + i\operatorname{sin}(kt\cdot \pi/L)) \\
= & (a_0+ib_0) + \sum_{k=1}^{\infty} (a_k + ib_k) (\operatorname{cos}(kt\cdot \pi/L) + i\operatorname{sin}(kt\cdot \pi/L)) \\
& +\sum_{k=1}^{\infty} (a_{-k} + ib_{-k}) (\operatorname{cos}(-kt\cdot \pi/L) + i\operatorname{sin}(-kt\cdot \pi/L)) \\ 
\end{aligned}
$$
if $f(t)\in\mathbb{R}$,
$a_k=a_{-k}$ and $b_k=-b_{-k}$ which means $c_k=\bar{c_k}$, then
$$
f(t) = a_0 + \sum_{k=1}^{\infty} (2a_k) \operatorname{cos}(kt\cdot \pi/L) + (-2b_k)\operatorname{sin}(kt\cdot \pi/L)) 
$$


#### Real value, conventional form

For $2\pi$-periodic function $f$,
$$
f(t) = \frac{a_0}{2} + \sum_{k=1}^{\infty} (a_k \operatorname{cos}(kt) + b_k\operatorname{sin}(kt))
$$

where

$$
a_k 
= \frac{1}{||\operatorname{cos}(kt)||^2} \langle f(t), \operatorname{cos}(kt)\rangle
= \frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \operatorname{cos}(kt) dt
$$
$$
b_k 
= \frac{1}{||\operatorname{sin}(kt)||^2} \langle f(t), \operatorname{sin}(kt)\rangle
= \frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \operatorname{sin}(kt) dt
$$


#### From fourier series to fourier transform
$$
f(t) = \sum_{k=-\infty}^{\infty} 
\left(
\frac{1}{2L} \int_{-L}^{L}f(x)e^{-ikx\cdot \pi/L}dx 
\right)
\cdot
e^{ikt\cdot \pi/L}
$$

Since
$$
\int_{-\infty}^{\infty} 
{f}(t) dt = 
\lim_{L\to\infty}
\sum_{k=-\infty}^{\infty}
\frac{\pi}{L} f(k\cdot\frac{\pi}{L})
$$

which leads,

$$
\begin{aligned}
f(t) 
&= 
\lim_{L\to\infty}\sum_{k=-\infty}^{\infty} 
\left(
\frac{1}{2L} \int_{-L}^{L}f(x)e^{-ikx\cdot \pi/L}
\cdot
e^{ikt\cdot \pi/L}
dx 
\right) \\
&=
\frac{1}{2\pi}
\lim_{L\to\infty}\sum_{k=-\infty}^{\infty} 
\frac{\pi}{L} 
\left(
\int_{-L}^{L}f(x)e^{-ikx\cdot \pi/L}
\cdot
e^{ikt\cdot \pi/L}
dx 
\right) \\
&=
\frac{1}{2\pi}
\int_{-\infty}^{\infty}
\left(
\int_{-\infty}^{\infty}f(x)e^{-ix\cdot \xi}
\cdot
e^{it\cdot \xi}
dx
\right)
d\xi \\ 
&=
\frac{1}{2\pi}
\int_{-\infty}^{\infty}
\left(
\int_{-\infty}^{\infty}f(x)e^{-ix\cdot \xi}
dx
\right) 
e^{it\cdot \xi}
d\xi \\
\end{aligned}
$$

Denote (Fourier transform)
$$
\hat {f}(\xi )
=
\int_{-\infty}^{\infty}f(x)e^{-ix\cdot \xi}
dx
$$
then (Inverse Fourier transform)
$$
f(t)
=
\frac{1}{2\pi}
\int_{-\infty}^{\infty}
\hat {f}(\xi )
e^{it\cdot \xi}
d\xi
$$

this is non-unitary, angular frequency form.

#### Fourier transform (unitary, oridnay frequency form)

For function $f\in L^1(\mathbb{R})$, 
i.e. $\int_{-\infty}^{\infty}|f(t)|dt < \infty$,
$$
\hat {f}(\xi )
=\int_{-\infty }^{\infty } f(t)e^{-2\pi i\xi t }\,dt
$$
with 
$\hat f\in L^1(\mathbb{R})$, i.e.
$\int_{-\infty}^{\infty}|f(\xi)|d\xi < \infty$.

Inverse Fourier transform
$$
{f}(t) = \int_{-\infty }^{\infty } \hat f(\xi)e^{2\pi it\xi }\,d\xi
$$

<!--
$\mathcal{F}(f)=\hat f$
-->

#### Derivatives.
$$
\int_{-\infty}^{\infty}f'(t)e^{-it\cdot \xi} dt
=
\left[ f(t)e^{-it\cdot \xi}\right]_{-\infty}^{\infty} - 
\int_{-\infty}^{\infty}f(t)(-i\xi)e^{-it\cdot \xi} dt
=
(i\xi)\int_{-\infty}^{\infty}f(t)e^{-it\cdot \xi} dt
$$
$$
\mathcal{F}(\frac{df(t)}{dt})
=
(i\xi)
\mathcal{F}(f(t))
$$

#### wave function
$$
u_{tt} = 
c^2 
u_{xx}
$$


#### Convolution
$$
(f*g)(x) = \int_{-\infty}^{\infty}f(\xi)g(x-\xi) d\xi
$$

$$
\mathcal{F}(f*g) = \mathcal{F}(f)\cdot\mathcal{F}(g) 
$$

$$
\begin{aligned}
\mathcal{F}(f*g) 
= &
\int_{-\infty}^{\infty}
\int_{-\infty}^{\infty}f(\xi)g(x-\xi) d\xi
e^{-ix\cdot t}
dx \\

= &
\int_{-\infty}^{\infty}
f(\xi)
\left(
\int_{-\infty}^{\infty}
g(x-\xi) 
e^{-ix\cdot t}
dx
\right)
d\xi \\

= &
\int_{-\infty}^{\infty}
f(\xi)
\left(
\int_{-\infty}^{\infty}
g(x-\xi) 
e^{-i(x-\xi)\cdot t}
d(x-\xi)
\right)
e^{-i\xi\cdot t}
d\xi \\

= &
\hat g(t)
\int_{-\infty}^{\infty}
f(\xi)
e^{-i\xi\cdot t}
d\xi \\

= &
\mathcal{F}(f)\cdot\mathcal{F}(g) \\
\end{aligned}
$$

#### Fast Fourier Transform (FFT)

#### Parseval's theorem
$$
\int_{-\infty}^{\infty}|\hat f(\xi)|^2d\xi =
2\pi \int_{-\infty}^{\infty}|f(t)|^2dt
$$