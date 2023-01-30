# Difference between Influence Function definition in PFD and Percy's
## Notation in our formulation
Let $X = \set{ x_1, x_2, \dots, x_n}$ be the space of all training point. Let $\mathcal{P}$ be the convex set of all Borel probability measure on the space $X$, $\mu \in \mathcal{P}$, $\chi \in \mathcal{P}$. By default, in our setting $\mu$ is a uniform probability measure, that is $\mu(x) = \frac{1}{n}$ for all $x \in X$. Let $x_t$ be the test point, $L$ be the loss function, $\hat{\theta}$ be the model parameter that minimize training loss on $x_i$. Let $J(\mu)$ be a functional such that $$J(\mu) = L(x_t; \hat{\theta_3} := argmin_{\theta_3} (\sum_i\mu(x_i)*L(x_i, \theta_3))$$

## Influence function definition in PFD under our formulation
Let $J: \mathcal{P}(X) \longrightarrow \mathbb{R}$. Then $\psi: X \longrightarrow \mathbb{R}$ is an influence function of $J$ at $\mu$ if and only if $$\frac{d}{d\epsilon} J(\mu + \epsilon\chi)|_{\epsilon=0} = \int_X \psi(x) d\chi$$
