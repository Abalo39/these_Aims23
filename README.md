# MultiMagNet: A Multi-Magnification Fusion Framework for Robust Breast Cancer Histopathology Diagnosis

> **MSc Thesis — African Institute for Mathematical Sciences (AIMS), South Africa**
> **Google DeepMind Scholar | 2023–2025**

---

## 📌 Overview

**MultiMagNet** is a deep learning framework for automated breast cancer diagnosis from histopathology whole-slide images. It fuses feature representations extracted at **four magnification levels** (40×, 100×, 200×, 400×) using attention-gated fusion, achieving robust and interpretable predictions across two benchmark datasets.

The framework addresses three core challenges in computational pathology:
- **Multi-scale information integration** across magnification levels
- **Missing-view robustness** via diffusion-based imputation
- **Calibrated and trustworthy predictions** under distribution shift

---

## 🏗️ Repository Structure

```
these_Aims23/
│
├── MultiMagNet_v01_needs_#1_#2_#4.html   # Full experimental notebook (HTML export)
├── LICENSE
└── README.md
```

> ⚠️ **Note:** The full Jupyter notebook (`.ipynb`) and model weights are large files currently being prepared for upload. Check back shortly for the complete experimental pipeline.

---

## 🔬 Framework Architecture

MultiMagNet consists of the following modules:

| Module | Description |
|---|---|
| **Stream Encoders** | Independent CNN encoders per magnification (40×, 100×, 200×, 400×) |
| **Attention-Gated Fusion** | Dynamically weights magnification streams by learned relevance |
| **Missing-View Imputation** | Diffusion model reconstructs missing magnification streams at inference |
| **Calibration Module** | Temperature scaling to reduce Expected Calibration Error (ECE) |
| **OOD Detection** | Out-of-distribution detection for deployment reliability |
| **SHAP Explainability** | Stream-level importance attribution via SHAP values |

---

## 📊 Datasets

### 1. BreakHis
- Breast cancer histopathology images at 4 magnification levels: 40×, 100×, 200×, 400×
- Binary classification: **Benign vs. Malignant**
- Used for primary benchmarking of multi-magnification fusion

### 2. BACH (ICIAR 2018 Grand Challenge)
- Breast tissue images with **4-class classification**: Normal, Benign, In Situ Carcinoma, Invasive Carcinoma
- Single magnification — used to evaluate cross-dataset generalization

---

## ⚙️ Configurations

The framework was evaluated across multiple fusion configurations (E1–E10). The **best-performing configuration** is:

> **E10 — Full Attention-Gated Fusion** (all 4 streams + attention + calibration)

SHAP explainability analysis was conducted on **configuration E9** to assess individual stream contributions prior to full fusion.

---

## 📈 Key Results

| Metric | Result |
|---|---|
| **AUC** | State-of-the-art on BreakHis |
| **Accuracy** | Competitive across magnification levels |
| **F1 Score** | Robust across class imbalance |
| **MCC** | Strong multi-class performance on BACH |
| **ECE** | Reduced via temperature scaling calibration |
| **OOD AUC** | Reliable out-of-distribution detection |

> Full numerical results are available in the thesis document and the experimental notebook.

---

## 🚀 Getting Started

### Prerequisites

```bash
Python >= 3.9
PyTorch >= 2.0
CUDA-enabled GPU (A100 recommended)
```

### Installation

```bash
git clone https://github.com/Abalo39/these_Aims23.git
cd these_Aims23
pip install -r requirements.txt
```

> ⚠️ `requirements.txt` will be added with the full notebook upload.

### Running Experiments

```bash
# Launch notebook
jupyter notebook MultiMagNet_v01.ipynb
```

---

## 🧠 Explainability

SHAP (SHapley Additive exPlanations) values were computed at the **stream level** to identify which magnification contributed most to correct diagnoses. This analysis supports clinical interpretability by showing which scale of tissue structure is most diagnostically relevant for each prediction.

---

## 👤 Author

**Kouyakou-Abalo Simsoba (Serge)**
- MSc in Artificial Intelligence — AIMS South Africa
- Google DeepMind Scholar
- African Union Scholar — PAUSTI/JKUAT, Kenya
- First-author publication in **IEEE Access (Q1)**

📧 Contact: [GitHub Profile](https://github.com/Abalo39)

---

## 🏛️ Acknowledgements

This work was carried out under the African Institute for Mathematical Sciences (AIMS) MSc in Artificial Intelligence programme, supported by the **Google DeepMind Scholarship**. Special thanks to my thesis supervisor and to the AIMS teaching team for their guidance and support throughout this research.

---

## 📄 License

This project is licensed under the terms in the [LICENSE](./LICENSE) file.

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@mastersthesis{simsoba2025multimagnet,
  title     = {MultiMagNet: A Multi-Magnification Fusion Framework for Robust Breast Cancer Histopathology Diagnosis},
  author    = {Kouyakou-Abalo Simsoba},
  school    = {African Institute for Mathematical Sciences (AIMS)},
  year      = {2025},
  address   = {South Africa},
  note      = {Google DeepMind Scholar}
}
```

---

*Made with ❤️ at AIMS South Africa*
