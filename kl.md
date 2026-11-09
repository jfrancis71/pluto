# Kullback-Leibler Divergence

p.34 2.45

$$
D_{KL}[p(x) || q(x)] \equiv E_{X \sim p(x)}[\log p(x) - \log q(x)]
$$

## Interpretation:

p.55 section 1.6.1 Bishop

We are transmitting X over a channel where X has probability distribution p, but we have used distribution q to construct our code. We will be transmitting an extra $D_{KL}[p||q]$ bits.

## Curious Aside

p.140 8.12, MacKay

$$
D_H[X,Y] \equiv H[X,Y] - I[X;Y]
$$

It is a distance metric and symmetric. MacKay sees no application of it, but I include it here as I find it curious.


## Reference

David MacKay, Information Theory, Inference, and Learning Algorithms
