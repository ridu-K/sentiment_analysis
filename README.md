# Sentiment Analysis of Indian Fashion E-Commerce Reviews using BERT

## 📌 Project Overview

With the rapid growth of **e-commerce in India**, especially in the **online fashion sector**, understanding customer sentiment has become crucial for brands to stay competitive. Customers frequently share opinions through reviews, but these reviews are often subjective, context-dependent, and linguistically nuanced.

This project applies **transformer-based Natural Language Processing (NLP)** models—primarily **BERT (Bidirectional Encoder Representations from Transformers)**—to perform **sentiment analysis** on customer reviews from popular Indian fashion e-commerce platforms such as:

* **Myntra**
* **Ajio**
* **Tata Cliq**

The objective is to evaluate the effectiveness of **BERT** in capturing nuanced customer sentiment and to **compare its performance with DistilBERT** in terms of accuracy and efficiency.

---

## 🎯 Objectives

* Perform sentiment analysis on Indian fashion e-commerce customer reviews
* Normalize star ratings into sentiment classes (Negative, Neutral, Positive)
* Fine-tune **BERT Base (Cased)** for sentiment classification
* Compare performance with **DistilBERT**
* Analyze classification errors and subjective sentiment cases
* Extract meaningful insights for brand-level decision-making

---

## 🧠 Models Used

### 1. BERT (Base – Cased)

* Bidirectional transformer architecture
* Captures contextual and semantic meaning of text
* Fine-tuned for 3-class sentiment classification

### 2. DistilBERT

* Lightweight distilled version of BERT
* Faster inference
* Used for comparative evaluation

---

## 📊 Dataset Description

* **Total Reviews**: ~7,500
* **Source**: Publicly available customer reviews from Indian fashion platforms
* **Ratings**: 1 to 5 stars

### Sentiment Normalization

| Rating | Sentiment |
| ------ | --------- |
| 1-star | Negative  |
| 2-star | Negative  |
| 3-star | Neutral   |
| 4-star | Positive  |
| 5-star | Positive  |

This normalization reduces subjectivity caused by individual rating behavior and improves consistency in sentiment classification.

---

## ⚙️ Methodology

### 1. Text Preprocessing

* Tokenization using **BERT WordPiece tokenizer**
* Maximum sequence length determined empirically

### 2. Sequence Length Selection

* Maximum token length analyzed across all reviews
* Majority of reviews contained **< 150 tokens**
* Final sequence length set to **150 tokens** to optimize performance and efficiency

### 3. Model Architecture

* **BERT Base Model**
* **Dropout Layer** (to prevent overfitting)
* **Fully Connected Layer** (3 output neurons)
* **Cross-Entropy Loss**
* **Softmax Activation** for probability estimation

---

## 🧪 Post-Processing

* Raw logits from the final layer are passed through **Softmax**
* The sentiment class with the highest probability is selected as the prediction

---

## 📈 Results

### 🔹 BERT Performance

* **Accuracy**: **92%**

| Class    | Precision | Recall | F1-Score |
| -------- | --------- | ------ | -------- |
| Negative | 0.87      | 0.96   | 0.91     |
| Neutral  | 0.90      | 0.80   | 0.85     |
| Positive | 0.94      | 0.95   | 0.94     |

---

### 🔹 DistilBERT Performance

* **Accuracy**: **89%**

| Class    | Precision | Recall | F1-Score |
| -------- | --------- | ------ | -------- |
| Negative | 0.91      | 0.86   | 0.88     |
| Neutral  | 0.83      | 0.89   | 0.86     |
| Positive | 0.93      | 0.90   | 0.92     |

📌 **Observation**:
Although DistilBERT was faster, **BERT outperformed it in accuracy**, making BERT more suitable for nuanced sentiment analysis in the Indian fashion domain.

---

## ❗ Error Analysis

Most misclassifications occurred around the **Neutral** class due to:

* Subjective weighting of pros and cons
* Mixed sentiment reviews (e.g., good quality but poor stitching)
* Rating inconsistency between text sentiment and star rating

Such errors are expected given the **subjective nature of human sentiment**.

---

## 🚀 Future Work

* Extend sentiment analysis to **multiple Indian languages**
* Use multilingual models like **mBERT** or **XLM-R**
* Capture region-specific linguistic and cultural sentiment trends
* Enable region-aware business intelligence for Indian e-commerce platforms

---

## 🛠️ Technologies Used

* Python
* PyTorch
* Hugging Face Transformers
* BERT Base (Cased)
* DistilBERT
* NumPy, Pandas
* Scikit-learn (evaluation metrics)

---

## 📚 Research Contribution

* Demonstrates effectiveness of **BERT in Indian e-commerce sentiment analysis**
* Provides comparative insights with DistilBERT
* Addresses an **under-explored domain**: Indian fashion e-commerce sentiment
* Bridges NLP research with practical retail applications

---
