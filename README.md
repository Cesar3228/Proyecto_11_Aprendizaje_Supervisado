# Proyecto_11_Aprendizaje_Supervisado
## Predicción de abandono de clientes (Churn) en Beta Bank  
## Customer Churn Prediction at Beta Bank

---

## 🧩 Descripción general / Overview

### 🇪🇸 Español

Los clientes de **Beta Bank** están abandonando el banco de forma gradual cada mes. Dado que **retener clientes existentes es más barato que adquirir nuevos**, resulta fundamental identificar con anticipación a los clientes con alto riesgo de abandono.

En este proyecto se desarrolló un **modelo de clasificación** para predecir si un cliente abandonará el banco (`Exited = 1`) o no (`Exited = 0`), utilizando información histórica de comportamiento financiero y datos demográficos.

El objetivo principal fue **maximizar el F1-score**, alcanzando al menos **0.59 en el conjunto de prueba**, y evaluar adicionalmente el modelo mediante la métrica **AUC-ROC**.

Este proyecto corresponde al **Sprint 11 – Machine Learning (Churn Prediction)** del programa de **Data Science de TripleTen**.

---

### 🇬🇧 English

Customers of **Beta Bank** are gradually leaving the bank every month. Since **retaining existing customers is cheaper than acquiring new ones**, predicting customer churn is a critical business task.

In this project, a **classification model** was built to predict whether a customer will leave the bank (`Exited = 1`) or not (`Exited = 0`), using historical behavioral and demographic data.

The main objective was to **maximize the F1-score**, reaching at least **0.59 on the test set**, and to further evaluate the model using the **AUC-ROC** metric.

This project corresponds to **Sprint 11 – Machine Learning (Churn Prediction)** from the **TripleTen Data Science program**.

---

## 📂 Datos / Data

### Archivo / File
- Ruta / Path: `/datasets/Churn.csv`

### Características / Features
- `RowNumber` — índice del registro  
- `CustomerId` — identificador único del cliente  
- `Surname` — apellido  
- `CreditScore` — puntaje de crédito  
- `Geography` — país de residencia  
- `Gender` — género  
- `Age` — edad  
- `Tenure` — años en el banco  
- `Balance` — saldo de la cuenta  
- `NumOfProducts` — número de productos bancarios  
- `HasCrCard` — tiene tarjeta de crédito (1 = sí, 0 = no)  
- `IsActiveMember` — cliente activo (1 = sí, 0 = no)  
- `EstimatedSalary` — salario estimado  

### Variable objetivo / Target
- `Exited` — el cliente abandonó el banco (1 = sí, 0 = no)

---

## 🔍 Metodología / Methodology

### 🇪🇸 Español

1. **Preparación de datos**
   - Eliminación de variables irrelevantes (identificadores y apellidos).
   - Codificación de variables categóricas.
   - Escalado de características numéricas cuando fue necesario.
   - División del dataset en conjuntos de **entrenamiento**, **validación** y **prueba**.

2. **Análisis del desbalance de clases**
   - Identificación de un desbalance significativo entre clientes que abandonan y los que permanecen.
   - Entrenamiento inicial de modelos sin corrección del desbalance para evaluar su impacto en el F1-score.

3. **Corrección del desbalance**
   - Uso de **ajuste del umbral de decisión**.
   - Configuración de **parámetros de balanceo en el modelo**.
   - Comparación de resultados entre enfoques.

4. **Entrenamiento y selección del modelo**
   - Evaluación de distintos modelos de clasificación.
   - Selección del modelo con mejor equilibrio entre **F1-score** y **AUC-ROC**.

5. **Evaluación final**
   - Evaluación del modelo final en el conjunto de prueba.

---

### 🇬🇧 English

1. **Data preparation**
   - Removal of irrelevant features (IDs and surnames).
   - Encoding categorical variables.
   - Scaling numerical features when needed.
   - Splitting the data into **training**, **validation**, and **test** sets.

2. **Class imbalance analysis**
   - Identification of a strong imbalance between churned and retained customers.
   - Initial model training without imbalance correction to assess its impact on F1-score.

3. **Handling class imbalance**
   - **Decision threshold tuning**.
   - Model-level balancing strategies.
   - Comparison across approaches.

4. **Model training and selection**
   - Training and evaluating multiple classification models.
   - Selection of the best model based on **F1-score** and **AUC-ROC**.

5. **Final evaluation**
   - Final performance assessment on the test set.

---

## 🤖 Resultados del modelo / Model Results

### ✅ Modelo final
- **RandomForestClassifier**
- Umbral de decisión óptimo: **0.28**

---

### 📊 Métricas en el conjunto de prueba

- **F1-score (test): 0.615**
- **AUC-ROC (test): 0.857**

✅ El F1-score supera el umbral mínimo requerido (**0.59**).

---

### 🧮 Reporte de clasificación (test)

| Clase | Precision | Recall | F1-score | Support |
|------|----------|--------|----------|---------|
| 0 (No churn) | 0.91 | 0.87 | 0.89 | 1593 |
| 1 (Churn)    | 0.56 | 0.68 | 0.61 | 407 |

- **Accuracy total:** 0.83  
- **Macro avg F1:** 0.75  
- **Weighted avg F1:** 0.83  

Estos resultados muestran un buen equilibrio entre la detección de clientes que abandonan y la precisión en clientes que permanecen.

---

### 📈 AUC-ROC
El valor **AUC-ROC = 0.857** indica que el modelo tiene una **alta capacidad discriminativa**, diferenciando correctamente entre clientes que abandonan el banco y aquellos que permanecen.

---

## 📁 Estructura del repositorio / Repository Structure

```text
.
├── Proyecto_11.ipynb
├── requirements.txt
└── README.md
