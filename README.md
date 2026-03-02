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

- **Vocabulary size capped at 15,000**
- **Maximum sequence length:** 20 tokens
- Dataset split:
- Training: 40,000
- Validation: 5,000
- Test: 5,000

---

## 🧠 Model Architecture
The model follows the **standard Transformer Encoder–Decoder design**:

### Encoder
- Token Embedding + Positional Embedding
- Multi-Head **Self-Attention**
- Feed Forward Network
- Residual connections with Layer Normalization

### Decoder
- Token Embedding + Positional Embedding
- **Masked Self-Attention**
- **Cross-Attention**  
- Queries (Q): Decoder (Spanish)
- Keys & Values (K, V): Encoder (English)
- Feed Forward Network
- Residual connections with Layer Normalization

### Hyperparameters
- `d_model = 256`
- `num_heads = 4`
- Single encoder and decoder layer
- Optimizer: **Adam**

---

## 🏋️ Training
- Training epochs: **20 (exact)**
- Loss: **Sparse Categorical Cross-Entropy**
- Padding tokens ignored during loss calculation
- Teacher forcing used during training
- Training and validation loss curves are plotted to demonstrate learning

---

## 🔍 Inference
- **Greedy decoding** strategy
- Translation starts with the `start` token
- Tokens generated one-by-one
- Decoding stops when:
- `end` token is generated, or
- Maximum length (20 tokens) is reached

---

## 📊 Results
- The model successfully learns alignment between English and Spanish using cross-attention.
- Due to limited data, word-level tokenization, and greedy decoding, translations may show repetition.
- This behavior is expected and does not affect the correctness of the implementation.

Five translation examples from the test set are included in the notebook output.

---

## 📈 Visualization
- A plot comparing **Training Loss vs Validation Loss** is included to show convergence.

---

## 📄 Files Included
- `m24aid027_assign_2.ipynb` – Complete Google Colab notebook with code, training, plots, and outputs
- `README.md` – Project documentation (this file)

---

## 📝 Notes
- No pretrained models or external Transformer libraries were used.
- All attention mechanisms were implemented explicitly to ensure conceptual clarity.
- The project emphasizes **architecture correctness** and **attention flow**, not state-of-the-art translation quality.

---

## ✅ Conclusion
This project demonstrates a complete, end-to-end implementation of a Transformer-based NMT system with explicit cross-attention, adhering strictly to academic constraints and showcasing a clear understanding of Transformer internals.

