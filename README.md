# Widespread Gender and Pronoun Bias in Moral Judgments Across LLMs - LREC 2026
Repository with data for the paper “Widespread Gender and Pronoun Bias in Moral Judgments Across LLMs.” This work presents a controlled, sentence-level study of how grammatical person, number, and gender markers shape LLM moral classifications of fairness. Starting from 550 balanced base sentences from the ETHICS dataset, we generate 14,850 semantically equivalent counterfactual variants (26 per item) by systematically varying pronouns and gender markers. We evaluate six model families (Grok, GPT, LLaMA, Gemma, DeepSeek, and Mistral) and quantify inter-group disparities using Statistical Parity Difference (SPD). Results reveal statistically significant biases: singular and third-person sentences are more often judged as “fair,” while second-person formulations are penalized. Gender markers have the strongest effects, with non-binary subjects consistently favored and male subjects disfavored. The repository includes the paper.


*Paper/data coming soon.*


## Reporting checklist (GUIDE-LLM)

We include a GUIDE-LLM reporting checklist as supplementary documentation for this study:
- [GUIDE-LLM completed checklist](docs/reporting/GUIDE-LLM_filled_checklist.pdf)

GUIDE-LLM is a consensus-based reporting checklist for describing how LLMs are used in behavioral and social science research:
- https://sfeuerriegel.github.io/llm-checklist/how-to-use/
