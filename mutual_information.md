# Mutual Information

$$
I(X,Y) \equiv D_{KL}[p(x,y)||p(x) p(y)]
$$


figure 8.1, p. 140, 
Note, I have added H[X,Y] = H[X] + H[Y|X]. Am I correct to do so?

```mermaid
block-beta
columns 4
a["H[X,Y]"]:4
b["H[X]"]:3 c["H[Y|X]"]:1
d["H[X|Y]"]:1 e["H[Y]"]:3
f["H[X|Y]"]:1 g["I[X,Y]"]:2 h["H[Y|X]"]:1
```

Reference:
David Mackay, Information Theory, Inference, and Learning Algorithms.
