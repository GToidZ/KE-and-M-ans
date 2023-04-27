Will come back to work on remaining questions, I can't keep up lol.
# Slide Answers (27/04/23)
## Exercise 2
Node B (which has a boolean value):
|$P(b)$|$P(\neg b)$|
|:-:|:-:|
|||

Node A (which has a continuous value):

Use a PDF (probability density function): 
```math
N(\mu,\sigma^2)(a)
```

Node C (parents are discrete and continuous):
```math
P(c|a,b) = N(a_th+b_t,\sigma_t^2)(c)=\frac{1}{\sigma_t\sqrt{2\pi}e}^{-\frac{1}{2}(\frac{c-(a_th+b_t)}{\sigma_t})^2}
```
```math
P(c|a,\neg b) = N(a_fh+b_f,\sigma_f^2)(c)=\frac{1}{\sigma_f\sqrt{2\pi}e}^{-\frac{1}{2}(\frac{c-(a_fh+b_f)}{\sigma_f})^2}
```

## Exercise 3
![image](https://user-images.githubusercontent.com/39559733/234791822-c9755072-5b88-405d-ad0c-b32632b3a171.png)

## Exercise 4
![image](https://user-images.githubusercontent.com/39559733/234791946-ebc0d05a-74af-4f82-a7f9-06f30afcd20d.png)


## Exercise 5
5.1 
```math
P(c,d) = \sum_A\sum_B\sum_EP(d)*P(B)*P(A|B,d)*P(E)*P(c|A,E)
```

5.2
```math
P(a|\neg b,c) = \alpha*\sum_D\sum_EP(\neg b)*P(D)*P(E)*P(a|\neg b,D)*P(c|a, E)
```
```math
P(\neg a|\neg b,c) = \alpha*\sum_D\sum_EP(\neg b)*P(D)*P(E)*P(\neg a|\neg b,D)*P(c|\neg a, E)
```

## Exercise 6
6.1
```math
P(\neg a,e,f) = \sum_B\sum_C\sum_DP(\neg a)*P(B|\neg a)*P(e|B)*P(C|B)*P(D|C)*P(f|\neg a,D,e)
```

6.2
```math
P(c|a,\neg d,f) = \alpha*\sum_B\sum_EP(a)*P(B|a)*P(E|B)*P(c|B)*P(\neg d|c)*P(f|a,\neg d,E)
```
```math
P(\neg c|a,\neg d,f) = \alpha*\sum_B\sum_EP(a)*P(B|a)*P(E|B)*P(\neg c|B)*P(\neg d|\neg c)*P(f|a,\neg d,E)
```

## Exercise 7
```math
\begin{aligned}
P(b|\neg e, f) &= \alpha*\sum_AP(A)*P(f)*P(b|A)*P(\neg e|b,f) \\
P(\neg b|\neg e, f) &= \alpha*\sum_AP(A)*P(f)*P(\neg b|A)*P(\neg e|\neg b,f)
\end{aligned}
```
```math
\begin{aligned}
P(b|\neg e, f) &= \alpha * P(f) * P(\neg e|b,f) * \sum_AP(A) * P(b|A) \\
&= \alpha * 0.4 * 0.2 * \left[ 
\begin{aligned}
&^{A=T}0.7 * 0.2 \\
&+ \\
&^{A=F}0.3 * 0.6
\end{aligned}
\right] \\
&= a * 0.0256
\end{aligned}
```
```math
\begin{aligned}
P(\neg b|\neg e, f) &= \alpha * P(f) * P(\neg e|\neg b,f) * \sum_AP(A) * P(\neg b|A) \\
&= \alpha * 0.4 * 0.6 * \left[ 
\begin{aligned}
&^{A=T}0.7 * 0.8 \\
&+ \\
&^{A=F}0.3 * 0.4
\end{aligned}
\right] \\
&= a * 0.1632
\end{aligned}
```

Eliminate $\alpha$:
```math
\begin{aligned}
P(b|\neg e,f) &= \frac{0.0256}{0.0256+0.1632} = 0.1355 \\
P(\neg b|\neg e,f) &= 0.8645
\end{aligned}
```

## Exercise 8
We can use Markov Blanket to find the probability distribution,

We are interested in Node B.

Markov Blanket of B: Node A, Node C, Node D.

The states are: $A=True,B=False,C=True,D=True,E=False$.

From network, we need to find: $P(B|a,c,d)$

```math
\begin{aligned}
P(b|a,c,d) &= \alpha*P(a)*P(d)*P(b|a)*P(c|b,d) \\
P(\neg b|a,c,d) &= \alpha*P(a)*P(d)*P(\neg b|a)*P(c|\neg b,d)
\end{aligned}
```

```math
\begin{aligned}
P(b|a,c,d) &= \alpha * P(a) * P(d) * P(b|a) * P(c|b,d)\\
&= \alpha * 0.6 * 0.7 * 0.7 * 0.3 \\
&= a * 0.0882
\end{aligned}
```

```math
\begin{aligned}
P(\neg b|a,c,d) &= \alpha * P(a) * P(d) * P(\neg b|a) * P(c|\neg b,d)\\
&= \alpha * 0.6 * 0.7 * 0.3 * 0.2 \\
&= a * 0.0252
\end{aligned}
```

Eliminate $\alpha$ with $\frac{1}{P(b|a,c,d) + P(\neg b|a,c,d)}$
```math
\begin{aligned}
P(b|a,c,d) &= \frac{0.0882}{0.0882+0.0252} = 0.778 \\
P(\neg b|a,c,d) &= 0.223
\end{aligned}
```

## Exercise 9
TODO: Complete the thing.

We want to find $P(P|h,g,\neg v)$.

```math
\begin{aligned}
P(p|h,g,\neg v) &=
\alpha*P(g)*
  \left[
    \begin{aligned}
    &^{M=T} P(m) * P(\neg v|m,g) * P(h|m,g) \\
    &+ \\
    &^{M=F} P(\neg m) * P(\neg v|\neg m,g) * P(h|\neg m,g)
    \end{aligned}
  \right] *
  \left [
    \begin{aligned}
    &^{R=T} P(r|g) * P(p|v,h,r)\\
    &+ \\
    &^{R=F} P(\neg r|g) * P(p|v,h,\neg r)
    \end{aligned}
  \right] 
\\
&= \alpha*P(g)*
  \left[
    \begin{aligned}
    &^{M=T} 0.7 * 0.9 * 0.2 \\
    &+ \\
    &^{M=F} 0.3 * 0.7 * 0.4
    \end{aligned}
  \right] *
  \left [
    \begin{aligned}
    &^{R=T} 0.2 * 0.9\\
    &+ \\
    &^{R=F} 0.8 * 0.7
    \end{aligned}
  \right]  \\
&= a*0.05712
\end{aligned}
```
