# 🧠 ECIFeelings  
### Early Detection of Depressive Disorder using Artificial Intelligence

ECIFeelings is an academic project developed within the framework of the **Principles and Technologies of Artificial Intelligence (PTIA)** course at the **Julio Garavito Colombian School of Engineering**.
Its main objective is to use **Natural Language Processing (NLP)** and **Deep Learning** techniques to identify linguistic patterns associated with depression in texts from social networks, specifically **X (Twitter)**.

---

## 📋 Problem Description

Depressive disorder is one of the leading public health problems worldwide. Early detection presents a significant challenge, as many warning signs present in everyday language or social interaction often go unnoticed by family members and healthcare professionals.
This project aims to address this issue through the automated analysis of texts, functioning as a support and screening tool, not as a substitute for clinical diagnosis.

---


## 🎯 Objectues

### General Objective
Develop a model based on **NLP and Artificial Intelligence** capable of detecting signs of depression in texts written in Spanish.

### Quantitative Goal
- To exceed **80% accuracy** in text classification.

### Ethical Approach
- To function as an **early warning** tool.
- Respect the **privacy of data**.
- To clarify, their role is solely **support**, not medical diagnosis.

---

## 🛠️ Methodology and Architecture

The system is based on a **Recurrent Neural Network (LSTM)** architecture, which are especially effective at processing text sequences and preserving long-term context.

### 🔄 Workflow

1. **Workflow**  
   Dataset: *Spanish Tweets Suggesting Depression* (Kaggle).

2. **Preprocessing**  
   - Text Cleaning 
   - Tokenization  
   - Lemmatization  
   - Removal of *stopwords*

3. **Vector Representation**  
   Use of **embeddings** to capture semantic relationships between words.

4. **Detection (Model)**  
   LSTM network that analyzes sequences and classifies the probability of depression riskón.

---

## 💻 Technologies Used

- **Language:** Python 
- **Deep Learning:** TensorFlow / Keras 
- **Natural Language Processing:** spaCy, NLTK 
- **Numerical Calculation:** NumPy 

---

## 📊 Featured Results

The model achieved satisfactory performance metrics, **exceeding the target of 80% accuracy**, after the application of **regularization** and **data imbalance management** techniques.

### 🧪 Significant Test Cases

| Tipo de Caso        | Entrada de Texto                                                                 | Resultado del Modelo | Análisis |
|---------------------|-----------------------------------------------------------------------------------|----------------------|----------|
| Clear Depression     | "Ya no tengo fuerzas para levantarme de la cama, solo quiero dormir."             | Depression (92%)      | He correctly identified chronic fatigue and abulia. |
| Normal State       | "Hoy es un día increíble para salir a caminar con amigos."                        | No Depression (14.8%) | Correct association of positive and social terms. |
| Complex Context   | "Estoy triste porque mi equipo de fútbol perdió el partido."                      | No Depression (20.1%) | He differentiated temporary sadness from pathological depression.. |

---

## 🚀 Conclusions

- **Feasibility:** It is possible to identify linguistic patterns associated with depression in Spanish texts using Deep Learning with an accuracy greater than 80%.
- **Contextual Capacity:** The LSTM architecture proved to be superior to more basic models, understanding contexts where words with negative emotional content do not necessarily imply depression.
- **Limitations:**  
   - False positives in the face of **explicit denials** (e.g., *"I don't have depression"*).
   - Difficulties with **figurative language** (e.g., *"I died laughing"*).
     
---

## 👤 Autor

**Julian Camilo Lopez Barrero**  
Escuela Colombiana de Ingeniería Julio Garavito  

📅 **Fecha:** December 2025
