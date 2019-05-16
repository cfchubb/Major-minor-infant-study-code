# Major-minor-infant-study-code
This repository contains the matlab program (kurtosisPermutationTest.m) to run the random permutation test described in "Sensitivity to Major Versus Minor Musical Modes is Bimodally Distributed in Young Infants".  The study was designed to investigate whether infants are bimodally distributed in their sensitivity to major vs. minor musical modes.  The data to be analyzed are responses drawn from a set of N_infs (N_infs = 30 in the "predictable" condition tested in Experiment 1, or N_infs = 20 in the unpredictable condition tested in Experiment 2).  

Different infants i produce different numbers n(i) of responses, and a given response is either correct or incorrect. Across all N_infs infants, let N_cor be the total number of correct responses and N_inc be the total number of incorrect responses, and let N_total = N_cor + N_inc. (N_cor = 176, N_inc = 76, and N_total = 205 in the predictable condition; N_cor = 73, N_inc = 69, and N_total = 142 in the unpredictable condition.) For each response r = 1,2,...,N_total, let I(r) be the infant who produced response r, and let P(r) be the proportion of the responses made by infant I(r) that were correct.  Thus, for any infant i, the distribution P contains n(i) copies of the proportion of correct responses produced by infant i. (High (low) proportions of correct responses reflect high (low) sensitivity to major vs. minor modes.)  

Does the obtained data support the conclusion that our infants actually comprise a heterogeneous mixture of high- and low-performers? To investigate this question, we used a random permutation test of the null hypothesis that all of our participants actually have the same probability of responding correctly. Our alternative hypothesis is that the distribution P is bimodal (because it is actually generated by a mixture of high- vs. low-performers). Under this alternative hypothesis, the kurtosis (the 4th central moment divided by the 4th power of the standard deviation) of P should be very low compared to distributions simulated under the null hypothesis.  

We proceed as follows. On each of 100,000 iterations, we generate a simulated distribution sim_P that should be identically distributed to P under the null hypothesis and compute the kurtosis of sim_P. In each iteration, we first form a random sequence S comprising N_cor ones (for the correct responses) and N_inc zeros; then, for k = 1, 2,..., N_infs, we assign to each successive infant i the next n(i) items in S to determine a simulated number of correct and incorrect responses and compute the proportion p(i) of correct responses for participant i; then we add n(i) copies of the value p(i) to the distribution sim_P, and finally, we compute the kurtosis of the resulting simulated distribution. We take as our p-value the proportion of simulated kurtosis values lower than the kurtosis of P. 

