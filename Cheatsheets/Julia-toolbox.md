# Julia ToolBox 


## Statistics and Distributions 

### Random generators 

Before generating and pseudo-random numbers, we must prompt julia to generate a
replicable 'seed' of random numbers, so that we can share this with others who
may seek to reproduce our workflows.     

I am not sure if this comes with Julia base, or we are required to load the package "RandomNumbers.jl"   
`Random.seed!(123434)`   

If we want to generate a set of random replicates from say, a distribution, we can use the convenient *rand* function.  

The following example will generate a set containing a single 'experiment'
which tallies (in this particular case) the number of successes within a 15
bernoulli trials - in other words, how many times did head comes up if we
flipped a fair coin 15 times!   
`rand(Binomial(15, 0.5)`   

We can replicate this set itself, and run the experiment another 15 times, to see the general flux of successes in repeated bernoulli trials.   
`random(Binomial(15, 0.5), 1000)`      

### Probability mass and density functions 

A probability mass function gives the value of a **discerte** random variable
under a specific distribution. A probability density function gives theis
value for a **continuously** disributed variable.    




### Binomial

Using any of the probability distributions, we must preload  the *Distributions.jl* package.    

Let's generation a binomial distribution with 20 trials, and slightly biased failure rate. The general structure of this function is **Binomial(trial number, success rate)**.    
``
using Distributions
Binomial(20, 0.45)
`` 