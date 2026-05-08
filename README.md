# 📊 Predicción de Churn en Telecomunicaciones (Telco Customer Churn)

Este proyecto desarrolla un modelo de aprendizaje automático para predecir la probabilidad de que un cliente abandone los servicios de una empresa de telecomunicaciones. El objetivo es identificar patrones de fuga y permitir que el departamento de retención actúe proactivamente para reducir la tasa de abandono.

---

## 🎯 Objetivo del Proyecto
El "Churn" o fuga de clientes es uno de los problemas más costosos en la industria de servicios. Este proyecto implementa un flujo de trabajo (Pipeline) que procesa datos de clientes y entrena un modelo predictivo optimizado, facilitando su puesta en producción mediante la exportación en formato `.pkl`.

## 📁 Estructura del Proyecto
Para mantener el orden profesional y la reproducibilidad, el repositorio sigue esta estructura:

* **`data/`**: Contiene el conjunto de datos original (`WA_Fn-UseC_-Telco-Customer-Churn.csv`).
* **`notebooks/`**: Notebook principal (`.ipynb`) con el Análisis Exploratorio de Datos (EDA), Ingeniería de Variables (Feature Engineering) y entrenamiento.
* **`models/`**: Almacena el pipeline final exportado (`pipeline_churn_model.pkl`).
* **`requirements.txt`**: Lista de dependencias necesarias para ejecutar el proyecto.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.10+
* **Procesamiento:** Pandas, NumPy.
* **Machine Learning:** Scikit-Learn (Pipelines, ColumnTransformer, GridSearchCV).
* **Evaluación:** Matplotlib, Seaborn, Scikit-Learn Metrics.
* **Exportación:** Joblib.

## ⚙️ Implementación del Pipeline
Se diseñó un **Pipeline de Scikit-Learn** que integra todas las fases del modelado para evitar la fuga de datos (*data leakage*) y asegurar la consistencia en producción:

1.  **Preprocesamiento Numérico:** Imputación de nulos mediante la mediana y escalado estándar (`StandardScaler`).
2.  **Preprocesamiento Categórico:** Imputación (valor más frecuente) y codificación (`OneHotEncoder`).
3.  **Modelo:** Se utilizó un clasificador (ej. Random Forest) optimizado mediante **GridSearchCV** y **Validación Cruzada**.

## 📈 Evaluación y Métricas
En la predicción de fuga, el **Recall (Sensibilidad)** es fundamental, ya que el costo de no detectar a un cliente que se va es mucho mayor que el de contactar a un cliente que planea quedarse.
* **Métricas analizadas:** F1-Score, Precisión, Recall y Matriz de Confusión.
* **Interpretación:** Se incluyó un análisis de importancia de variables (*Feature Importance*) para entender qué factores (tipo de contrato, cargos mensuales, etc.) impulsan la fuga.

## 🚀 Cómo ejecutar este proyecto
1.  Clonar el repositorio.
2.  Crear y activar un entorno virtual:
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # En Linux/Mac
    ```
3.  Instalar las librerías necesarias:
    ```bash
    pip install -r requirements.txt
    ```
4.  Abrir el notebook en `notebooks/` y ejecutar las celdas para reproducir el entrenamiento y la generación del archivo `.pkl`.

---
*Este proyecto forma parte del Checkpoint 8 y demuestra habilidades en la construcción de flujos de trabajo de Machine Learning robustos y escalables.*