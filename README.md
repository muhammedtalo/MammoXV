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
* **Task 3 (Screening):** Flags Malignant vs. Normal tissue ($\text{AUC} = \mathbf{0.9743}$).

---

## 📂 Repository Topology & Code Navigation

The project dataset folder is organized as follows:

```text

├── Dataset/           
   ├── CC/                           
   │   ├── Normal/                  
   │   ├── Benign/
   │   └── Malign/
   └── MLO/                          
       ├── Normal/
       ├── Benign/
       └── Malign/
               
