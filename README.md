# Neural Machine Translation using Transformer with Cross-Attention

## 📌 Overview
This project implements a **Neural Machine Translation (NMT)** system that translates **English sentences into Spanish** using a **Transformer-based Encoder–Decoder architecture** with an explicit **Cross-Attention mechanism**.  
The model is built **from scratch** using TensorFlow/Keras and trained on a limited subset of the Spanish–English dataset to ensure feasibility on Google Colab GPUs.

The implementation strictly follows the assignment guidelines, with a focus on understanding and correctly implementing **self-attention** and **cross-attention**.

## Transformer Architecture:
![transformers](https://github.com/user-attachments/assets/5a3618f7-3fe3-4c97-8aa6-ff125f186bef)

---

## 📂 Dataset
- **Source:** Hugging Face – `OscarNav/spa-eng`
- **Sentence Pairs Used:** First **50,000** examples only
- **Languages:**
  - English → Source
  - Spanish → Target

---

## ⚙️ Preprocessing
- All text converted to **lowercase**
- **Punctuation removed**
- Spanish sentences wrapped with special tokens:
