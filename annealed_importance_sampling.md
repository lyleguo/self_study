# Background
Sometimes, the distribution can be too complex to generate points from it. In this case, we can generate points from some simpler approximating distribution, and then use an 
importance sampling estimate. We can also use a sample of dependent points obtained by simulating a Markov chain that converges to the correct distribution. Annealed Importance 
Sampling combines both of them, by using an importance sampling distribution defined by a series of Markov chains
## Importance Sampling
Suppose we are interested in a distribition of $x$, with pdf that is proportional to $f(x)$ Computing $f(x)$ from $x$ is feasible, but we cannot directly sample from the distribition
 it defines. However, we can sample from other distribution that approximates the one defined by $f(x)$. And the pdf of that distribution is proportional to $g(x)$, which we can evaluate.
## Metropolis-Hastings Algorithm (Markov Chain Monte Carlo)
Metropolis-Hastings Algorithm is a type of Markov Chain Monte Carlo (MCMC) Algorithm. MCMC is used to sample points from a distribution. It constructs a Markov chain that has the desired distribution as its equilibrium distribution. Then it can obtain a sample of the desired distribution by recording states from the chain. At each step, we only make small changes to state variables. The more steps that are included, the more closely the distribution of the sample matches the actual desired distribution.\
Let our target distribution be $\pi$ and we have a transition kernel $Q$.\

Initialize $x_0$\
For $t=0,1,2,...$\
$\qquad$ Sample $x'$ from $Q(x'|x_t)$\
$\qquad$ Compute\
$$A=min(1,\frac{\pi(x')Q(x_t|x')}{\pi(x_t)Q(x'|x_t)})$$
$\qquad$ With probability A, we set $x_{t+1}=x'$. Otherwise, $x_{t+1}=x_t$\

## Simulated Annealing
It is a way of handling multiple modes in an optimization ocntext. Suppose we have a sequence of distribitions from $p_n(x)$ to $p_0(x)$. $p_0$ is the one of interest. Simulated annealing starts from some inital state and simulates a Markov chain to converge to $p_n$. Then simulates the Markov chain to converge to $p_{n-1}$, given the output of previous stage as its input. It repeat such steps until reaches $p_0$.
# Problem Setting
Our purpose is to find the expectation of some function of $x$ with respect to a pdf $p_0(x)$. We have a sequence of other distributions from $p_1(x)$ to $p_n(x)$. For each one, we are able to compute some function $f_j(x)$ proportional to $p_j(x)$. We also have some methods for sampling from $p_n$. For each $i$ from 1 to $n-1$, we can simulate a Markov chain transition $T_j$ that leaves $p_j$ invariant.
# Steps
1. The function $f$ is constructed as $f_j(x)=f_0(x)^{\beta_j}f_n(x)^{1-\beta_j}$ where $1=\beta_0>\beta_1>...>\beta_n=0$.
2. Generate a sequence of points
   - Generate $x_{n-1}$ from $p_n$
   - Generate $x_{n-2}$ from $x_{n-1}$ using $T_{n-1}$
   - Repeat until we generate $x_0$ from $x_1$ using $T_1$
3. Using
# Applications in <Reduce, Reuse, Recycle: Compositional Generation with Energy-Based Diffusion Models and MCMC>
