# TFM EUR/USD

Este repositorio contiene el código, los notebooks y los conjuntos de datos utilizados en el Trabajo Fin de Máster sobre predicción de la dirección diaria del tipo de cambio EUR/USD mediante técnicas de aprendizaje automático.

El objetivo del proyecto es analizar si, utilizando información histórica y variables técnicas, es posible predecir si el cierre de la siguiente jornada del EUR/USD será superior o inferior al cierre actual.

## Estructura del proyecto

El proyecto está organizado principalmente en tres carpetas:

- `notebooks/`: contiene todo el desarrollo realizado en Jupyter Notebook.
- `data/`: contiene los datos originales y los conjuntos procesados utilizados durante el análisis.
- `outputs/`: contiene tablas y gráficos generados durante el proyecto.

Además, el archivo `requirements.txt` incluye las principales librerías necesarias para ejecutar los notebooks.

## Notebooks

Los notebooks deben revisarse siguiendo aproximadamente este orden:

| Notebook | Descripción |
|---|---|
| `00_prueba_entorno.ipynb` | Comprobación inicial del entorno de trabajo. |
| `01_descarga_datos.ipynb` | Descarga inicial de los datos del EUR/USD. |
| `02_limpieza_exploracion.ipynb` | Limpieza y exploración inicial de los datos. |
| `03_creacion_variables.ipynb` | Creación de las variables predictoras utilizadas inicialmente. |
| `04_division_temporal.ipynb` | División temporal de los datos para entrenamiento y validación. |
| `05_entrenamiento_modelos.ipynb` | Primer entrenamiento de modelos utilizando datos de Yahoo Finance. |
| `05b_revision_posicion_cierre.ipynb` | Comprobación de la variable `Posicion_cierre` utilizando Alpha Vantage. |
| `06_preparacion_alpha_vantage.ipynb` | Preparación definitiva de los datos de Alpha Vantage y creación de las variables. |
| `07_entrenamiento_modelos_alpha_vantage.ipynb` | Modelos base y regresión logística con los datos definitivos. |
| `08_random_forest_alpha_vantage.ipynb` | Entrenamiento y ajuste del modelo Random Forest. |
| `09_xgboost_alpha_vantage.ipynb` | Entrenamiento y ajuste del modelo XGBoost. |
| `10_Resumen.ipynb` | Resumen general del desarrollo realizado. |
| `11_evaluacion_final_alpha_vantage.ipynb` | Evaluación final sobre el periodo reservado desde 2025. |

## Datos

Los datos se encuentran separados en dos carpetas:

### `data/raw`

Contiene los datos originales descargados de las fuentes utilizadas:

- Yahoo Finance.
- Alpha Vantage.

### `data/processed`

Contiene los conjuntos de datos obtenidos después de realizar la limpieza, creación de variables y división temporal.

Se conservaron los archivos correspondientes a Yahoo Finance para documentar el análisis inicial y la comprobación posterior realizada con Alpha Vantage.

## Variables utilizadas

Entre las variables calculadas se encuentran:

- Retornos diarios y retardados.
- Rango diario.
- Cuerpo de la vela.
- Posición del cierre.
- Distancias respecto a medias móviles.
- Volatilidad.
- RSI.
- MACD.

## Modelos evaluados

Durante el proyecto se compararon:

- Modelos base.
- Regresión logística.
- Random Forest.
- XGBoost.

El mejor modelo durante la etapa de desarrollo fue una regresión logística regularizada. Sin embargo, en la evaluación final sobre datos reservados desde 2025 obtuvo aproximadamente:

- Accuracy: 48,40 %.
- Balanced accuracy: 48,59 %.
- ROC-AUC: 49,13 %.

Estos resultados mostraron que la pequeña capacidad predictiva observada durante el desarrollo no se mantuvo de forma estable en el periodo final.

## Requisitos

Las dependencias principales del proyecto se encuentran en:

`requirements.txt`

Para instalarlas puede utilizarse:

```bash
pip install -r requirements.txt