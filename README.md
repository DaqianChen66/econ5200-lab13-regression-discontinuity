# econ5200-lab13-regression-discontinuity
# Regression Discontinuity: Bandwidths, Manipulation and Close Elections

## Objective

I used regression discontinuity designs to study how bandwidth choice, manipulation around a cutoff, and local comparisons affect causal estimates.

## Methodology

- I simulated a grant program with a true treatment effect of 0.08 at a cutoff.
- I compared a global quadratic estimate of 0.0357 with a local linear estimate of 0.0789 using a data-driven bandwidth of 16.1.
- I repeated the simulation 300 times and compared bias, variance, and RMSE across different bandwidths.
- I ran a density test to detect manipulation of the running variable and a continuity test using a pre-treatment covariate.
- I applied RD to U.S. House elections to compare districts where a Democrat barely won with districts where a Democrat barely lost.
- I wrote my own local linear RD estimator using a triangular kernel and checked its estimates against the rdrobust package.

## Key Findings

The global quadratic estimate was 0.0357, substantially below the true treatment effect of 0.08. The local linear estimate was 0.0789 at a bandwidth of 16.1, which was much closer to the true effect.

Across the 300 simulations, the lowest RMSE on the tested grid occurred at a bandwidth of 20. Small bandwidths had more sampling variation, while very large bandwidths introduced more bias.

The manipulation test produced a p-value of 0.0022 when units were deliberately moved across the cutoff, showing that the density test can detect sorting around the threshold. The covariate continuity test also detected the planted discontinuity in the pre-treatment score.

In the U.S. House application, a Democrat barely winning rather than barely losing increased the representative's adjusted ADA score by 46.491 points. This indicates a large difference in policy representation at the electoral threshold.
