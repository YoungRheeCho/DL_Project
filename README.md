# DL_Project: Can Autoencoders Detect Unknown Attacks?

**Student:** Cho, YoungRhee

---

## Summary

Modern network intrusion detection systems (IDS) face a critical limitation: they rely on **known attack signatures** and fail to detect novel threats. As cyberattacks evolve rapidly, a system that only recognizes previously seen attacks is fundamentally insufficient for real-world security environments. This motivated me to explore whether machine learning models — particularly unsupervised approaches — can generalize beyond their training distribution.

Using the **CICIDS2017 dataset**, which contains real network traffic labeled with various attack types including DDoS, DoS, PortScan, Brute Force, Web Attacks, and Botnet activity, I train and evaluate four models: Random Forest, MLP, LSTM, and an Autoencoder.

The experiment is split into two parts. First, all models are trained on a subset of known attack types and evaluated on held-out test data from the same distribution. Second, and more critically, models are evaluated on attack types entirely excluded from training. While supervised models learn to classify specific attack labels, the Autoencoder takes a fundamentally different approach: trained only on normal traffic, it flags anything that deviates significantly from learned patterns as an anomaly.

The core research question is whether an Autoencoder — by learning normal traffic representations rather than attack signatures — can outperform supervised models when encountering unknown attacks, offering a more robust foundation for real-world intrusion detection.

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
