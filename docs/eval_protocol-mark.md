\# Evaluation Protocol



\*\*Team:\*\* \[Team Two]  

\*\*Created:\*\* W19D1  

\*\*Last Updated:\*\* \[2026-02-08]



---



\## Metric



| Field | Value |

|-------|-------|

| \*\*Primary Metric\*\* | Mean episodic return |

| \*\*How Measured\*\* | Average reward over fixed evaluation episodes |

| \*\*Higher is Better\*\* | Yes |



---



\## Seeds



| Field | Value |

|-------|-------|

| \*\*Number of Seeds\*\* | \[1] |

| \*\*Seed Values\*\* | \[42] |

| \*\*Why This Many\*\* | \[Single seed for baseline to establish reference.] |



---



\## Training Budget



| Field | Value |

|-------|-------|

| \*\*Timesteps per Run\*\* | \[20,000] |

| \*\*Episodes for Eval\*\* | \[10] |



---



\## Stopping Rule



\- Training stops after fixed timesteps (50,000)

\- Evaluation runs after training completes

* No early stopping used

---



\## Comparison Rules



1\. Compare mean episodic return across seeds

2\. Report standard deviation across evaluation episodes

3\. A config "wins" if: \[It achieves equal or higher mean return than baseline AND shows similar or lower variance OR reaches high performance faster (fewer timesteps)]



---



\## Agreement



\- \[ ] All team members reviewed this protocol

\- \[X] Runner confirmed feasibility

\- \[X] Protocol will not change mid-experiment without team discussion



