# Language background and listening attention

Does the distance between your first language and English affect how well you can follow spoken English, especially in noise?

This project analyses the **PhyAAt** dataset: 25 non-native English speakers transcribed English sentences under different noise levels, sentence lengths and semantic conditions, producing an attention score per trial. It then adds my own extension using **lang2vec** (the URIEL typological database) to measure linguistic distance objectively.

## Part 1: Statistical analysis

- Descriptive statistics and visualisation across noise, length and semanticity
- Confidence interval estimation for mean attention
- Hypothesis tests chosen according to normality checks (Shapiro–Wilk, Q–Q plots): paired **Wilcoxon** signed-rank, **Mann–Whitney U**, and **Spearman** correlation
- Comparisons between noise conditions, individual participants and age groups, and associations with self-reported English proficiency

## Part 2: Extension. Does first-language distance from English predict attention?

Self-reported English proficiency was only weakly related to attention, so I used lang2vec to compute six objective distance measures between each participant's first language and English: phonological, syntactic, genetic, geographic, inventory and featural.

**Findings**
- No distance type significantly predicted overall attention. Geographic distance showed a marginal effect, likely confounded by English exposure.
- **Phonological distance** showed a consistent negative trend, strongest in the noisiest condition (SNR −6 dB, ρ = −0.32).
- At SNR −6 dB, participants with low vs high phonological distance differed significantly (Mann–Whitney U, **p = 0.0039**, rank-biserial r = 0.338).
- Stronger conclusions would need a larger sample that controls for English exposure.

## Run it

Install the dependencies:

```
pip install -r requirements.txt
```

Download the PhyAAt tabular data from the [PhyAAt project page](https://PhyAAt.github.io) and place the CSVs in the working directory. The notebook installs lang2vec from GitHub and uses its pre-computed distance files.

## Tools

Python · pandas · NumPy · SciPy · Matplotlib · seaborn · lang2vec

*Completed as part of the MSc Artificial Intelligence at Queen Mary University of London.*
