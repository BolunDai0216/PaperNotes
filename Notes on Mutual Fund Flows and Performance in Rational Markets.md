# **Notes on Mutual Fund Flows and Performance in Rational Markets**

Bolun Dai (bd1555@nyu.edu)

## The Model

- **The model produces two central behaviors**

- - **Flows that are responsive to performance**
  - **Performance that is not persistent**

The return (in percentage) in excess of the passive benchmark on actively managed funds without cost and fees is denoted as:
$$
R_t = \alpha + \epsilon_t,
$$
where $\alpha$ is the source of differential ability across managers and the error term $\epsilon_t$ is normally distributted with mean zero and variance $\sigma^2$.



When managing a fund to achieve high returns the manager needs to expend resources and pay bid-ask fees, if we denote the costs incurred when actively managing a fund of size $q_t$ as $C(q_t)$. The managers are paid a fixed management fee $f$ denoted as a fraction of the assets under management $q_t$.



The excess total payout (in dollar) to investors over what would be earned on the passive benchmark is
$$
TP_{t+1} = q_tR_{t+1} - C(q_t) - q_tf,
$$
the excess return (in percentage) over the benchmark is
$$
r_{t+1} = \frac{TP_{t+1}}{q_t} = R_{t+1} - \frac{C(q_t)}{q_t} - f = R_{t+1} - c(q_t),
$$
where the unit cost associated with investing in the actively managed fund is
$$
c(q_t) \equiv \frac{C(q_t)}{q_t} + f.
$$


At the birth of the fund the participant's prior about the ability of the fund management is that $\alpha$ is normally distributed with mean $\phi_0$ and variance $\eta^2$. By observing the history $\{r_s, q_s\}_{s=0}^t$  investors can infer the history $\{R_s\}_{s=0}^t$. We have the posterior mean of management ability at time $t$ as,
$$
\phi_t \equiv \mathbb{E}[R_{t+1}\ |\ R_1, \cdots, R_t].
$$


##  **The Flow of Funds and Performance**

We assume the expected excess return to invest in any surviving fund is zero $\mathbb{E}_t[r_{t+1}] = 0$.  And we have,
$$
\begin{align}
	\mathbb{E}_t[r_{t+1}] &= \mathbb{E}_t[R_{t+1} - c(q_t)]\\
	                    0 &= \mathbb{E}_t[R_{t+1}] - \mathbb{E}_t[c(q_t)]\\
	                      &= \phi_t - c(q_t)
\end{align}
$$
which gives us
$$
\phi_t = \frac{C(q_t)}{q_t} + f.
$$
 We can see that as performance $\phi_t$ changes the asset under management $q_t$ changes.



> **Proposition 1**: *For any fund in operation at dates $t-1$ and $t$, the evolution of $\phi_t$ and the change in the amount of money under management at any date, as a function of the prior performance, are given by the solutions to*
> $$
> \phi_t = \phi_{t-1} + \frac{\omega}{\gamma + t\omega}r_t
> $$
> *and*
> $$
> c(q_t) = c(q_{t-1}) + \frac{\omega}{\gamma + t\omega}r_t.
> $$

This is just saying that good performance results in inflow of funds, while bad performance causes outflow of funds. And for younger funds the performance will cause a more dramatically response in fund flows.



### Efficient Provision of Portfolio Management Service

Let the fee managers charge at each time be defined as $f_t$ and we have
$$
q_t\phi_t - C(q_t) = q_tf_t
$$
by choosing the optimal $q_t$, denoted as $q_t^*(\phi_t)$, for the manager we can have
$$
\phi_t = C'(q_t).
$$
This is done by choosing the level of $q_t$ that maximizes $q_t\phi_t - C(q_t)$ (take the derivative w.r.t $q_t$ and set it to 0). Then the manager selects $f_t^*$ to ensure that the investors invest  $q_t^*(\phi_t)$
$$
f_t^* = \phi_t - \frac{C(q_t^*(\phi_t))}{q_t^*(\phi_t)}.
$$
This is the best for both the manager and the investor, which is also called Pareto efficient.



If we allow managers to index funds we have $q_t$ being the total amount of money under management, $q_t^*(\phi_t)$ being the amount of money that is actively managed and $q_{It}$ being the amount of money that is indexed. Because the amount of money that is indexed does not contribute to the costs $C(\cdot)$, due to it not being able to generate excess returns compared to the passive benchmark, we have
$$
r_{t+1} = \frac{q_t^*(\phi_t)}{q_t}R_{t+1} - \frac{C(q_t^*(\phi_t))}{q_t} - f = h(q_t)R_{t+1} - c(q_t).
$$
By taking an expectation on both sides and letting $\mathbb{E}_t[r_{t+1}] = 0$ we can have
$$
h(q_t)\phi_t = c(q_t),
$$
which we can write out as
$$
\begin{align}
	\frac{q_t^*(\phi_t)}{q_t}\phi_t &= \frac{C(q_t^*(\phi_t))}{q_t} + f\\
	            q_t^*(\phi_t)\phi_t &= C(q_t^*(\phi_t)) + fq_t\\
  q_t^*(\phi_t)\phi_t - C(q_t^*(\phi_t)) &= [q_t^*(\phi_t) + q_{It}]f
