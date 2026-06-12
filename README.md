# ECIFeelings
### Early Detection of Depressive Disorder using Artificial Intelligence

ECIFeelings is an academic project developed as part of the **Principles and Technologies of Artificial Intelligence (PTIA)** course at the **Escuela Colombiana de Ingeniería Julio Garavito**.

Its main goal is to apply **Natural Language Processing (NLP)** and **Deep Learning** techniques to identify linguistic patterns associated with depression in Spanish-language social media texts, specifically from **X (Twitter)**.

> **Disclaimer:** This tool is intended for research and early-warning support only. It is **not a substitute for clinical diagnosis**. If you or someone you know is struggling, please contact a mental health professional.

---

## Problem Description

Depressive disorder is one of the leading public health challenges worldwide. Early detection is difficult because many warning signs appear subtly in everyday language and social interactions, often going unnoticed by family members and healthcare professionals alike.

This project addresses that gap through **automated text analysis**, acting as a **screening and support tool** rather than a replacement for clinical evaluation.

---

## Objectives

**General Goal**
Build a model based on **NLP and Artificial Intelligence** capable of detecting signs of depression in texts written in Spanish.

**Quantitative Target**
- Exceed **80% accuracy** in text classification.

**Ethical Principles**
- Serve only as an **early-warning tool**.
- Respect **user data privacy**.
- Be transparent that this is a **support system**, not a medical diagnostic tool.

---

## Dataset

