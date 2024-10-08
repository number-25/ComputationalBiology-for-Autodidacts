# Some parameters in the population genetics of mutations
Taken from ["The population genetics of mutations: good, bad and indifferent"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2871823/) 

This is also a good exercise in MathJax formatting within markdown! 

| Notation                                    | Definition                                                                                                                                                                                                           |
| ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $U$                                         | mutation rate per generation per genome; check context for effects of mutations                                                                                                                                      |
| $G_e , G$                                   | effective haploid genome size (all functional base pairs), total haploid genome size (with neutral sites)                                                                                                          |
| $\mu , \mu_{10} , \mu_{01}$                 | mutation rate per locus or per site per generation, away from the preferred base, and back                                                                                                                          |
| $\kappa$ , **tn/tv**         | mutational bias: $\mu_{10}/\mu_{01}$, transition/transversion ratio                                                                                                                                                  |
| $r_e , r_{co} , r_{gc}$                     | effective recombination rate, cross over rate, gene conversion rate                                                                                                                                                  |
| $s$                                         | selection coefficient; measures changes in fitness; check context for exact definitions (homozygous or heterozygous; positive or negative)                                                                |
| $h$                                         | dominance coefficient so that *sh* is the effect of heterozygous mutations                                                                                                                                           |
| **DME (or DFE)**                            | distribution of mutational effects on fitness                                                                                                                                                                        |
| ${W_A}$                                     | Wrightian fitness of a genotype A (one of the many ways fitness can be defined)                                                                                                                                      |
| $\varepsilon$                               | epistasis: interactions of mutational effects. If fitness is multiplicative, $\varepsilon = W_{AB} - W_AW_B$                                                                                               |
| $N_e , N$                                   | effective population size, census population size                                                                                                                                                                    |
| $m$                                         | migration rate                                                                                                                                                                                                       |
| ${P_{fix}}$                                    | probability of fixation of a (mutant) allele                                                                                                                                                                         |
| ${T_{fix}} , {T_{loss}}$                         | time to fixation, loss in generations                                                                                                                                                                                |
| $K_A , K_S$ **(or** $D_N , D_S$**)**        | rate of DNA divergence per site between two species corrected for multiple hits (see context for method); substitutions can be non-synonymous (change amino acids), or synonymous (or silent) (check context) |
| $\pi_A , \pi_S , \theta_{WA} , \theta_{WS}$ | DNA diversity within a population per site: $\theta$ is the average pairwise nucleotide diversity, $\theta_W$ is Watternson's estimate; for explanation of indices see $K_A , K_S$                        |
| $D , D' , {r^2}$                            | measures of linkage disequilibrium (LD)                                                                                                                                                                              |
| ${V_G}$                                       | genetic variance in a quantitative trait                                                                                                                                                                             |
| $V_M$                                       | increment in $V_G$ from new mutations per generation                                                                                                                                                                 |
| $V_R$                                       | environmental variance in a quantitative trait                                                                                                                                                                       |

* For historical reasons and due to the limitations of the alphabet, several
symbols have different meanings in different contexts. Examples: ${h^2}$ =
heritability of a quantitative trait; $r$ = rate of selfing; $r$ = rate of
population growth; $D$ = ‘Tajima's D’, where $D$ < 0 may indicate population
expansion or directional selection and $D$ > 0 a bottleneck or balancing
selection.
