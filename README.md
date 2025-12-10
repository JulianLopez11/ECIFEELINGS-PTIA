# 🧠 ECIFeelings  
### Detección Temprana de Trastorno Depresivo mediante Inteligencia Artificial

ECIFeelings es un proyecto académico desarrollado en el marco del curso **Principios y Tecnologías de Inteligencia Artificial (PTIA)** de la **Escuela Colombiana de Ingeniería Julio Garavito**.  
Su objetivo principal es utilizar técnicas de **Procesamiento de Lenguaje Natural (PLN)** y **Deep Learning** para identificar patrones lingüísticos asociados a la depresión en textos provenientes de redes sociales, específicamente **X (Twitter)**.

---

## 📋 Descripción del Problema

El trastorno depresivo es uno de los principales problemas de salud pública a nivel mundial. Su detección temprana representa un desafío significativo, ya que muchas señales de alerta presentes en el lenguaje cotidiano o en la interacción social suelen pasar desapercibidas para familiares y profesionales de la salud.

Este proyecto busca abordar esta problemática mediante el **análisis automatizado de textos**, funcionando como una **herramienta de apoyo y tamizaje**, **no como un sustituto del diagnóstico clínico**.

---

## 🎯 Objetivos

### Objetivo General
Desarrollar un modelo basado en **PLN e Inteligencia Artificial** capaz de detectar indicios de depresión en textos escritos en español.

### Meta Cuantitativa
- Superar un **80% de precisión** en la clasificación de textos.

### Enfoque Ético
- Funcionar como una herramienta de **alerta temprana**.
- Respetar la **privacidad de los datos**.
- Aclarar que su rol es únicamente de **soporte**, no de diagnóstico médico.

---

## 🛠️ Metodología y Arquitectura

El sistema se basa en una arquitectura de **Redes Neuronales Recurrentes (LSTM)**, las cuales son especialmente efectivas para procesar secuencias de texto y conservar contexto a largo plazo.

### 🔄 Flujo de Trabajo

1. **Adquisición de Datos**  
   Dataset: *Spanish Tweets Suggesting Depression* (Kaggle).

2. **Preprocesamiento**  
   - Limpieza de texto  
   - Tokenización  
   - Lematización  
   - Eliminación de *stopwords*

3. **Representación Vectorial**  
   Uso de **embeddings** para capturar relaciones semánticas entre palabras.

4. **Detección (Modelo)**  
   Red LSTM que analiza las secuencias y clasifica la probabilidad de riesgo de depresión.

---

## 💻 Tecnologías Utilizadas

- **Lenguaje:** Python  
- **Deep Learning:** TensorFlow / Keras  
- **Procesamiento de Lenguaje Natural:** spaCy, NLTK  
- **Cálculo Numérico:** NumPy  

---

## 📊 Resultados Destacados

El modelo alcanzó métricas de desempeño satisfactorias, **superando el objetivo del 80% de precisión**, tras la aplicación de técnicas de **regularización** y **manejo del desbalance de datos**.

### 🧪 Casos de Prueba Significativos

| Tipo de Caso        | Entrada de Texto                                                                 | Resultado del Modelo | Análisis |
|---------------------|-----------------------------------------------------------------------------------|----------------------|----------|
| Depresión Clara     | "Ya no tengo fuerzas para levantarme de la cama, solo quiero dormir."             | Depresión (92%)      | Identificó correctamente fatiga crónica y abulia. |
| Estado Normal       | "Hoy es un día increíble para salir a caminar con amigos."                        | No Depresión (14.8%) | Asociación correcta de términos positivos y sociales. |
| Contexto Complejo   | "Estoy triste porque mi equipo de fútbol perdió el partido."                      | No Depresión (20.1%) | Diferenció tristeza temporal de depresión patológica. |

---

## 🚀 Conclusiones

- **Viabilidad:** Es posible identificar patrones lingüísticos asociados a la depresión en textos en español utilizando Deep Learning con una precisión superior al 80%.
- **Capacidad Contextual:** La arquitectura LSTM demostró ser superior a modelos más básicos, entendiendo contextos donde palabras con carga emocional negativa no implican necesariamente depresión.
- **Limitaciones:**  
  - Falsos positivos ante **negaciones explícitas** (ej. *"No tengo depresión"*).  
  - Dificultades con **lenguaje figurado** (ej. *"Morí de risa"*).

---

## 👤 Autor

**Julian Camilo Lopez Barrero**  
Escuela Colombiana de Ingeniería Julio Garavito  

📅 **Fecha:** Deciembre 2025
