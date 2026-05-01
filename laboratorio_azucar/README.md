# Laboratorio 1: Predicción y Clasificación en la Industria Azucarera

## Descripción general

Este proyecto académico desarrolla un análisis completo de datos históricos del Ingenio Providencia con el objetivo de aplicar técnicas de machine learning para la predicción y clasificación de variables clave en la producción de caña de azúcar.

El laboratorio aborda dos problemas principales:

* **Regresión:** predicción de:

  * `TCH` (Toneladas de caña por hectárea)
  * `%Sac.Caña` (contenido de sacarosa)
* **Clasificación:** categorización en niveles `alto`, `medio` y `bajo` de:

  * `TCH`
  * variable de sacarosa (`%Sac.Caña` o aproximación disponible)

---

## Estado actual del proyecto

El proyecto se encuentra **completamente desarrollado hasta la fase de modelamiento**, incluyendo:

* ✔️ Contexto del negocio (Parte 1)
* ✔️ Análisis exploratorio de datos – EDA (Parte 2)
* ✔️ Modelos de regresión y clasificación (Parte 3)
* ✔️ Generación de métricas, tablas y visualizaciones

---

## Objetivo general

Construir modelos predictivos y clasificadores que permitan analizar la productividad y calidad de la caña de azúcar, con el fin de generar insights útiles para la toma de decisiones en el contexto agrícola.

---

## Estructura del proyecto

```
laboratorio_azucar/
├── data/
│   ├── raw/                # datasets originales (NO versionar)
│   └── processed/          # datasets transformados
│
├── notebooks/
│   ├── 01_contexto_negocio.ipynb
│   ├── 02_carga_calidad_datos.ipynb
│   ├── 03_modelamiento.ipynb
│   └── 03_clasificacion_corregida.ipynb
│
├── outputs/
│   ├── figures/            # gráficas generadas
│   └── tables/             # métricas y resultados
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Datasets utilizados

### 1. HISTORICO_SUERTES.xlsx

Utilizado para:

* Regresión de `TCH`
* Regresión de `%Sac.Caña`

---

### 2. BD_IPSA_1940.xlsx

Utilizado para:

* Clasificación de `TCH`
* Clasificación de sacarosa

⚠️ Nota:
Este dataset no contiene `%Sac.Caña`, por lo que se utilizó la variable disponible `sacarosa` como aproximación para la construcción de clases.

---

## Metodología

### 1. Contexto del negocio

* Investigación del sector azucarero en Colombia
* Identificación de variables agronómicas relevantes
* Definición de hipótesis iniciales

---

### 2. Análisis exploratorio de datos (EDA)

* Revisión de estructura de datos
* Identificación de valores faltantes
* Detección de outliers
* Análisis de correlaciones
* Evaluación de posibles problemas de data leakage

---

### 3. Modelamiento

#### Regresión

Modelos utilizados:

* Regresión lineal
* Random Forest Regressor

Métricas:

* R²
* RMSE
* MAE

---

#### Clasificación

⚠️ Corrección aplicada:
Se realizó una corrección metodológica utilizando el dataset `BD_IPSA_1940.xlsx`, conforme al enunciado del laboratorio.

Modelos utilizados:

* DummyClassifier (baseline)
* LogisticRegression
* KNeighborsClassifier
* RandomForestClassifier

Métricas:

* Accuracy
* Precision
* Recall
* F1-score
* Cohen’s Kappa

---

## Resultados principales

* **Regresión:**
  Random Forest superó a la regresión lineal, indicando relaciones no lineales en los datos.

* **Clasificación:**
  Random Forest obtuvo el mejor desempeño general en ambas tareas (`TCH` y sacarosa).

* La clase **media** presentó mayor dificultad de clasificación, evidenciando solapamiento entre categorías.

---

## Outputs generados

### Tablas

Ubicación: `outputs/tables/`

* `mejores_regresion.csv`
* `clasificacion_corregida_mejores_*.csv`
* `resumen_regresion.csv`
* `resumen_clasificacion.csv`

---

### Figuras

Ubicación: `outputs/figures/`

Incluyen:

* Predicción vs valores reales
* Matrices de confusión
* Importancia de variables

---

## Consideraciones metodológicas

* Se evitó el uso de variables con posible **data leakage**
* Se utilizó validación tipo **hold-out (80/20)**
* Se recomienda implementar validación cruzada en trabajos futuros

---

## Limitaciones

* Datos con ruido y variabilidad
* Dificultad para separar clases intermedias
* Variables disponibles limitadas
* Aproximación de `%Sac.Caña` en clasificación

---

## Próximos pasos

* Implementar validación cruzada (k-fold)
* Optimización de hiperparámetros
* Incorporación de nuevas variables (climáticas, satelitales, etc.)
* Desarrollo de modelos más robustos

---

## Preparación del entorno

### Crear entorno virtual

```bash
python3 -m venv .venv
```

### Activar entorno

```bash
source .venv/bin/activate
```

### Instalar dependencias

```bash
pip install -r requirements.txt
```

### Ejecutar notebooks

```bash
jupyter notebook
```

---

## Consideraciones sobre datos

⚠️ IMPORTANTE:

Los datasets utilizados contienen información potencialmente sensible y **no deben subirse a repositorios públicos**.

---

## Autores

Esue Torres Morales - A00401225
Cesar Augusto Jimenez - A00401283
Juan Diego GIl - A003999
