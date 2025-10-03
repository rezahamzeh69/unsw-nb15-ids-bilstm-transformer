# A Robust and Interpretable Hybrid Transformer-BiLSTM for Network Intrusion Detection

This repository contains the complete source code and reproducible research pipeline for developing a robust and interpretable Intrusion Detection System (IDS) based on a hybrid Transformer-BiLSTM architecture. The project is implemented in PyTorch and is presented as a self-contained Jupyter Notebook (`robust-transformer-bilstm-ids.ipynb`).

This work demonstrates an end-to-end framework for building a high-performance IDS, with a strong focus on practical challenges such as adversarial robustness, model interpretability, and full reproducibility.

## Table of Contents
- [Key Features](#key-features)
- [Model Architecture](#model-architecture)
- [Dataset](#dataset)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Notebook](#running-the-notebook)
- [Core Methodologies](#core-methodologies)
  - [Data Preprocessing](#data-preprocessing)
  - [Adversarial Training](#adversarial-training)
  - [Model Interpretability](#model-interpretability)
- [Experimental Results](#experimental-results)
  - [Detection Performance](#detection-performance)
  - [Adversarial Robustness](#adversarial-robustness)
  - [Feature Importance](#feature-importance)
- [Reproducibility](#reproducibility)
- [Citation](#citation)
- [License](#license)

## Key Features
- **Hybrid Deep Learning Model**: A powerful architecture combining a **Transformer Encoder** for global context awareness and a **Bidirectional LSTM (BiLSTM)** for sequential pattern modeling.
- **Realistic Adversarial Robustness**: Hardened against evasion attacks using **Projected Gradient Descent (PGD)** with domain-specific constraints (i.e., perturbations are masked on categorical features).
- **Built-in Interpretability**: Provides transparent insights into model decisions using **Integrated Gradients (IG)** for feature attribution and **Attention Maps** for temporal focus.
- **End-to-End Reproducible Pipeline**: A single notebook to replicate the entire experimental workflow, from data download to final evaluation.
- **Efficient Training Framework**: Features include automatic checkpointing, auto-resume functionality, early stopping, and weighted loss for handling class imbalance.

## Model Architecture
The model processes input sequences through the following stages:
1.  **Input Projection & Positional Encoding**: Input features are projected to a 128-dimensional latent space, and sinusoidal positional encodings are added.
2.  **Transformer Encoder**: A 2-layer Transformer with 8 attention heads captures long-range dependencies.
3.  **BiLSTM Layer**: A 2-layer BiLSTM with 128 hidden units per direction models temporal dynamics.
4.  **Classification Head**: The final hidden states are concatenated and passed to a dense layer for final classification.

<!-- Optional: Add a simple diagram of the architecture here -->
<!-- ![Model Architecture Diagram](architecture.png) -->

## Dataset
This project uses the **UNSW-NB15 dataset**, a widely-used benchmark for network intrusion detection. The notebook automatically downloads the dataset in Parquet format from [KaggleHub](https://www.kaggle.com/datasets/dhoogla/unswnb15).

## Getting Started

### Prerequisites
- Python 3.8+
- PyTorch 1.12+
- CUDA-enabled GPU (recommended for faster training)
- Kaggle API credentials configured for `kagglehub` (see [Kaggle documentation](https://www.kaggle.com/docs/api))

### Installation
Clone the repository and install the required packages:
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
pip install -r requirements.txt
