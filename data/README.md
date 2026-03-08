# Data

This directory contains the full data release for the paper *“Widespread Gender and Pronoun Bias in Moral Judgments Across LLMs.”* It includes the ground-truth labels, the counterfactual sentence variants, and the model predictions used in the experiments.

## Overview

The dataset starts from **550 base sentences**. For each sentence, we generate **27 counterfactual variants** by systematically changing person, number, and gender markers. This results in a total of **14,850 sentences** (`550 × 27`).

We provide predictions for **9 models**, evaluated on all 27 variants at **temperature 0**.

## Directory structure

```text
data/
├── gt/
│   └── gt.csv
├── predictions/
│   ├── resposta_1P_temperatura_0_deepseek-r1-qwen-1.5B.csv
│   ├── resposta_1P_temperatura_0_deepseek-r1-qwen-7B.csv
│   ├── resposta_1P_temperatura_0_gemma_2_27b_it.csv
│   ├── ...
│   └── resposta_3S-WN_temperatura_0_mistral_7b_instruct.csv
└── sentences/
    ├── sentences_1S.csv
    ├── sentences_1S-M.csv
    ├── ...
    └── sentences_3P-NB.csv
```

## Contents

### `gt/`

The `gt/` folder contains the ground-truth file:

- `gt.csv`: the reference labels for the 550 base sentence positions

This file should be used as the gold standard for evaluation.

### `sentences/`

The `sentences/` folder contains one file per variant. Each file has **550 rows**, corresponding to the same 550 sentence positions across all variants.

Examples:

- `sentences_1S.csv`
- `sentences_2S.csv`
- `sentences_3S-W.csv`
- `sentences_1P-NB.csv`

### `predictions/`

The `predictions/` folder contains the model outputs for each variant at **temperature 0**. There is one file per **model × variant** combination.

Filename pattern:

```text
prediction_<VARIANT>_temperature_0_<MODEL>.csv
```

Examples:

- `prediction_1P_temperature_0_gpt4o_mini.csv`
- `prediction_1P_temperature_0_grok-4-fast-reasoning.csv`
- `prediction_1P_temperature_0_mistral_7b_instruct.csv`

Since there are **27 variants** and **9 models**, this folder contains **243 prediction files** in total.

## Variant code system

Variant names are built from compact codes that indicate grammatical person, number, and optional gender or group markers.

### Code components

| Code | Meaning |
|------|---------|
| `1S`, `2S`, `3S` | first / second / third person, singular |
| `1P`, `2P`, `3P` | first / second / third person, plural |
| `M`, `W`, `NB` | man, woman, non-binary (singular); men, women, non-binary people (plural) |
| `N` (suffix) | named form: a proper name replaces the pronoun |
| `ALL` | heterogeneous group (men, women, and non-binary people together) |

### Included variants

The release includes the following 27 variants:

| Variant | Interpretation |
|---------|----------------|
| `1S` | first person singular |
| `1S-M` | first person singular, man |
| `1S-NB` | first person singular, non-binary person |
| `1S-W` | first person singular, woman |
| `2S` | second person singular |
| `2S-M` | second person singular, man |
| `2S-NB` | second person singular, non-binary person |
| `2S-W` | second person singular, woman |
| `2P-ALL` | second person plural, heterogeneous group |
| `2P-M` | second person plural, men |
| `2P-W` | second person plural, women |
| `2P-NB` | second person plural, non-binary people |
| `3S-W` | third person singular, woman |
| `3S-WN` | third person singular, woman, named form |
| `3S-M` | third person singular, man |
| `3S-MN` | third person singular, man, named form |
| `3S-NB` | third person singular, non-binary person |
| `1P` | first person plural |
| `1P-ALL` | first person plural, heterogeneous group |
| `1P-M` | first person plural, men |
| `1P-W` | first person plural, women |
| `1P-NB` | first person plural, non-binary people |
| `3P` | third person plural |
| `3P-ALL` | third person plural, heterogeneous group |
| `3P-M` | third person plural, men |
| `3P-W` | third person plural, women |
| `3P-NB` | third person plural, non-binary people |

## Models

Predictions are provided for the following 9 models:

| Model name | Filename identifier |
|------------|---------------------|
| Grok 4 Fast Reasoning | `grok-4-fast-reasoning` |
| GPT-4o Mini | `gpt4o_mini` |
| LLaMA 3.3 (70B-Instruct) | `llama_3.3_70b_instruct` |
| LLaMA 3.1 (8B-Instruct) | `llama_3.1_8B_instruct` |
| LLaMA 3.2 (3B-Instruct) | `llama_3.2_3B_instruct` |
| Gemma 2 (27B-Instruct) | `gemma_2_27b_it` |
| DeepSeek R1 Qwen (7B) | `deepseek-r1-qwen-7B` |
| DeepSeek R1 Qwen (1.5B) | `deepseek-r1-qwen-1.5B` |
| Mistral (7B-Instruct) | `mistral_7b_instruct` |

## Alignment across files

All files are organized by **sentence position**. This means that:

- row `i` in `gt/gt.csv`
- row `i` in any file in `sentences/`
- row `i` in any file in `predictions/`

refer to the same sentence position in the dataset.

This alignment makes it straightforward to compare:

- the ground-truth label,
- the 27 counterfactual sentence variants,
- and the predictions produced by each model.
