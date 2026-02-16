Experiment Results



We compared the baseline PPO configuration (A) against the tuned configuration (B) across five random seeds and computed the performance difference (B − A).



Results:



Seed	A	B	B − A

0	500	500	0

1	188.3	500	311.7

2	500	500	0

3	500	500	0

4	500	500	0



Most runs produced identical rewards due to the environment’s performance ceiling. One seed showed a large difference because the baseline failed to learn optimal behavior while the tuned model succeeded.



Because performance is saturated and the improvement occurs in only one seed, the confidence interval for (B − A) includes zero. Therefore, we do not have sufficient statistical evidence that the tuned configuration consistently outperforms the baseline.



Decision



ITERATE



The tuned configuration may improve stability but does not reliably improve expected performance in CartPole.

