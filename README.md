# Breast Cancer Image Classification with CLIP Features

A medical-imaging machine-learning project exploring whether image embeddings from a pretrained vision-language model can be used as input features for a conventional classifier.

The notebook combines **CLIP ViT-B/32 feature extraction** with **scikit-learn Logistic Regression** on the **CBIS-DDSM mammography dataset**. The approach uses CLIP as a feature extractor rather than fine-tuning the full vision-language model.

> **Research / educational project only.** This implementation is not a medical device, has not been clinically validated, and must not be used to diagnose, screen, or guide treatment.

## Problem and approach

Mammography images contain visual patterns that can be challenging to represent with handcrafted features. This project explores a transfer-learning workflow:

1. Load and prepare mammography images from CBIS-DDSM.
2. Use the pretrained CLIP ViT-B/32 image encoder to obtain image embeddings.
3. Train a Logistic Regression classifier on the extracted representations.
4. Evaluate the classifier using standard classification metrics.

The goal is to study a lightweight feature-extraction baseline, not to claim clinical performance.

## Model pipeline

```text
Mammography images
       |
       v
Image preprocessing
       |
       v
Pretrained CLIP ViT-B/32 image encoder
       |
       v
Image embeddings
       |
       v
Logistic Regression
       |
       v
Predicted class
```

## Dataset

- **Dataset:** [CBIS-DDSM](https://www.cancerimagingarchive.net/collection/cbis-ddsm/)
- **Modality:** Mammography
- **Task:** Image classification using the labels prepared for the notebook.

Dataset versions and preprocessing choices can affect the number of usable images and class distribution. Refer to the notebook's data-loading and preprocessing cells for the exact subset and label mapping used in a run.

## Technologies

- Python
- PyTorch
- CLIP / pretrained ViT-B/32 image encoder
- scikit-learn
- NumPy and Pandas
- Matplotlib / Seaborn

## Run the notebook

1. Clone this repository.
2. Open `breast-cancer-imageclassification.ipynb` in Jupyter or Google Colab.
3. Obtain access to CBIS-DDSM and arrange the dataset in the directory structure expected by the notebook.
4. Install the notebook's required Python packages.
5. Run the notebook cells in order.

The dataset is not included in this repository. A CUDA-enabled GPU may reduce feature-extraction time, but availability depends on the runtime and installed PyTorch build.

## Evaluation and reproducibility

The notebook contains the implementation and evaluation workflow. Results depend on the selected dataset subset, preprocessing, label mapping, train/test partition, and classifier configuration. No performance figure is stated here because a reproducible result should be reported together with those experimental details.

For a rigorous comparison, use a fixed and documented split, report per-class precision/recall/F1 and a confusion matrix, and guard against patient-level leakage between training and test data.

## Limitations

- CLIP was pretrained on general image-text data, not specifically validated for mammography.
- A simple classifier over embeddings is a baseline, not a clinically validated model.
- Dataset imbalance, acquisition differences, and data leakage can materially affect evaluation.
- Predictions require expert review and must not be interpreted as medical advice.

## Repository contents

- `breast-cancer-imageclassification.ipynb` — notebook containing the implementation.

---

Built by [Nuaima Saeed](https://github.com/Nuaima).
