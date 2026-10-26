# Data Analytics ML Challenge 2026-2
## Laboratorio 1: Predicción de entregas tardías en comercio electrónico (Olist)

**Estudiante ID:** 27  
**Institución:** Universidad Central  
**Profesor:** Elias Buitrago Bolivar  

---

## Descripción del Proyecto

Este repositorio contiene el desarrollo del **Laboratorio 1 (Semana 12)** para el reto de analítica de datos e inteligencia artificial. El objetivo principal es construir y evaluar un modelo predictivo supervisado (Clasificación) capaz de anticipar qué pedidos de comercio electrónico tienen riesgo de entregarse después de la fecha comprometida (`is_late = 1`).

El proyecto analiza datos transaccionales anonimizados de **Olist** (Brasil), integrando información de pedidos, productos, clientes, vendedores y métodos de pago disponibles al momento de confirmar la compra.

---

## Configuración del Estudiante (ID: 27)

* **ID Asignado:** `27`
* **Semilla Numérica:** `1027`
* **Muestra Seleccionada:** 35,000 pedidos reales estratificados.
* **Partición de Datos:**
  * **Entrenamiento (70%):** 24,500 pedidos
  * **Validación (15%):** 5,250 pedidos
  * **Prueba Final (15%):** 5,250 pedidos *(reservados para la semana 16)*

---

## Estructura del Repositorio

```text
├── data/
│   ├── raw/          # Datos originales sin procesar (no subidos a GitHub)
│   └── processed/    # Muestras procesadas interactivas
├── notebooks/
│   └── S12_ML_Challenge.ipynb  # Cuaderno principal de análisis e integración
├── reports/
│   └── S12_resultados_ID_27.json # Informe final con métricas y huella de ejecución
├── src/              # Módulos y funciones reutilizables
└── README.md         # Descripción general del repositorio
```

> **Nota:** Los archivos `.csv` de Olist no se incluyen directamente en el repositorio debido a su tamaño; se consumen desde la fuente pública con revisión fija registrada en el cuaderno.

---

## Flujo de Trabajo y Tecnologías

1. **Integración de Fuentes:** Consolidación de 7 tablas relacionales a nivel de pedido (`order_id`).
2. **Preprocesamiento:** Imputación de nulos (mediana/moda), escalado de variables numéricas (`StandardScaler`) y codificación categórica (`OneHotEncoder`) dentro de un `Pipeline` de Scikit-Learn para evitar fugas de información (*data leakage*).
3. **Modelado Base:** Comparación entre un modelo de referencia (`DummyClassifier`) y un modelo de Regresión Logística ajustado.
4. **Métricas de Evaluación:** Evaluación integral mediante `Accuracy`, `Precision`, `Recall`, `F1-Score`, `ROC-AUC` y `Average Precision`.
5. **Análisis de Impacto y Negocio:** Evaluación de errores por segmentos geográficos/temporales y análisis de costo operativo basado en falsos positivos (R$ 8) y falsos negativos (R$ 35).

---

## Instrucciones de Ejecución

1. Abrir el archivo `notebooks/S12_ML_Challenge.ipynb` en Google Colab o en un entorno de Jupyter con Python 3.x.
2. Confirmar que la variable `ID_ESTUDIANTE = 27` esté configurada correctamente.
3. Ejecutar todas las celdas en orden secuencial.
4. Validar que la celda de **Autoverificación** finalice con la salida `Autoverificación superada.`.
5. El informe final formateado se exportará automáticamente a `reports/S12_resultados_ID_27.json`.