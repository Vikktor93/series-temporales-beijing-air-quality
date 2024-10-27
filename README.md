# Proyecto N°3: Análisis de la Contaminación del Aire en Beijing con Series Temporales

<p align="left">
   <img src="https://img.shields.io/badge/Status-En%20Desarrollo-green?style=plastic">
   <img src="https://img.shields.io/badge/Python-3776AB?style=plastic&logo=python&logoColor=white"/>
   <img src="https://img.shields.io/badge/Jupyter-%23e58f1a.svg?style=plastic&logo=Jupyter&logoColor=white"/>

<img src="./assets/banner-series.png"/>

Este proyecto tiene como objetivo realizar un análisis exhaustivo de la calidad del aire en Beijing mediante series temporales, utilizando el dataset [Beijing Multi-Site Air-Quality Dataset](https://www.kaggle.com/datasets/sid321axn/beijing-multisite-airquality-data-set) de Kaggle. Se aplicarán técnicas de Análisis Exploratorio de Datos (EDA), Limpieza y Transformación de Datos, y un modelo de Autoregresión (AR) para analizar patrones y tendencias en la contaminación del aire.

## Descripción del Dataset

El dataset incluye mediciones de varios contaminantes atmosféricos y variables meteorológicas en múltiples estaciones de Beijing:

- **PM2.5:** Concentración de partículas finas ≤ 2.5 micras.
- **PM10:** Concentración de partículas ≤ 10 micras.
- **SO2:** Dióxido de azufre.
- **NO2:** Dióxido de nitrógeno.
- **CO:** Monóxido de carbono.
- **O3:** Ozono troposférico.
- **TEMP:** Temperatura en grados Celsius.
- **PRES:** Presión atmosférica en hectopascales.
- **DEWP:** Punto de rocío.
- **RAIN:** Precipitación.
- **WSPM:** Velocidad del viento.

El análisis busca entender los factores que influyen en la calidad del aire y detectar patrones temporales en los niveles de contaminación.

## Estructura del Proyecto

La estructura del proyecto es la siguiente:
```
Proyecto-Series-Temporales/
├── assets/                           # Carpeta que contiene imágenes o activos para el README
│   └── banner-series.png             # Imagen del banner utilizado en el README.md
├── data/                             # Carpeta que contiene los datasets originales y limpios
│   ├── PRSA_Data_Aotizhongxin.csv    # Dataset original
│   └── dataset_clean.csv             # Dataset limpio tras la limpieza de datos
├── notebooks/                        # Notebooks de Jupyter con el análisis y transformación de datos
│   ├── 001_Analisis_Exploratorio.ipynb   # Análisis exploratorio de los datos
│   ├── 002_Limpieza_Formato_ING.ipynb    # Limpieza, formato e ingeniería de datos
│   ├── 003_Estacionariedad_ACF_PACF.ipynb# Pruebas de estacionariedad, ACF y PACF
│   └── 004_Modelo_AR.ipynb               # Aplicación del modelo AR y conclusiones
├── README.md                         # Archivo de documentación del proyecto
```

### 1. **Análisis Exploratorio (`001_Analisis_Exploratorio.ipynb`)**
En este notebook se realiza una exploración inicial del dataset:
- Revisión del contenido y estructura del dataset.
- Visualización de las distribuciones de las variables numéricas.
- Visualización de la variación temporal de los contaminantes principales (PM2.5, PM10, NO2).
- Cálculo de la correlación entre variables para identificar posibles relaciones entre contaminantes y condiciones meteorológicas.

### 2. **Limpieza de Datos (`002_Limpieza_de_Datos_ING.ipynb`)**
En esta etapa se prepara el dataset para el análisis de series temporales:
- Eliminación de valores nulos en las variables principales.
- Conversión de columnas temporales (year, month, day, hour) en un índice datetime.
- Detección y manejo de outliers en concentraciones de contaminantes.
- Creación de nuevas columnas como mes, día de la semana, estación para enriquecer el análisis estacional.

### 3. **Modelo de Regresión Lineal (`003_Estacionariedad_ACF_PACF.ipynb`)**
En este notebook se evalúa si las series de contaminantes son estacionarias, un paso fundamental para aplicar modelos AR:
- Pruebas de Estacionariedad: Se aplican pruebas de Dickey-Fuller para verificar si la serie es estacionaria.
- Transformaciones: En caso de no ser estacionarias, se aplican diferenciaciones.
- Autocorrelación y Autocorrelación Parcial: Se visualizan las funciones de autocorrelación (ACF) y autocorrelación parcial (PACF) para entender los lags relevantes.

### 4. **Modelo Autoregresivo (`004_Modelo_AR.ipynb`)**
Este notebook se enfoca en el modelo autoregresivo para el análisis de series temporales de la concentración de PM2.5.
- Objetivos:
    - Aplicar el modelo AR(1) y, si es necesario, modelos de orden superior (AR(p)).
    - Evaluar el ajuste del modelo y su precisión en la predicción.
    - Comparar los resultados del modelo y discutir las conclusiones.
- Contenido:
    - Ajuste del modelo AR(1) para la serie de PM2.5 y análisis de los coeficientes.
    - Evaluación del modelo utilizando métricas de precisión como R² ajustado y Error Promedio (EP).
    - Discusión sobre la aplicabilidad del modelo y posibles mejoras para análisis futuros.

## Requisitos Previos

Para ejecutar los notebooks y replicar el análisis, necesitas instalar las siguientes dependencias:

`pip install numpy pandas matplotlib seaborn statsmodels`
