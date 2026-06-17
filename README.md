
<img width="1470" height="525" alt="workflow_pix2pix_mri drawio" src="https://github.com/user-attachments/assets/ad3db7e4-9ecc-4464-8879-5a06a1263192" />


# pix2pix-mri-artifact-prediction
Official implementation of the YOLOv8n + Pix2Pix cGAN pipeline for predictive downstream knee MRI artifact simulation from scout scans.
# Predictive Simulation of Knee MRI Artifacts Using a Hybrid YOLOv8 and Pix2Pix Framework

Official implementation of the YOLOv8n + Pix2Pix cGAN pipeline for predictive downstream knee MRI artifact simulation from rapid structural scout scans. This framework allows MRI technicians to forecast subsequent image degradation and signal voids prior to running full clinical sequences.

---

## 📌 Framework Overview

Our proposed workflow shifts artifact assessment to the very beginning of the acquisition pipeline using a two-stage deep learning framework:
1. **Region of Interest (ROI) Localization:** A fine-tuned **YOLOv8n** network detects and isolates the boundaries of expected degradation zones directly on rapid structural localizer scans (sagittal scout views).
2. **Conditional Image Translation:** A **Pix2Pix conditional GAN (cGAN)** takes the cropped scout slice and executes a cross-modal synthesis to generate the predicted target sagittal PDFS sequence displaying localized metal artifact profiles.

<p align="center">
  </p>

---

## 📊 Performance Highlights

Our framework is validated quantitatively across anatomical fidelity, localization reliability, and distribution alignment suites:

* **Localization (YOLOv8n):** Achieved an $\text{mAP}_{50}$ of **0.9913** on the unseen test set, ensuring highly reliable localized bounding box extraction.
* **Structural & Spatial Fidelity:** Achieved a Mean Dice Similarity Coefficient (**DSC**) of **0.7429** via semantic validation of the signal void zones.
* **Texture & Quality Distribution:** Yielded an exceptionally low Kernel Inception Distance (**KID**) of **0.029**, proving outstanding image quality without assuming a parametric Gaussian feature form.

---
