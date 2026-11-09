# Variational Autoencoder

$$
E_{x \sim p_{(x)}}[\log p_\theta(x)]
$$

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z)}[\log p_\theta(x)]]
$$

Using Bayes Rule (rearranged):

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z)}[\log \frac{p_\theta(x|z) p_\theta(z)}{p_\theta(z|x)}]]
$$

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z)}[\log \frac{p_\theta(x|z) p_\theta(z)}{p_\theta(z|x)} \frac{q_\phi(z)}{q_\phi(z)}]]
$$

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z)}[\log p_\theta(x|z)] + E_{z \sim q_\phi(z)}[\log \frac{p_\theta(z)}{q_\phi(z)} ] + E_{z \sim q_\phi(z)}[\log \frac{q_\phi(z)}{p_\theta(z|x)}]]
$$

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z)}[\log p_\theta(x|z)] - D_{KL}[q_\phi(z)||p_\theta(z)] + D_{KL}[q_\phi(z)||p_\theta(z|x)]]
$$

First two terms are ELBO.

Note, we generally make $q_\phi(z)$ depend on x, so rewrite as $q_\phi(z|x)$

So above becomes:

$$
= E_{x \sim p_{(x)}}[E_{z \sim q_\phi(z|x)}[\log p_\theta(x|z)] - D_{KL}[q_\phi(z|x)||p_\theta(z)] + D_{KL}[q_\phi(z|x)||p_\theta(z|x)]]
$$

If we rearrange we can see what we are in fact optimizing:

$$
elbo = E_{x \sim p_{(x)}}[\log p_\theta(x)] - D_{KL}[q_\phi(z|x)||p_\theta(z|x)]]
$$


## Discussion

If our objective is a good generative model then presumably we would want to minimize $D_{KL}[p(x)||p_\theta(x)]$, but our above result suggests our VAE objective may trade this off with minimizing $D_{KL}[q_\phi(z)||p_\theta(z|x)]$. So a poor q(z|x) may lead to a suboptimal generative model.

## References

Failure Modes of Variational Autoencoders and Their Effects on Downstream Tasks, Yacoby, Pan, Doshi-Velez (2022), [https://arxiv.org/pdf/2007.07124]
