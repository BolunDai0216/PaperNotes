# Notes on Measuring skill in the mutual fund industry

**Authors: Jonathan B. Berk and Jules H. van Binsbergen**

Notes by Bolun Dai (bd1555@nyu.edu)

### Introduction

- Current compensation predicts future performance

### Definitions

Let $R_{it}^n$ denote the return in excess of the risk free rate earned by investors in the $i$-th fund at time $t$. Which can be split up into the excess return of the investor's next best alternative investment opportunity $R_{it}^B$, which we can the manager's benchmark, and a deviation from the benchmark $\epsilon_{it}$
$$
R_{it}^n = R_{it}^B + \epsilon_{it}.
$$
The most common measure of skill is the unconditional mean of $\epsilon_{it}$, also called the net alpha $\hat{\alpha}_i^n$
$$
\hat{\alpha}_{i}^n = \frac{1}{T_i}\sum_{t=1}^{T_i}{\epsilon_{it}}
$$
where $T_i$ is the number of periods fund $i$ appears in the database. However, the net alpha measures the rationality and competiveness of the market, if the net alpha is positive then the capital market is not competitive and the supply of capital is insufficient to compete away the abnormal return, if the net alpha is negative then the investors are committing too much capital to active management.



Let $R_{it}^g$ denote the gross excess return and $f_{i, t-1}$ denotes the percentage fee and we have
$$
R_{it}^g \equiv R_{it}^n + f_{i, t-1} = R_{it}^B + \epsilon_{it} + f_{i, t-1}.
$$
And we have the gross alpha defined as
$$
\hat{\alpha}_i^g = \frac{1}{T_i}\sum_{t=1}^{T_i}{(f_{i, t-1} + \epsilon_{it})}.
$$
However, the gross alpha measures the return the fund earns not the value it adds and it can be shown that it does not even positive correlates to managerial skills.



We can define the dollar value the fund adds with respect to the benchmark as
$$
V_{it} \equiv q_{i, t-1}(R_{it}^g - R_{it}^B) = q_{i, t-1}f_{i, t-1} + q_{i, t-1}\epsilon_{it}.
$$
And a measurement of skill can be given as
$$
S_i \equiv \mathbb{E}[V_{it}],
$$
where we can have an estimation of the skill as
$$
\hat{S}_i = \sum_{t=1}^{T_i}{\frac{V_{it}}{T_i}}.
$$
The mean value added across funds can be estimated in two ways

- $\displaystyle\bar{S} = \frac{1}{N}\sum_{i=1}^{N}{\hat{S}_i}$, denotes the mean of the distribution from which the value added is drawn,
- $\displaystyle\bar{S}_w = \frac{\sum_{i=1}^{N}{T_i\hat{S}_i}}{\sum_{i=1}^{N}{T_i}}$, denotes the mean of the surviving funds.

 

### Why alpha measures do not measure skill

We assume the alpha generated my manager $i$ by actively managing money is given as
$$
\alpha_i^* = a_i - b_iq
$$
where $a_i > 0$ is the alpha on the first cent the manager actively invests and $b_i > 0$ is a parameter that captures the decreasing returns to scale the manager faces. 

> **Proposition 1**:
>
> - *The net alpha never proxies for, or measures, managerial skill.*
> - *The only condition under the gross alpha measures managerial skill is if all managers set their fees to ensure that the AUM of all funds is exactly $1. Gross alpha will proxy for managerial skill only under the condition that managers set fees to ensure that all funds have the same AUM.*
> - *Value added, the product of AUM and gross alpha, always measures skill.*



### Choice of benchmarks and estimation

If $R_{t}^j$ is the excess return earned by investors in the $j$-th Vanguard index fund at time $t$, then the benchmark return for fund $i$ is given by
$$
R_{it}^B = \sum_{j=1}^{n(t)}{\beta_i^jR_t^j}
$$
where $n(t)$ is the number of index funds offered by Vanguard at time $t$ and $\beta_i^j$ is obtained from the appropriate linear projection of the $i$-th active mutual fund onto the set of Vanguard index funds.



The second benchmark is where the returns are the same as the return of a portfolio of equivalent riskiness constructed from the Fama-French-Carhart (FFC) factor portfolios
$$
R_{it}^B = \beta_i^{mkt}MKT_t + \beta_i^{sml}SML_t + \beta_i^{hml}HML_t + \beta_i^{umd}UMD_t.
$$
