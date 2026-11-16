# Policy Gradients

$$
J(\theta) = E_{\tau \sim p_\theta(\tau)}[v(\tau)]
$$


where

$$
v(\tau) = \sum_{t=0}^\infty \nu^t r_t
$$

and $\tau$ is a trajectory, $(s_0,a_0,r_0,s_1,a_1,r_1,,s_2,a_2,r_2,...)$


We wish to compute:

$$
\nabla_\theta[J(\theta)]
$$

$$
\nabla_\theta[E_{\tau \sim p_\theta(\tau)}[v(\tau)]]
$$

By Reinforce:

$$
= E_{\tau \sim p_\theta(\tau)}[v(\tau) \nabla_\theta[\log(p(\tau)]]
$$

$$
p_\theta(\tau) = p(s_0) \pi_\theta(a_0|s_0) p(r_0|s_0) \prod_{t=1}^T p(s_t|s_{t-1},a_{t-1}) \pi_\theta(a_t|s_t) p(r_t|s_t)
$$

$$
\log(p_\theta(\tau)) = \log(p(s_0)) + \log(\pi_\theta(a_0|s_0)) +
\log(p(r_0|s_0)) + \\
\sum_{t=1}^T \log(p(s_t|s_{t-1},a_{t-1})) + 
\log(\pi_\theta(a_t|s_t)) + \log(p(r_t|s_t))
$$

$$
\nabla_\theta[\log(p_\theta(\tau)] = \sum_{t=1}^T \nabla_\theta[\log(\pi_\theta(a_t|s_t))]
$$

$$
\nabla_\theta[J(\theta)] =
E_{\tau \sim p_\theta(\tau)}[v(\tau) \sum_{t=0}^T \nabla_\theta[\log(\pi_\theta(a_t|s_t))]
$$
