# Self-Assessment American Options

## Exercise 1: Lattice Methods

**a)** Compute and visualize the Cox–Ross–Rubinstein (CRR) **binomial tree** (without dividends) of the underlying, the European call and put, and the American call and put.

**b)** Compute and visualize the **Early Exercise Boundary** for an American put option. Assuming a sufficiently small time-step, use Monte Carlo simulation to compute the **risk-neutral** probability that an American put option is early exercised and plot the **Optimal Stopping Time** distribution for an ITM put option.

**c)** Compute and visualize the Cox–Ross–Rubinstein **Trinomial Tree** (without dividends) of the underlying, and the American put option. Compare the pricing engine of the American option using a binomial tree with the one using a trinomial tree as you increase the number of steps. For which pricing engine is the convergence faster? Explain the result.

**d)** Price an American lookback put with payoff
$$
\max_{\{0<s<t\}} \, S(s) - S(t)
$$
using the **Forward Shooting Grid** algorithm built over the trinomial tree. Show how **Richardson Extrapolation** can be used to achieve higher computational efficiency.

---

## Exercise 2: Finite-Difference Method

**a)** Through a change of variables of your choice, transform the **Black–Scholes PDE** into the **1D heat equation**. Using the **$\theta$-method** with asymptotic Dirichlet boundary conditions for a European call or put, study the stability of the discretization scheme, focusing on:
- $\theta = 1$ (Implicit Euler),
- $\theta = \tfrac{1}{2}$ (Crank–Nicolson),
- $\theta = 0$ (Explicit Euler).

**b)** Price an American put with the $\theta$-method using **Brennan–Schwarz** projection. Compute and visualize $\Delta$ and $\Gamma$ of an American put in the continuation region and compare them with the Greeks of a European put.

---

## Exercise 3: LSMC

**a)** Consider the **Bates** stochastic-volatility–jump diffusion model under the $\mathbb{Q}$-measure:
$$
\frac{dS_t}{S_{t^-}}
= \big(r - q - \lambda \kappa_J\big)\,dt
  + \sqrt{v_t}\,dW_{1,t}
  + (J-1)\,dN_t
$$
$$
dv_t = \gamma\big(\theta - v_t\big)\,dt + \sigma_v \sqrt{v_t}\, dW_{2,t}
$$
$$
\mathrm{corr}(dW_{1,t}, dW_{2,t}) = \rho
$$
$$
\kappa_J = \mathbb{E}[J-1] = e^{\mu_J + \tfrac12 \sigma_J^2} - 1
$$
$$
J_t \sim \text{Lognormal}(\mu_J,\sigma_J), \quad
N_t \sim \text{Poisson process with intensity } \lambda>0
$$

Price an American call option using *Longstaff–Schwartz Least Squares Monte Carlo* (LSMC), where the continuation value is estimated via polynomial regressions.

