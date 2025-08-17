# 📊 Telecom X - Parte 2: Predicción de Cancelación de Clientes (Churn)

## 🚀 Propósito del Análisis
El objetivo principal de este proyecto es **predecir la cancelación (churn) de clientes** de la compañía **Telecom X**, utilizando variables relevantes que describen el comportamiento de los usuarios, su tipo de contrato, cargos y servicios contratados.  

Este análisis busca:
- Identificar los **factores más influyentes en la cancelación**.  
- Entrenar y evaluar modelos de machine learning para predecir el churn.  
- Proponer **estrategias de retención** basadas en los hallazgos.  

---
## ⚙️ Preparación de los Datos

1. **Clasificación de variables**:
   - **Categóricas**: Género, método de pago, tipo de contrato, servicio de internet, etc.
   - **Numéricas**: Tenure (antigüedad), cargos mensuales, cargos totales, cuentas diarias.

2. **Normalización y Codificación**:
   - Se aplicó **OneHotEncoder** a variables categóricas.
   - Variables numéricas fueron **escaladas/normalizadas** para modelos sensibles a magnitudes (ej. KNN).

3. **Separación en conjuntos**:
   - Datos divididos en **80% entrenamiento** y **20% validación/prueba**.
   - Semilla fija (`random_state=42`) para reproducibilidad.

4. **Justificación de modelización**:
   - Se probaron **Árbol de Decisión** y **KNN**.
   - KNN resultó con mejor **balance entre precisión, recall y F1-score**, siendo elegido como modelo base.
   - La métrica priorizada fue **F1-score**, dado que el problema busca equilibrio entre precisión y recall para predecir clientes en riesgo.

---

## 📊 Análisis Exploratorio (EDA)

Durante el EDA se identificaron patrones clave:

- Clientes con **contrato mes a mes** presentan mayor probabilidad de cancelar.  
- La **baja antigüedad (tenure bajo)** está fuertemente asociada al churn.  
- Los usuarios de **fibra óptica** registran tasas de cancelación más altas.  
- **Cargos altos** (mensuales y totales) influyen en la decisión de cancelar.  

## ✅ Resultados Finales

Modelo seleccionado: KNN

Métricas en validación:

Accuracy: 0.77

Precision: 0.57

Recall: 0.49

F1-score: 0.53

Los resultados confirman que el KNN permite identificar con mayor equilibrio a los clientes en riesgo de cancelar, y junto con el análisis de variables importantes, brinda información valiosa para diseñar estrategias de retención segmentadas.
