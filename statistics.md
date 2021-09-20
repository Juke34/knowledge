# Generalities about statistics

## Tests

One common activity in statistics is two independant samples are different between each other.
  * First we must check if the distribution follow the Normal distribution with `Shapiro` test. Depending this result we will not apply the same test.
    * If test is significant => does not follow the Normal distributuion, we must then use the `Wilcoxon` test.
    * If test not significant => the data follow normal distribution, we must use the `Student` test. (N>=20)  
