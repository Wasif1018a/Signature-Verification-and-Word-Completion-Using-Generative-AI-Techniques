# Signature Verification and Word Completion using Generative AI

*Author: Wasif Mehboob*

## 📌 Project Overview

This project explores two very different applications of deep learning:

1. **Signature Verification** – Classifying handwritten signatures using a CNN, compared against a manual HOG+SVM approach.
2. **Word Completion** – A word-level LSTM trained on Shakespeare’s plays to predict the next word in a sentence, with an interactive interface.

Everything (data preprocessing, model building, training, evaluation, visualization, and the interface) is implemented inside **`main.ipynb`**.

---

## 🔑 Key Features

### **Signature Verification**

* **Preprocessing:** Grayscale → Resize (128×128) → Normalize
* **Models:**

  * CNN with Conv, MaxPooling, Dense + Dropout
  * HOG + SVM (linear kernel)
* **Results:**

  * CNN: ~92% training accuracy, 100% on limited test set
  * HOG+SVM: ~86% accuracy

---

### **Word Completion**

* **Dataset:** Shakespeare’s plays
* **Architecture:** Embedding (100-dim) → 2× LSTMs (128 units) → Dense + softmax
* **Training:**

  * 10 epochs ≈ 1 hr (Kaggle T4 GPU)
  * ~40% accuracy after 50 epochs
* **Interface:**

  * Streamlit script included in the **last notebook cell**
  * Generates an **ngrok link** when that cell is run
* **Examples:**

  * “to be or not” → *“to”*
  * “all the world’s a” → *“stage”*

---

## 📊 Results Summary

| Task                   | Model            | Accuracy                  | Notes                                  |
| ---------------------- | ---------------- | ------------------------- | -------------------------------------- |
| Signature Verification | CNN              | ~92% (train), 100% (test) | Outperforms HOG+SVM                    |
| Signature Verification | HOG + SVM        | ~86%                      | Simpler but weaker                     |
| Word Completion        | LSTM (50 epochs) | ~40%                      | Predictions improve with more training |

---

## 🚀 How to Run

1. Open **`main.ipynb`** in Jupyter / Colab / Kaggle.
2. Run preprocessing + training cells for either:

   * **Signature Verification (CNN / HOG+SVM)**
   * **Word Completion (LSTM)**
3. To launch the **interactive word completion app**:

   * Scroll to the **last cell** of the notebook
   * Run it → An **ngrok link** will be generated
   * Open the link in your browser to use the app

---

## 📂 Datasets Used

* [Signature Verification Dataset](https://www.kaggle.com/datasets/robinreni/signature-verification-dataset)
* [Shakespeare Plays Dataset](https://www.kaggle.com/datasets/kingburrito666/shakespeare-plays)

---

## 📖 References

* Hochreiter & Schmidhuber (1997). *Long Short-Term Memory*. Neural Computation.
* LeCun, Bengio & Hinton (2015). *Deep Learning*. Nature.
* Kaggle Datasets: Signature Verification & Shakespeare Plays

---

## ✨ Conclusion

* CNN clearly outperformed the HOG+SVM approach for signature verification.
* The LSTM model, while resource-heavy and initially modest in accuracy, shows promise with coherent next-word predictions.
* The project demonstrates how deep learning can be applied to **visual data (signatures)** and **text data (Shakespeare)** within a single pipeline.

---
