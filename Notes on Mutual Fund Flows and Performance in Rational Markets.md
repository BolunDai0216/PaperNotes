# **Notes on Mutual Fund Flows and Performance in Rational Markets**

**Authors: Jonathan B. Berk and Richard C. Green**

Notes by Bolun Dai (bd1555@nyu.edu)

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
\begin{align}
	\frac{d(q_t\phi_t - C(q_t))}{dq_t} &= 0\\
	\phi_t - C'(q_t) &= 0\\
	\phi_t &= C'(q_t)
\end{align}
$$
This is done by choosing the level of $q_t$ that maximizes $q_t\phi_t - C(q_t)$ (take the derivative w.r.t $q_t$ and set it to 0). Then the manager selects $f_t^*$ to ensure that the investors invest  $q_t^*(\phi_t)$
$$
f_t^* = \phi_t - \frac{C(q_t^*(\phi_t))}{q_t^*(\phi_t)}.
$$
This is the best for both the manager and the investor, which is also called Pareto efficient. Because $\phi_t$ depends on the history instead of the present performance the compensation also only depends on the history.



**But using a fix fee we can achieve the same compensation! If we let the managers to index funds.**



If we allow managers to index funds we have $q_t$ being the total amount of money under management, $q_t^*(\phi_t)$ being the amount of money that is actively managed and $q_{It}$ being the amount of money that is indexed. Because the amount of money that is indexed, it does not contribute to the costs $C(\cdot)$, due to it not being able to generate excess returns compared to the passive benchmark (but the management fee is still payed on the indexed funds), we have
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
q_t^*(\phi_t)\phi_t - C(q_t^*(\phi_t)) = q_t^*(\phi_t)f_t^* = [q_t^*(\phi_t) + q_{It}]f
$$
*which confirms that under both a variant-fee and a fixed-fee contract the manager can earn the same amount of compensation simply by avoiding the cost when indexing part of the fund*. And we have the amount of money that is indexed as
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

Here the word fund is talking mutual funds instead of capital.



We assume that the manager incur known fixes costs $F$ (operation cost of the fund), and let $\bar{\phi}$ be the lowest expectation of management ability for which the manager still stays in business. We can have
$$
q_t^*(\bar{\phi})\bar{\phi} - C(q_t^*(\bar{\phi})) = F,
$$
when $\phi_t < \bar{\phi}$ the fund shuts down.

- **Question: Even though $q_t^*(\bar{\phi})\bar{\phi} - C(q_t^*(\bar{\phi}))$ is not a function of $f$ but shouldn't it be equal to $q_tf$ thus be related to the fee?**



## Cross-Sectional Distribution of Managerial Talent

The analysis above is concerned about a *single manager*. However, the empircal analysis is with regard to an *age cohort*.



Let $G_t(\phi)$ be the probability, conditioned on the funds survival through period $t$, that the perceived talent of the manager at $t$, $\phi_t$ is less than $\phi$. We first consider the joint probability that a fund is born at time $0$ and survives through period $t$ and has $\phi_t<\phi$, which we denote as $\hat{G}_t(\phi)$. Let $g_t(\phi) \equiv dG_t(\phi)/d\phi$ and $\hat{g}_t(\phi) \equiv d\hat{G}_t(\phi)/d\phi$ be the corresponding probability density functions.



The reason we have this is that according to Bayes' rule we have
$$
P(A\ |\ B) = \frac{P(B\ |\ A)P(A)}{P(B)} = \frac{P(A\cap B)}{P(B)}
$$
where $P(A\cap B)$ represents the joint probability of $A$ happening and $B$ happening. In our case we have $A$ being the perceived talent of the manager at $t$, $\phi_t$ is less than $\phi$, and $B$ being the funds survival through period $t$. And we have
$$
\begin{align}
	G_t(\phi) &= P(A\ |\ B)\\
	\hat{G}_t(\phi) &= P(A\cap B).
\end{align}
$$
We begin by conditioning on $\alpha$, the actual talent of the manager. Let $\hat{G}_t^\alpha(\phi)$ be the probability conditioned on having a manager with talent $\alpha$, that the fund survives through period $t$ and, at time $t$, the perceived talent of the manager is less than or equal to $\phi$, and we have $\hat{g}_t^\alpha(\phi) \equiv d\hat{G}_t^\alpha(\phi)/d\phi$ be the corresponding probability density function. Here we have 
$$
\hat{G}_t^\alpha(\phi) = P(A\cap B\ |\ \alpha).
$$
First we have the following proposition that defines how to calculate $\hat{g}_t^\alpha(\phi)$.



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



This is saying the talent of the manager can be any number, however the perceived talent has to be in $[\bar{\phi},\ \phi]$.



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



