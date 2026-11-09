# Kullback-Leibler Divergence

p.34 2.45

$$
D_{KL}[p(x) || q(x)] \equiv E_{X \sim p(x)}[\log p(x) - \log q(x)]
$$

## Interpretation:

p.55 section 1.6.1 Bishop

We are transmitting X over a channel where X has probability distribution p, but we have used distribution q to construct our code. We will be transmitting an extra $D_{KL}[p||q]$ bits.

## Reference

David MacKay, Information Theory, Inference, and Learning Algorithms