| Field | Detail |
|---|---|
| Source | [Spanish Tweets Suggesting Depression](https://www.kaggle.com/) — Kaggle |
| File | `spanish_tweets_suggesting_signs_of_depression_v1.csv` |
| Language | Spanish |
| Synthetic data | Normal (non-depressive) tweets generated synthetically to balance classes |
| Noise injection | 15% of labels randomly flipped to improve generalization |

The dataset is combined with synthetic normal-class samples to address class imbalance, and 15% noise injection is applied during preparation to prevent overfitting.

---

## Architecture & Methodology

The system is built on a **Recurrent Neural Network (LSTM)** architecture, which is particularly effective for processing text sequences and retaining long-range context.

### Pipeline

```
Raw Tweet
   │
   ▼
Text Cleaning      ── lowercase, remove URLs, remove special chars
   │
   ▼
Tokenization       ── vocabulary of 2,000 tokens
   │
   ▼
Padding            ── fixed sequence length of 50 tokens
   │
   ▼
Embedding Layer    ── 50-dimensional dense word vectors
   │
   ▼
SpatialDropout1D   ── 50% dropout for regularization
   │
   ▼
LSTM Layer         ── 16 units, dropout 0.4 / recurrent dropout 0.4
   │
   ▼
Dense (sigmoid)    ── binary output: depression / no depression
   │
   ▼
Prediction         ── probability score (threshold: 0.5)
```

### Key Hyperparameters

| Parameter | Value |
|---|---|
| Vocabulary size | 2,000 tokens |
| Sequence length | 50 tokens |
| Embedding dimensions | 50 |
| LSTM units | 16 |
| Spatial dropout | 0.5 |
| LSTM dropout | 0.4 |
| Recurrent dropout | 0.4 |
| Epochs | 6 |
| Batch size | 32 |
| Optimizer | Adam |
| Loss function | Binary cross-entropy |

---

## Technologies

| Category | Tools |
|---|---|
| Language | Python 3.x |
| Deep Learning | TensorFlow / Keras |
| NLP | spaCy (`es_core_news_sm`), NLTK |
| Numerical Computing | NumPy |
| Data Handling | Pandas |
| Visualization | Matplotlib |
| Evaluation | scikit-learn |

---

## How to Run

### Prerequisites

```bash
pip install tensorflow spacy nltk numpy pandas matplotlib scikit-learn
python -m spacy download es_core_news_sm
```

### Steps

1. Clone this repository:
   ```bash
   git clone https://github.com/JulianLopez11/ECIFEELINGS-PTIA.git
   cd ECIFEELINGS-PTIA
   ```

2. Make sure the dataset file is in the root directory:
   ```
   spanish_tweets_suggesting_signs_of_depression_v1.csv
   ```

3. Open and run the notebook:
   ```bash
   jupyter notebook ECIFEELINGS.ipynb
   ```

4. Run all cells in order. Training takes approximately 30–60 seconds depending on hardware.

> The notebook was developed and tested on **Google Colab**. It is recommended to run it there for best compatibility.

---

## Results

The model exceeded the 80% accuracy target after applying regularization techniques and noise injection.

### Training Performance

| Epoch | Train Accuracy | Val Accuracy | Val Loss |
|---|---|---|---|
| 1 | 66.1% | 74.0% | 0.6152 |
| 2 | 75.2% | 81.8% | 0.5016 |
| 3 | 79.6% | 83.0% | 0.4561 |
| 4 | 82.8% | 84.8% | 0.4295 |
| 5 | 83.6% | 86.8% | 0.4187 |
| **6** | **84.8%** | **87.0%** | **0.4123** |

**Final validation accuracy: 87%**

### Notable Test Cases

| Case Type | Input Text | Model Result | Analysis |
|---|---|---|---|
| Clear depression | "Ya no tengo fuerzas para levantarme de la cama, solo quiero dormir." | Depression (93%) | Correctly identified chronic fatigue and anhedonia. |
| Normal state | "Hoy es un día increíble para salir a caminar con amigos." | Normal (26.2%) | Correctly associated positive and social terms. |
| Complex context | "Estoy triste porque mi equipo de fútbol perdió el partido." | Normal (48.1%) | Distinguished temporary sadness from pathological depression. |
| Subtle symptoms | "Antes disfrutaba jugar fútbol, ahora ya no me interesa nada." | Depression (92.7%) | Detected loss of interest / anhedonia correctly. |

---

## Conclusions

- **Viability:** It is possible to identify linguistic patterns associated with depression in Spanish texts using Deep Learning with accuracy above 80%.
- **Contextual Understanding:** The LSTM architecture outperformed simpler models by capturing context — correctly handling cases where emotionally negative words do not necessarily indicate depression.
- **Limitations:**
  - False positives with **explicit negations** (e.g., *"No tengo depresión"* → model flags it as depression).
  - Struggles with **figurative language** (e.g., *"Morí de risa"* / "I died laughing" → misclassified).
  - The synthetic normal-class data may not reflect the full diversity of real non-depressive speech.

---

## Future Work

- Use **pre-trained Spanish embeddings** (e.g., FastText, Word2Vec trained on Twitter data) for richer semantic representations.
- Experiment with **transformer-based models** (e.g., BETO — BERT for Spanish) to better handle negations and figurative language.
- Expand the normal-class dataset with real, diverse tweets to reduce false positive rates.
- Add **negation handling** as a preprocessing step.
- Explore **multi-class classification** (e.g., severity levels: none / mild / moderate / severe).

---

## Project Structure

```
ECIFEELINGS-PTIA/
├── ECIFEELINGS.ipynb                              # Main notebook (model + training + evaluation)
├── spanish_tweets_suggesting_signs_of_depression_v1.csv  # Dataset
├── ECIFeelings.pdf                                # Project report (PDF)
├── LICENSE                                        # MIT License
└── README.md                                      # This file
```

- **Feasibility:** It is possible to identify linguistic patterns associated with depression in Spanish texts using Deep Learning with an accuracy greater than 80%.
- **Contextual Capacity:** The LSTM architecture proved to be superior to more basic models, understanding contexts where words with negative emotional content do not necessarily imply depression.
- **Limitations:**  
   - False positives in the face of **explicit denials** (e.g., *"I don't have depression"*).
   - Difficulties with **figurative language** (e.g., *"I died laughing"*).
     
---

## Author

- [@JulianLopez11](https://github.com/JulianLopez11)

---

## License

This project is licensed under the [MIT License](LICENSE).