\end{align}
$$
which from $q_t\phi_t - C(q_t) = q_tf_t$ we can have
$$
q_t^*(\phi_t)f_t^* = [q_t^*(\phi_t) + q_{It}]f
$$
and we have the amount of money that is indexed as
$$
q_{It} = q_t^*(\phi_t)\frac{f_t^* - f}{f}.
$$
This gives us the fixed fee contract
$$
q_t = q_t^*(\phi_t) + q_{It} = \frac{q_t^*(\phi_t)\phi_t - C(q_t^*(\phi_t))}{f},
$$
which following ***proposition 1*** has the following update rule
$$
\begin{align}
	\phi_t &= \phi_{t-1} + \frac{r_t}{h(q_{t-1})}\frac{\omega}{\gamma+t\omega}\\
	\frac{c(q_t)}{h(q_t)} &= \frac{c(q_{t-1})}{h(q_{t-1})} + \frac{r_t}{h(q_{t-1})}\frac{\omega}{\gamma+t\omega}.
\end{align}
$$


### Entry and Exit of Funds

We assume that the manager incur known fixes costs $F$, and let $\bar{\phi}$ be the lowest expectation of management ability for which the manager still stays in business. We can have
$$
q_t^*(\bar{\phi})\bar{\phi} - C(q_t^*(\bar{\phi})) = F,
$$
when $\phi_t < \bar{\phi}$ the fund shuts down.



## Cross-Sectional Distribution of Managerial Talent

Let $G_t(\phi)$ be the probability, conditioned on the funds survival through period $t$, that the perceived talent of the manager at $t$, $\phi_t$ is less than $\phi$. We first consider the joint probability that a fund is born at time $0$ and survives through period $t$ and has $\phi_t<\phi$, which we denote as $\hat{G}_t(\phi)$. Let $g_t(\phi) \equiv dG_t(\phi)/d\phi$ and $\hat{g}_t(\phi) \equiv d\hat{G}_t(\phi)/d\phi$ be the corresponding probability density functions.



We begin by conditioning on $\alpha$, the actual talent of the manager. Let $\hat{G}_t^\alpha(\phi)$ be the probability conditioned on having a manager with talent $\alpha$, that the fund survives through period $t$ and, at time $t$, the perceived talent of the manager is less than or equal to $\phi$, and we have $\hat{g}_t^\alpha(\phi) \equiv d\hat{G}_t^\alpha(\phi)/d\phi$ be the corresponding probability density function.



> **Proposition 2**: *Suppose that a manager with true ability $\alpha$ begins operating a time $0$ when the market's prior on her ability is $\phi_0$. Then $\hat{g}_t^\alpha(\phi)$ is defined recursively as*
> $$
> \hat{g}_t^\alpha(\phi) = \frac{\gamma + t\omega}{\omega}\int_{\bar{\phi}}^{\infty}{\hat{g}_t^\alpha(v)n^\alpha\Big(\frac{\gamma + t\omega}{\omega}\phi - \frac{\gamma + (t-1)\omega}{\omega}\Big)dv},
> $$
> *with the boundary condition*
> $$
> \hat{g}_1^\alpha(\phi) = \frac{\gamma + \omega}{\omega}n^\alpha\Big(\frac{\gamma + \omega}{\omega}(\phi - \phi_0) + \phi_0\Big),
> $$
> *and $n^\alpha(\cdot)$ is a normal density function with mean $\alpha$ and precision $\omega$.*



Then we can have the joint probability pooling all types $\hat{G}_t$ (the talent of the manager $\alpha$ can be any number).



> **Proposition 3**: *Suppose that a fund begins operation at time $0$ when the market's prior on the fund manager's ability is $\phi_0$. Then*
> $$
> \hat{g}_t(\phi) = \int_{-\infty}^{\infty}{\hat{g}_t^u(\phi)n^{\phi_0}(u)du},
> $$
> *and*
> $$
> \hat{G}_t(\phi) = \int_{\bar{\phi}}^{\phi}{\hat{g}_t(u)du},
> $$
> *where $n^{\phi_0}(u)$ is a normal distribution with mean $\phi_0$ and precision $\gamma$.*



The distribution of $\phi_t$, conditioned on survival through date $t$, can now be computed directly using, 
$$
G_t(\phi) = \frac{\displaystyle\int_{\bar{\phi}}^{\phi}{\hat{g}_t(u)du}}{\displaystyle\int_{\bar{\phi}}^{\infty}{\hat{g}_t(u)du}}
$$
with the corresponding density function
$$
g_t(\phi) = \frac{\hat{g}_t(\phi)}{\displaystyle\int_{\bar{\phi}}^{\infty}{\hat{g}_t(u)du}}.
$$

> **Proposition 4**: The unconditional probability that a fund that starts at time 0 survives through period $t$ is
> $$
> P_t = \int_{\bar{\phi}}^{\infty}{\hat{g}_t(\phi)d\phi = \hat{G}(\infty)}
> $$
> and the unconditional probability that a fund shuts down in period $t$ is $P_{t-1} - P_t$, where $P_0 = 1$.



## Parameterization

### Parametric Cost Function

 Assume $C(q) = aq^2$ and $q_{It} > 0$ we have
$$
q_t^*(\phi_t) = \frac{\phi_t}{2a}
$$
and the total amount of money under management is
$$
q_t = \frac{\phi_t^2}{4af}.
$$
And we can have the amount of money under active management as
$$
h(q_t) = \sqrt{\frac{f}{aq_t}}
$$
which gives us
$$
\frac{c(q_t)}{h(q_t)} = 2\sqrt{aq_tf}.
$$
And now we have the percentage change in funds at time $t$ as a function of the manager's performance:
$$
\frac{q_t - q_{t-1}}{q_t} = \frac{r_t}{f}\Big(\frac{\omega}{\gamma + t\omega}\Big) + \frac{r_t^2}{4f^2}\Big(\frac{\omega}{\gamma + t\omega}\Big)^2.
$$




