#### Definition

Scalar $\alpha \in \mathbf{R}$,

Vector $x \in \mathbf{R}^n,n\in\mathbf{N}$

Linearity $f: \mathbf{R}^n\mapsto\mathbf{R}^m$,
    $$
        f(\alpha \cdot x + \beta\cdot y ) = \alpha\cdot f(x) + \beta\cdot f(y)
    $$

Estimator

Bias
$$
    \operatorname{bias}(\hat y) = \operatorname{E}(\hat y) - y
$$
$\hat y$ unbiased if $\operatorname{bias}(\hat y) = 0$  

Mean Squared Error
$$
    MSE = \operatorname{E}((\hat y - y)^2) = \operatorname{bias}(\hat y)^2 + \operatorname{Var}(\hat y) 
$$

minimizing the mean squared error = maximum likelihood estimator

Moore-Penrose pseudoinverse
$$
    X^+ = \lim_{\alpha\to 0} (X^TX + \alpha I)^{-1}X^T 
$$

#### Probability

$P(y,x)$ represent the probability of $x$ and $y$ hanppend.

$P(y|x)$ represent the probability of $y$ while $x$ already known been happend.

Conditional Probability
$$
    P(y|x) = \frac{P(y,x)}{P(x)}
$$

If $x$ independent with $y$, then
$$
    P(y|x) = P(y), \quad P(y|x) = P(y,x)
$$

Bayes's Rule
$$
    P(x|y) = \frac{P(x)P(y|x)}{P(y)}
$$

Experience
$$
    \operatorname{E}(x_i) = \sum_i P(x_i)x_i
$$

$$
    \operatorname{E}(x) = \int_I P(x)x \operatorname{d} x
$$

Variance
$$
    \operatorname{Var}(x) = \operatorname{E}((x-\operatorname{E}(x))^2)
$$

Covariance
$$
    \operatorname{Cov}(x,y) = \operatorname{E}((x-\operatorname{E}(x))(y-\operatorname{E}(y)))
$$

Normal Distribution
$$
    \mathcal{N} (\mu,\sigma^2) = \sqrt{\frac{1}{2\pi\sigma^2}}e^{-\frac{1}{2\sigma^2}(\cdot-\mu)^2}
$$
If $x \sim \mathcal{N}(\mu,\sigma^2)$, then $\operatorname{E}(x) = \mu$, $\operatorname{Var}(x) = \sigma^2$.

Logistic sigmoid
$$
    s(x) = \frac{1}{1+e^{-x}}
$$

Softplus function
$$
    \zeta(x) = \operatorname{log}(1+e^{x})
$$

Softmax
$$
    \sigma(x)_i = \frac{e^{x_i}}{\sum_j e^{x_j}}
$$

$L^p$ norm
$$
    ||x||_p = \left(\sum_i |x_i|^p\right)^{\frac{1}{p}}
$$

#### XOR
Linear model cannot perform XOR operation
$$
    f(x,W,c,w,b) = w^T\cdot max(0,W^Tx+c) + b
$$
$$
    f\left(\begin{bmatrix}
        0 & 0 \\
        0 & 1 \\
        1 & 0 \\
        1 & 1 
    \end{bmatrix}\right)
    =
    \begin{bmatrix}
        0 \\
        1 \\
        1 \\
        0
    \end{bmatrix}
$$
$$
    W = 
    \begin{bmatrix}
        1 & 1 \\
        1 & 1 
    \end{bmatrix}
    , \quad
    c = 
    \begin{bmatrix}
        0 \\
        -1
    \end{bmatrix}
    , \quad
    w = 
    \begin{bmatrix}
        1 \\
        -2 
    \end{bmatrix}
    ,\quad
    b = 0
$$


#### General Problem
For a data-set with $N$ samples
$$
(x_{i},y_{i}) 
\in \mathbf{R}^n\times\mathbf{R}^m,\quad
i\in\mathbf{N},
$$
$$
    f : \mathbf{R}^n \mapsto \mathbf{R}^m
$$
$\hat y=f(x)$ 
$$
    ||\hat y-y||_2^2 = \sum_{i} (\hat y_i-y_i)^2
$$

#### Linear Case
Module
$ x \in \mathbf{R}^n, $
$ w \in \mathbf{R}^n\times\mathbf{R}^m, $
$ y \in \mathbf{R}^m, $
$ b \in \mathbf{R}^m, $

$$
    \hat y = f(x) = x\cdot w + b
$$

#### Likelihood function
Likelihood is the probability that a particular outcome $x$ is observed when the true value of the parameter is $\theta$,
$$ 
{\mathcal {L}}(\theta \mid x)=p_{\theta }(x)=P_{\theta }(X=x)
$$

Unlike probabilities, likelihood function do not have to integrate (or sum) to 1.

#### Probability density function

#### Cross entropy
Entropy 
$$
    H(X) = -\sum_{x\in X} P(x)\operatorname{log} P(x)
$$
Uniform probability yields maximum uncertainty and therefore maximum entropy.

The Kullback–Leibler divergence (relative entropy) was introduced as the directed divergence between two distributions
$$
    D_{\text{KL}}(P\parallel Q)=-\sum _{x\in {\mathcal {X}}}P(x)\log \left({\frac {Q(x)}{P(x)}}\right)
$$

The cross entropy of the distribution $q$ relative to a distribution $p$ over a given set is defined as follows:
$$
    H(p,q)=-\operatorname{E} _{p}[\log q] = -\sum p\log q =  H(p)+D_{\mathrm {KL} }(p\|q)
$$

#### Quadratic Problem
$$
F(x) = \frac{1}{2}xwx^T - bx
$$

$$
\nabla F(x) = xw - b
$$

$$
\nabla^2 F(x) = w
$$

$w$ is invertable,

$$
x_1 = x_0 - \nabla F(x_0) (\nabla^2 F(x_0) )^{-1} 
    = x_0 - (x_0w-b)w^{-1} 
    = bw^{-1} 
    = x^*
$$

$$
{\hat w}={\underset w {\operatorname {arg\,min} }}\,S(w)
$$
