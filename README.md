# 🧬 MirrorDB: Privacy-First Synthetic Data Generator

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-CTGAN-green)
![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)



## 📖 About The Project

In today's data-driven world, organizations face a critical bottleneck: the **"Privacy-Utility Tradeoff."** Data scientists need access to rich data to train models, but strict privacy regulations (GDPR, CCPA, HIPAA) make it legally risky to share sensitive records. Traditional anonymization techniques often destroy the usefulness of the data or leave it vulnerable to reverse-engineering.

**MirrorDB** is an end-to-end, privacy-first synthetic data generation platform. It acts as a "digital twin" engine for tabular databases. Using a **Conditional Tabular Generative Adversarial Network (CTGAN)**, MirrorDB deep-learns the mathematical distributions and feature correlations of a sensitive dataset to generate a completely new, synthetic dataset. 

This synthetic "twin" contains **zero real user records**, ensuring absolute privacy while maintaining the statistical integrity and predictive utility of the original data.

### ✨ Key Features
* **High-Fidelity Generation:** Uses state-of-the-art CTGAN architectures optimized for tabular data (handling both continuous and categorical variables).
* **GPU-Accelerated:** Built to seamlessly utilize NVIDIA T4 GPUs for rapid model training.
* **Interactive Dashboard:** A user-friendly Streamlit frontend for non-technical stakeholders to train models and generate data.
* **Automated Validation Suite:** Mathematically proves data viability through correlation heatmaps, distribution plots, and Machine Learning Utility scoring (using Random Forest classifiers).
* **Instant Deployment:** Includes a tunneling architecture to deploy instantly from cloud notebooks.

---

## 🛠️ Technologies Used

**Core ML & Data Engineering:**
* Python
* SDV (Synthetic Data Vault) / CTGAN
* Scikit-Learn
* Pandas & NumPy

**Visualization & Frontend:**
* Streamlit
* Seaborn & Matplotlib

**Infrastructure:**
* Google Colab (NVIDIA T4 GPU)
* PyTorch (CUDA)
* Localtunnel

---

## 🚀 Getting Started (Google Colab)

Because training Generative Adversarial Networks requires significant compute power, this project is optimized to run on the **Google Colab Free Tier** utilizing a T4 GPU.

### Prerequisites
1. A Google Account (to access Google Colab).
2. The `MirrorDB_Colab.ipynb` notebook from this repository.

### Installation & Execution
1. Open [Google Colab](https://colab.research.google.com/) and upload the notebook.
2. Navigate to **Runtime > Change runtime type** and select **T4 GPU**.
3. Run **Cell 1** to install all dependencies (`ctgan`, `streamlit`, `localtunnel`, etc.).
4. Run **Cell 2** to write the `app.py` script to the local Colab storage.
5. Run **Cell 3** to launch the backend and frontend.
   * *Note: Cell 3 will output an **Endpoint IP address**.*
6. Click the generated `loca.lt` URL, paste the Endpoint IP into the security checkpoint, and your MirrorDB dashboard will be live!

---

## 📊 The Validation Suite

MirrorDB doesn't just generate data; it proves its worth. The built-in validation suite outputs three key metrics:
1. **Distribution Overlap:** Visual proof (KDE plots) that the synthetic data matches the real data's shape.
2. **Correlation Heatmaps:** Side-by-side matrices proving the "hidden logic" and relationships between columns were captured.
3. **ML Utility Score:** The system trains a Random Forest model on the *Real* data and one on the *Synthetic* data, testing both against a real holdout set. A high utility retention score proves the synthetic data is ready for downstream analytics.

---

## 📄 License

Distributed under the Apache 2.0 License. See `LICENSE` for more information.
