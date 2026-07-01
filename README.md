
<img width="1469" height="562" alt="IEEE_Pix2Pix_metodology-Página-2 drawio" src="https://github.com/user-attachments/assets/496c3d8a-cb39-48d8-81e9-2ada29dca78b" />


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

## 📊 Dataset Access & Setup

This repository uses a dual-stage framework requiring two distinct dataset components. To maintain repository efficiency while ensuring full scientific reproducibility, the data is distributed as follows:


###  1) Bounding Box Localization Dataset (YOLOv8)
The open-access **MetalDetecMRI-v1** dataset containing annotated sagittal scout views for orthopedic implant localization is hosted externally via Roboflow. 

* **How to Access:** To preserve branch clean-lines, the direct download link and pipeline export tokens are stored in a standalone documentation file in this repository.
* **File Location:** Navigate to the **`MetalDetecMRI-v1.md`** file located in this repository's root directory to find the active download link.

* ###   2) Paired Image Synthesis Dataset (Pix2Pix)
The complete image pair dataset used to train and validate the generative network is hosted natively within this branch as a compressed archive.

* **File Name:** **UTFPR-Scout2PDFS-v1.zip** 
* **Location:** Located in the root directory of this branch.
* **Extraction Instructions:** Clone this repository or download the zip archive directly from the file list above.
  

## 📊 Performance Highlights

Our framework is validated quantitatively across anatomical fidelity, localization reliability, and distribution alignment suites:

* **Localization (YOLOv8n):** Achieved an $\text{mAP}_{50}$ of **0.9913** on the unseen test set, ensuring highly reliable localized bounding box extraction.
* **Structural & Spatial Fidelity:** Achieved a Mean Dice Similarity Coefficient (**DSC**) of **0.7429** via semantic validation of the signal void zones.
* **Texture & Quality Distribution:** Yielded an exceptionally low Kernel Inception Distance (**KID**) of **0.029**, proving outstanding image quality without assuming a parametric Gaussian feature form.

---

## 🎓 Citation
This work has been submitted to the IEEE SENSORS CONFERENCE 2026. The citation will be provided after the review process.
