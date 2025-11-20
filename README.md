# Causal Sentiment Mining under Noisy Streams via Lightweight Attention

This repository contains the code and experiments for the paper:

> Causal Sentiment Mining under Noisy Streams via Lightweight Attention  
> Miloud Mihoubi, Meriem Zerkouk, Belkacem Chikhaoui, 2025.

## Overview

We propose a lightweight, noise-robust and interpretable sentiment analysis model that combines:
- a **Noise-Invariant Contrastive Head (NICH)** for normalising noisy tokens (typos, elongations, emojis),
- a **CNN–BiLSTM** backbone for local n-grams and long-range dependencies,
- a **single Multi-Head Self-Attention (MHSA)** block for global dependencies and token-level importance scores.

The model is evaluated on:
- **Sentiment-140** (1.6M tweets, noisy short text),
- **IMDb** (50k long-form movie reviews).

It outperforms classical baselines (LR, SVM, RF) and an Attention-BiLSTM reference model, while providing meaningful attention-based token-level explanations.

## Repository structure (planned)

- `src/` – model implementation (NICH, CNN–BiLSTM–MHSA, training loop)
- `configs/` – training and evaluation configuration files
- `scripts/` – scripts to preprocess data and run experiments
- `notebooks/` – optional analysis notebooks (ablation, attention visualisation)
- `data/` – **not included**, see below
- `results/` – logs, metrics, and trained model checkpoints

## Datasets

Due to licensing constraints, the original datasets are **not redistributed** in this repository.

- **Sentiment-140**: can be downloaded from the official project page.  
- **IMDb Reviews**: available from the `aclImdb` dataset (Maas et al., 2011).

We provide scripts in `scripts/` to:
- preprocess both datasets (cleaning, tokenisation, splits),
- reproduce the exact train/validation/test setup used in the paper.

If your journal/reviewer explicitly requires data copies, please refer to the `data/README.md` for details and conditions.

## Reproducing the experiments

1. Create and activate a Python environment.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
