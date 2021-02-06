# multiresolution

Any wavelet generate a direct sum decomposition of $L^2(\mathbb{R})$.

For each $j\in\mathbb{Z}$, the cloased subspaces, 
$$
V_j = V_{j-1} \oplus W_{j-1} = \cdots \oplus W_{j-2} \oplus W_{j-1}
$$
These subspaces clearly have the following properties:
* $V_{j-1} \sub V_{j} $
* $\cap V_j = \{0\} $
* $\overline{\cup V_j} = L^2(\mathbb{R}) $
* $f \in V_j \iff f(2^{-j}\cdot) \in V_{0}$
* if $\phi\in V_0$, then $\{\phi(\cdot-k)\}_{k\in\mathbb{Z}}$ constitute an orthonomal basis for $V_0$.