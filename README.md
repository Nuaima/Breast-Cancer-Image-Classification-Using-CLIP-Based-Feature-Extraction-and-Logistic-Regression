Breast Cancer Image Classification Using CLIP-Based Feature Extraction and Logistic Regression

Overview

This repository presents a lightweight and interpretable pipeline for breast cancer image classification. We combine CLIP(Contrastive Language–Image Pretraining) for 
semantic-rich image feature extraction with a Logistic Regression classifier to detect benign and malignant lesions using the CBIS-DDSM dataset. Our goal 
is to demonstrate how foundation models like CLIP can be adapted to medical imaging with minimal compute and without fine-tuning.


Motivation

- Traditional deep learning approaches are often resource-intensive and lack transparency.
- CLIP provides generalized vision-language embeddings, but is underexplored in clinical tasks.
- We address this by extracting CLIP features and feeding them into a simple, explainable classifier.


Methodology

- Dataset: CBIS-DDSM, with 10,239 high-res mammograms (benign, malignant, normal).
- Feature Extraction: CLIP (ViT-B/32) used to embed images (zero-shot, no fine-tuning).
- Classifier: Logistic Regression (one-vs-rest, L2 regularization).
- Evaluation Metrics: Accuracy, Precision, Recall, F1-score.
- Experimental Setup: 80-20 train-test split, 50 epochs, batch size 32.

Repository Structure

bash
📦 Breast-Cancer-CLIP/
├── 📄 Breast-Cancer-CLIP.ipynb        # Full implementation notebook
├── 📄 Report.pdf                      # IEEE-format research paper
├── 📄 README.md                       # Project documentation
└── 📁 assets/                         # Visuals (architecture, predictions)
