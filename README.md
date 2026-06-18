# MammoXV: A Public Dual-View Mammography Benchmark for Breast Lesion Characterization, Cancer Detection, and Screening

Official open-source repository containing the deterministic preprocessing engine, nested evaluation pipelines, and architectural variants for the **MammoXV** framework.

[![Dataset](https://img.shields.io/badge/Dataset-GitHub%20Release-blue.svg)](#1-repository-topology--code-navigation)
[![Python 3.10](https://img.shields.io/badge/Python-3.10+-green.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-ee4c2c.svg)](https://pytorch.org/)

---

## 📌 Executive Summary

**MammoXV** is a dual-view mammographic benchmark comprising **961 patients** (1,922 images) designed for patient-disjoint, leakage-free evaluation. Both Cranio-Caudal (CC) and Medio-Lateral-Oblique (MLO) projections are processed simultaneously using a weight-shared visual foundation backbone (**Base Vision Transformer**) and global average pooling feature fusion.

### Core Benchmarking Targets:
* **Task 1 (Characterization):** Discriminates Benign vs. Malignant findings ($\text{AUC} = \mathbf{0.8036}$).
* **Task 2 (Cancer Detection):** Identifies Malignant vs. All Non-Malignant cases ($\text{AUC} = \mathbf{0.8503}$), catching **84.47%** of confirmed malignancies.
* **Task 3 (Screening):** Flags Malignant vs. Normal tissue ($\text{AUC} = \mathbf{0.9743}$) with a stable **92.59%** specificity threshold for population triage.

---

## 📂 Repository Topology & Code Navigation

The project directory layout is strictly organized as follows:

```text
├── .gitattributes
├── MammoXV_GitHub_Release/           # Anonymized dataset release directories
│   ├── CC/                           # Cranio-Caudal projections (Sequential IDs)
│   │   ├── Normal/                   # MammoXV_001.png, MammoXV_002.png...
│   │   ├── Benign/
│   │   └── Malign/
│   └── MLO/                          # Medio-Lateral-Oblique complementary views
│       ├── Normal/
│       ├── Benign/
│       └── Malign/
├── 01_preprocessing.ipynb            # Stage 1: Artifact & pectoral boundary removal
├── 02_data_pipeline.ipynb            # Stage 2: Balanced patient-disjoint fold splits
├── 03_ablation.ipynb                 # Stage 3: Feature pool & cross-attention ablation matrix
├── 04_multitask.ipynb                # Stage 4: Production model multi-task training
└── 05_baselines.ipynb                # Stage 5: Rigorous comparative baseline suites
