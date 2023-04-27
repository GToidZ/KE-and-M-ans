# Slide Answers (27/04/23)
## Exercise 2
Node B:
|$P(b)$|$P(\neg b)$|
|:-:|:-:|
|||

Node A:

Use a PDF (probability density function): 
```math
N(\mu,\sigma^2)(a)
```

Node C:
```math
P(c|a,b) = N(a_th+b_t,\sigma_t^2)(c)=\frac{1}{\sigma_t\sqrt{2\pi}e}^{-\frac{1}{2}(\frac{c-(a_th+b_t)}{\sigma_t})^2}
```
```math
P(c|a,\neg b) = N(a_fh+b_f,\sigma_f^2)(c)=\frac{1}{\sigma_f\sqrt{2\pi}e}^{-\frac{1}{2}(\frac{c-(a_fh+b_f)}{\sigma_f})^2}
```
