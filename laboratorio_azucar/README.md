# Laboratorio 1: Predicción y Clasificación en la Industria Azucarera

## Descripción general
Este proyecto académico organiza la base de trabajo para el laboratorio **"Predicción y Clasificación en la Industria Azucarera"**, orientado al análisis de datos históricos del Ingenio Providencia.

El laboratorio completo, en fases posteriores, abordará dos líneas de modelamiento:

- Regresión para predecir `TCH`.
- Regresión para predecir `%Sac.Caña`.
- Clasificación de niveles de desempeño `alto`, `medio` y `bajo` para `TCH`.
- Clasificación de niveles de desempeño `alto`, `medio` y `bajo` para `%Sac.Caña`.

## Alcance actual
En esta entrega **solo** se deja implementada la **Parte 1**, enfocada en el entendimiento del negocio y la contextualización del problema. Por tanto, este repositorio **todavía no incluye**:

- análisis exploratorio de datos,
- preprocesamiento,
- construcción de variables,
- entrenamiento de modelos,
- validación,
- comparación de resultados,
- conclusiones cuantitativas.

## Objetivo general del laboratorio
Construir una base analítica y metodológica para estudiar variables relacionadas con productividad y calidad de caña de azúcar, con el fin de soportar futuras tareas de predicción y clasificación mediante técnicas de machine learning.

## Estructura del proyecto
```text
laboratorio_azucar/
├── data/
│   ├── raw/
│   └── processed/
├── docs/
│   └── investigacion_contexto.md
├── notebooks/
│   └── 01_contexto_negocio.ipynb
├── outputs/
│   ├── figures/
│   └── tables/
├── report/
│   ├── informe_ieee_base.md
│   └── referencias_borrador.md
├── reports/  # carpeta heredada; no usar como carpeta oficial
├── src/
│   └── __init__.py
├── .gitignore
├── README.md
└── requirements.txt
```

## Convención de carpetas
La carpeta oficial para documentos del informe es `report/`.

La carpeta `reports/` se conserva únicamente porque ya existía en la base inicial del proyecto. Por ahora no se elimina para evitar borrar contexto útil, pero **no debe usarse** como destino de nuevos archivos.

## Archivos principales
- `notebooks/01_contexto_negocio.ipynb`: notebook base para desarrollar exclusivamente la contextualización del negocio y el planteamiento inicial del problema.
- `docs/investigacion_contexto.md`: plantilla operativa para registrar fuentes, datos, citas breves y pendientes de investigación.
- `report/informe_ieee_base.md`: borrador inicial del informe en estilo IEEE, limitado a secciones tempranas de esta fase.
- `report/referencias_borrador.md`: espacio organizado para consolidar referencias encontradas.
- `requirements.txt`: dependencias mínimas para trabajo con notebooks, análisis y documentación.
- `.gitignore`: exclusiones recomendadas para entorno, salidas generadas y archivos sensibles.

## Preparación del entorno
### 1. Crear entorno virtual
```bash
python3 -m venv .venv
```

### 2. Activar entorno virtual
En macOS o Linux:
```bash
source .venv/bin/activate
```

En Windows:
```bash
.venv\Scripts\activate
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 4. Registrar kernel de Jupyter
```bash
python -m ipykernel install --user --name laboratorio_azucar --display-name "Python (laboratorio_azucar)"
```

## Cómo abrir el notebook
Desde la raíz del proyecto:
```bash
jupyter notebook
```

Luego abrir:

- `notebooks/01_contexto_negocio.ipynb`

## Consideraciones sobre datos
Los datos del ingenio, bases operativas, archivos exportados y cualquier documento con información sensible o propietaria **no deben publicarse en repositorios públicos** sin autorización expresa.

Recomendación:

- almacenar insumos originales en `data/raw/`,
- guardar versiones transformadas en `data/processed/`,
- revisar antes de cada `commit` que no se estén versionando archivos sensibles.

## Estado actual del proyecto
Actualmente el repositorio deja lista la base para:

- redactar la introducción del problema,
- documentar el contexto del sector azucarero,
- definir conceptualmente `TCH` y `%Sac.Caña`,
- plantear hipótesis iniciales,
- preparar la transición a la siguiente fase de exploración de datos.

## Próximos pasos
En las siguientes fases del laboratorio se desarrollará:

- carga y revisión del dataset,
- análisis exploratorio de datos,
- evaluación de calidad de datos,
- preprocesamiento,
- selección y transformación de variables,
- modelos de regresión y clasificación,
- validación y análisis de resultados.
