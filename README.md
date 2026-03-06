# Heuristic and Language-Model-Based Detection of Corporate Phishing and Whaling Emails

**MSc Information Technology with Cybersecurity** — CMM500 Project  
**Author:** Joshua Wilson  
**Supervisor:** Jean-Claude Golovine

---

## Overview

This project builds a prototype detection engine that combines **heuristic scoring rules** with a **RoBERTa-based language model** to identify phishing and whaling emails in corporate environments. The goal is to catch targeted, organisation-specific attacks that generic email filters miss — particularly executive-level ("whaling") threats.

---

## How It Works

1. **Heuristic scoring** — flags red-flag lexicons, behavioural indicators, and structural features common in corporate phishing/whaling emails
2. **RoBERTa classifier** — fine-tuned transformer model that analyses subtle linguistic cues in email content
3. **Combined scoring** — both signals are merged to produce a final threat classification

---

## Model Config

| Parameter | Value |
|---|---|
| Base model | `roberta-base` |
| Epochs | 5 |
| Batch size | 8 |
| Training samples | 5,000 |

---

## Running the Notebook

> ⚠️ **This project is developed in Google Colab.** Local training is not practical due to AMD GPU incompatibility with the CUDA-dependent libraries used (PyTorch, Transformers). A free or Pro Colab runtime with a T4/A100 GPU is recommended.

1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Set runtime to **GPU** (Runtime → Change runtime type → T4 GPU)
3. Run all cells from top to bottom

---

## Dependencies

All dependencies are installed within the notebook. Key libraries:

- `transformers`
- `torch`
- `datasets`
- `scikit-learn`
- `pandas`

---

## Evaluation Metrics

The model is evaluated against a baseline generic phishing filter using:

- Detection rate (recall)
- False positive rate
- False negative rate
- F1 score

---

## Dataset

Trained and evaluated on publicly available phishing datasets and synthetic corporate email corpora. No real organisational data is used.

---

## References

Key literature informing this project:

- Heiding et al. (2024) — *Devising and Detecting Phishing Emails Using Large Language Models*, IEEE Access
- Kalla et al. (2024) — *Investigating the Impact of Heuristic Algorithms on Cyberthreat Detection*, ICAICCIT
- Vanitha et al. (2023) — *Detection System of Whaling Attack using Deep Learning Techniques*
- Arshad et al. (2021) — *A Systematic Literature Review on Phishing and Anti-Phishing Techniques*