This unconditional probabilty is just the probability that the perceived talent is larger than $\bar{\phi}$ at time $t$.



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
And now we have the **percentage change in funds at time $t$ as a function of the manager's performance**:
$$
\frac{q_t - q_{t-1}}{q_t} = \frac{r_t}{f}\Big(\frac{\omega}{\gamma + t\omega}\Big) + \frac{r_t^2}{4f^2}\Big(\frac{\omega}{\gamma + t\omega}\Big)^2.
$$



If the excess return is below a critical realization $r^*(\phi_{t-1})$ defined as
$$
r^*(\phi_{t-1}) = (\bar{\phi} - \phi_{t-1})h(q_{t-1})\frac{\gamma + t\omega}{\omega} = 2\Big(\frac{\bar{\phi} - \phi_{t-1}}{\phi_{t-1}}\Big)\Big(\frac{\gamma + t\omega}{\omega}\Big)f
$$
the market's posterior on the maneger's ability falls to $\bar{\phi}$, if the return is lower than the critial realization all of the funds will leave and the change in AUM will be $-1$.



In summary we have the **overall change in the assets under management** given by
$$
\frac{q_t - q_{t-1}}{q_{t-1}} = \begin{cases}
	-1 & \mathrm{if}\ r_t < \displaystyle2\Big(\frac{\bar{\phi} - \phi_{t-1}}{\phi_{t-1}}\Big)\Big(\frac{\gamma + t\omega}{\omega}\Big)f\\
	\displaystyle\frac{r_t}{f}\Big(\frac{\omega}{\gamma + t\omega}\Big) + \frac{r_t^2}{4f^2}\Big(\frac{\omega}{\gamma + t\omega}\Big)^2 & \mathrm{otherwise}
\end{cases}.
$$


If we **consider the flow of new funds** we can have
$$
n_t(r_t, \phi_{t-1}) = \begin{cases}
	-1 & \mathrm{if}\ r_t < \displaystyle2\Big(\frac{\bar{\phi} - \phi_{t-1}}{\phi_{t-1}}\Big)\Big(\frac{\gamma + t\omega}{\omega}\Big)f\\
	\displaystyle\Big[\frac{1}{f}\Big(\frac{\omega}{\gamma + t\omega} - 1\Big)\Big]r_t + \frac{1}{4f^2}\Big(\frac{\omega}{\gamma + t\omega}\Big)^2r_t^2 & \mathrm{otherwise}
\end{cases}.
$$


And we have the unconditional relationship (not conditioned on the perceived talent $\phi_{t-1}$) between the flow of funds and past return as
$$
N_t(r) = \Big[\frac{1}{f}\Big(\frac{\omega}{\gamma + t\omega} - 1\Big)\Big]\Big\{1 - G_{t-1}[\rho(r)]\Big\}r + \frac{1}{4f^2}\Big(\frac{\omega}{\gamma + t\omega}\Big)^2\Big\{1 - G_{t-1}[\rho(r)]\Big\}r^2 - G_{t-1}[\rho(r)],
$$
where
$$
\rho(r) \equiv \begin{cases}
	\displaystyle\frac{\bar{\phi}}{1 + (r/2f)[\omega/(\gamma+t\omega)]} & \displaystyle r > -2\Big(\frac{\gamma + t\omega}{\omega}\Big)f\\
	\infty & \displaystyle r \leq -2\Big(\frac{\gamma + t\omega}{\omega}\Big)f
\end{cases}.
$$


Here we have $G_{t-1}[\rho(r)]$ as the unconditioned probability that the fund will go out of buisness at time $t$ given the return $r$.



With this cost function we have the conditional volatility of fund's excess return as a function of the assest under management (or the perceived quality of the manager) as
$$
\mathrm{Var}(r_{t+1}) = \mathrm{Var}_t\Big[\frac{q_t^*(\phi_t)}{q_t}R_{t+1}\Big] = \Big[\frac{q_t^*(\phi_t)}{q_t}\Big]^2\frac{1}{\omega} = \frac{f}{aq_t\omega} = \frac{1}{\omega}\Big(\frac{2f}{\phi_t}\Big)^2.
$$
We can see that the conditional volatility is a decreasing function of the size of the fund.



**Question: why is the volatility the same as the perceived quality of the manager?**



### Implementation

Determination of the parameters

- $f$ is determined from past studies, and set to $f = 1.5\%$
- $\sigma = 20\%$, reflects the historical level of volatility
- the exit mean is $\bar{\phi} = 3\%$
- by matching the survival rate with empircal data we have $\phi_0 = 6.5\%$
- by matching the relationship of actual flow of fund and performance we have $\gamma = 277$ 



From the model they assume that the managers have skills and using that assumption they built models for flow of funds and surviving fund percentage, which matches the existing data. Therefore, they conclude that managers have skills. 