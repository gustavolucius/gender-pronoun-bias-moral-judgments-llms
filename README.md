# Widespread Gender and Pronoun Bias in Moral Judgments Across LLMs - LREC 2026
Repository with data for the paper “Widespread Gender and Pronoun Bias in Moral Judgments Across LLMs.” This work presents a controlled, sentence-level study of how grammatical person, number, and gender markers shape LLM moral classifications of fairness. Starting from 550 balanced base sentences from the ETHICS dataset, we generate 14,850 semantically equivalent counterfactual variants (26 per item) by systematically varying pronouns and gender markers. We evaluate six model families (Grok, GPT, LLaMA, Gemma, DeepSeek, and Mistral) and quantify inter-group disparities using Statistical Parity Difference (SPD).

### Main findings

The heatmap below summarizes the paper’s main findings across models and counterfactual transformations involving number, grammatical person, and gender markers.

<p align="center">
  <img src="./figs/tabela_spd_heatmap.png" alt="Heatmap summarizing aggregated Statistical Parity Difference (SPD) effects across models for number, person, and gender." width="100%">
</p>

Results reveal statistically significant biases: singular and third-person sentences are more often judged as “fair,” while second-person formulations are penalized. Gender markers have the strongest effects, with non-binary subjects consistently favored and male subjects disfavored. The repository includes the paper.


## Paper

*Paper coming soon.*

## Data

The `data/` directory contains the full dataset used in the paper, organized into three parts:

- `gt/`: the ground-truth labels (`gt.csv`)
- `predictions/`: model predictions for each variant at temperature 0
- `sentences/`: the sentence files for each counterfactual variant

The dataset is built from 550 base sentences. We generate 27 counterfactual variants per sentence, resulting in a total of 14,850 sentences. Predictions are provided for 9 models, with one file per model and variant.

See [`data/README.md`](data/README.md) for a complete description of the file structure, naming conventions, and variant codes.

## Reporting checklist (GUIDE-LLM)

We include a GUIDE-LLM reporting checklist as supplementary documentation for this study:
- [GUIDE-LLM completed checklist](docs/reporting/GUIDE-LLM_filled_checklist.pdf)

GUIDE-LLM is a consensus-based reporting checklist for describing how LLMs are used in behavioral and social science research:
- https://sfeuerriegel.github.io/llm-checklist/how-to-use/
