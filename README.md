#  Machine Fault Detection using Vision Transformers (ViTs)

This repository contains a project on **machine fault detection** using **Vision Transformers (ViTs)**.  
We compare ViTs with traditional CNNs using accelerometer and acoustic data converted into time–frequency images.

---

##  Dataset: UORED-VAFCLS (University of Ottawa)

We use the **UORED-VAFCLS** dataset, which provides accelerometer and acoustic recordings of rolling-element bearings under constant load and speed.  
- Includes healthy and three fault conditions: inner race, outer race, ball, cage.  
- Accessible here: [UORED Dataset](https://data.mendeley.com/datasets/y2px5tg92h/5)

---

##  Project Overview

| Notebook/File              | Description |
|-----------------------------|-------------|
| `UORED_csv_to_image.ipynb`  | Convert raw CSV signals into scalograms & spectrograms (224×224 RGB). |
| `Accelerometer_ViTs.ipynb`  | Train & evaluate Vision Transformer on accelerometer data. |
| `acoustic_ViTs.ipynb`       | Train & evaluate Vision Transformer on acoustic data. |
| `CNN_machine_fault.ipynb`   | Baseline CNN implementation for comparison. |
| `Research Docs/`            | Contains the final paper and documentation. |
| `best_checkpoint/`          | Saved model checkpoints (best-performing runs). |
| `README.md`                 | This file — project description and instructions. |

---

##  Results Summary

| Model               | Accuracy (%) | Precision (%) | Recall (%) | F1-score (%) |
|---------------------|--------------|---------------|------------|--------------|
| CNN (2D Conv)       | 68.20        | 70.10         | 67.50      | 68.80        |
| ViT (Accelerometer) | 99.89        | 99.90         | 99.88      | 99.89        |
| ViT (Acoustic)      | 98.79        | 98.88         | 98.43      | 98.64        |

**Key Insight:** Vision Transformers significantly outperform CNNs in generalizing to unseen data, especially with accelerometer input achieving ~99.9% accuracy.

<p align="center">
  <img src="https://github.com/user-attachments/assets/5fded6c7-a8fb-45a1-ac84-ba87463579df" alt="result" width="80%">
</p>

##  Visual Results

###  Test Predictions (Scalograms - Accelerometer)

<p align="center">
  <img src="https://github.com/user-attachments/assets/00296e81-d565-4316-a7f0-bcb6bac13b14" alt="accelerometer_predictions" width="80%">
</p>

###  Test Predictions (Spectrograms - Acoustic)
<p align="center">
  <img src="https://github.com/user-attachments/assets/931bbad9-00bd-483e-abd4-00edb04cf02b" alt="acoustic_predictions" width="80%">
</p>

###  Attention Visualization (Acoustic)
<p align="center">
  <img src="https://github.com/user-attachments/assets/4937d015-3985-4af4-a2fe-f8aee15942ab"  alt="attention_heads" width="80%">
</p>
