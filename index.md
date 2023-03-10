# Difference between Influence Function definition in PFD and Percy's
## Notation in our formulation
Let $X = \set{ x_1, x_2, \dots, x_n}$ be the space of all training point. Let $\mathcal{P}$ be the convex set of all Borel probability measure on the space $X$, $\mu \in \mathcal{P}$, $\chi \in \mathcal{P}$. By default, in our setting $\mu$ is a uniform probability measure, that is $\mu(x) = \frac{1}{n}$ for all $x \in X$. Let $x_t$ be the test point, $L$ be the loss function, $\hat{\theta}$ be the model parameter that minimize training loss on $x_i$. Let $J(\mu)$ be a functional such that $$J(\mu) = L(x_t; \hat{\theta} := argmin_{\theta} (\sum_i\mu(x_i)*L(x_i, \theta))$$

## Influence function definition in PFD under our formulation
Let $J: \mathcal{P}(X) \longrightarrow \mathbb{R}$. Then $\psi: X \longrightarrow \mathbb{R}$ is an influence function of $J$ at $\mu$ if and only if $$\frac{d}{d\epsilon} J(\mu + \epsilon\chi)|_{\epsilon=0} = \int_X \psi(x) d\chi$$

## Influence function definition in Percy's under our formulation
$\mathcal{I}(x_i, x_t)$ is defined as the influence of training point $x_i$ on the test point $x_t$. The key idea is that let $\hat{\theta_\epsilon} = argmin_\theta \frac{1}{n}\sum_{i} L(z_i, \theta) + \epsilon L(z, \theta)$ where $z$ is the training point of interest and we want to calculate $\frac{dL(x_t, \hat{\theta_\epsilon})}{d\epsilon}$ where $\epsilon = 0$. 

## Equivalence between $J(\mu)$ and $L(x_t, \hat{\theta})$
We can identify that the only difference between $J(\mu)$ in our formulation and $L(x_t, \hat{\theta_\epsilon})$ is the difference between $\hat{\theta}$. In our formulation, $\hat{\theta} = argmin_{\theta} (\sum_i\mu(x_i)*L(x_i, \theta))$. In Percy's, $\hat{\theta_\epsilon} = argmin_\theta \frac{1}{n}\sum_{i} L(z_i, \theta) + \epsilon L(z, \theta)$. So, if we let $\mu(x) = \frac{1}{n} + \epsilon$ for the target training point $x$, and $\mu(x_i) = \frac{1}{n}$ for all other training points. We will be able to build the equivalence.

## Equivalence between PFD and Percy's Influence function under our formulation

