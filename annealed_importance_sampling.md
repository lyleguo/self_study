# Background
Sometimes, the distribution can be too complex to generate points from it. In this case, we can generate points from some simpler approximating distribution, and then use an 
importance sampling estimate. We can also use a sample of dependent points obtained by simulating a Markov chain that converges to the correct distribution. Annealed Importance 
Sampling combines both of them, by using an importance sampling distribution defined by a series of Markov chains
## Importance Sampling
Suppose we are interested in a distribition of $x$, with pdf that is proportional to $f(x)$ Computing $f(x)$ from $x$ is feasible, but we cannot directly sample from the distribition
 it defines. However, we can sample from other distribution that approximates the one defined by $f(x)$. And the pdf of that distribution is proportional to $g(x)$, which we can
 evaluate.
## Metropolis-Hastings Algorithm (Markov Chain Monte Carlo)
Metropolis-Hastings Algorithm is a type of Markov Chain Monte Carlo (MCMC) Algorithm. MCMC is used to sample points from a distribution. It constructs a Markov chain that has 
the desired distribution as its equilibrium distribution. Then it can obtain a sample of the desired distribution by recording states from the chain. At each step, we only make 
small changes to state variables. The more steps that are included, the more closely the distribution of the sample matches the actual desired distribution.
```

```
## Stimulated Annealing
# Problem Setting

