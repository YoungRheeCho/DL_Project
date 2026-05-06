# DL_Project: Can Autoencoders Detect Unknown Attacks?

**Student:** Cho, YoungRhee

---

## Summary

This project investigates the limitations of supervised learning models in network intrusion detection, specifically their inability to detect unknown attack types not seen during training.

Using the **CICIDS2017 dataset** — which contains real network traffic labeled with various attack types including DDoS, DoS, PortScan, Brute Force, Web Attacks, and Botnet activity — I train and evaluate four models:

| Model |
|---|
| Random Forest |
| MLP |
| LSTM |
| Autoencoder |

## Experimental Design

The experiment is split into two parts:

1. **Known Attack Evaluation** — All models are trained on a subset of known attack types and evaluated on held-out test data from the same distribution.

2. **Unknown Attack Evaluation** *(core contribution)* — Models are evaluated on attack types entirely excluded from training (e.g., Web Attacks, Botnet). While supervised models learn to classify specific attack labels, the Autoencoder takes a fundamentally different approach: it learns only the **representation of normal traffic**, flagging anything that deviates significantly as an anomaly.

## Research Question

> Can an Autoencoder — by learning normal traffic patterns rather than attack signatures — outperform supervised models on unknown attack types?
