# Comprehensive Analysis of Annotation Artifacts in Arabic Natural Language Inference

This repository accompanies the article:

> Tarik Boudaa, Samira Boudaa, Mohamed El Marouani, Mohamed Tayyaui, Aboudourazakou Tetereou, Adil El Mansori and Mohamed Fahim.
> *Comprehensive Analysis of Annotation Artifacts in Arabic Natural Language Inference.* Submitted to *Information* (MDPI), 2026.

> **Status.** The code, the train/test split indices and the predictions of every model will be released here upon acceptance of the article.

## Overview

Annotation artifacts are a known weakness of Natural Language Inference (NLI) benchmarks, yet audits have focused almost exclusively on English.
This work audits the three main Arabic NLI resources, ArEntail, ArNLI and the Arabic portion of XNLI, with established diagnostics,
with diagnostics designed for Arabic (root-level overlap and particle-level negation) and with model-level tests across four pretrained
encoders (AraBERT v0.2, CAMeLBERT-MSA, ARBERTv2 and XLM-R base) and several random seeds. The evidence is summarized in an artifact-risk
matrix with explicit criteria, and an artifact-aware evaluation protocol is proposed for Arabic NLI benchmarks.

## Planned contents

| Path | Content |
|---|---|
| `Audit_A_statistics.ipynb` | Data cleaning and splits, shallow probes (length, overlap, bag-of-words), lexical associations (χ² with Benjamini–Hochberg correction, PMI), negation typology, root-level overlap, length matching |
| `Audit_B_neural.ipynb` | Fine-tuning of four encoders over several seeds (full, hypothesis-only, premise-only), truncation, length-matched training, negation intervention, cross-corpus transfer |
| `Audit_C_tables.ipynb` | Tables of the article, collapsed-run filtering, counter-examples, artifact-risk matrix |
| `arabic_nli_audit.py`, `camel_roots.py` | Shared code used by the notebooks |
| `splits/` | Train/test split indices for every corpus (random and group-aware splits) |
| `predictions/` | Per-example predictions of every model and seed |

## Data

No new dataset was created in this study, and the original corpora are **not** redistributed in this repository.

- **ArEntail**: available from its authors on request (Obeidat et al., *Language Resources and Evaluation*, 2025, https://doi.org/10.1007/s10579-024-09731-1).
- **ArNLI**: available from its authors on request (Al Jallad and Ghneim, *Computer Science*, 2023, https://doi.org/10.7494/csci.2023.24.2.4378).
- **XNLI**: publicly available from its original source (Conneau et al., EMNLP 2018, https://github.com/facebookresearch/XNLI).

Split indices and predictions refer to examples by their identifiers only, so they can be used once the corpora have been obtained from their sources.

## Citation

The citation will be added here upon publication.

## Contact

Tarik Boudaa, LSA Laboratory, National School of Applied Sciences of Al Hoceima, Abdelmalek Essaadi University, Morocco: t.boudaa@uae.ac.ma

## License

The code is released under the MIT License (see `LICENSE`). The ArEntail, ArNLI and XNLI corpora remain subject to the terms set by their respective authors.
