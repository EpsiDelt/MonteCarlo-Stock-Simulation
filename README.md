# Monte Carlo Stock Price Simulation using Geometric Brownian Motion

## Descripción

Este proyecto implementa un modelo Log-Normal basado en Movimiento Browniano Geométrico (GBM) para simular el comportamiento futuro de los precios de las acciones de NVDA, AMD, INTC e IBM.

Utilizando datos históricos del periodo 2016-2020, se generaron 2500 escenarios simulados para estimar la probabilidad de que cada activo superara un umbral del 110% durante el año 2021.

---

## Objetivo

Desarrollar un modelo de simulación Monte Carlo para proyectar precios futuros de activos financieros y evaluar la probabilidad de alcanzar un objetivo de rentabilidad previamente definido.

---

## Tecnologías utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* yfinance

---

## Metodología

### 1. Descarga de datos históricos

Se descargaron precios ajustados al cierre de las acciones NVDA, AMD, INTC e IBM desde Yahoo Finance utilizando la librería `yfinance`.

### 2. Cálculo de rendimientos logarítmicos

A partir de los precios históricos se calcularon los rendimientos logarítmicos diarios. Se utilizó este enfoque bajo el supuesto de que los rendimientos siguen una distribución aproximadamente normal, lo que conduce a una distribución Log-Normal para los precios.

### 3. Estimación de parámetros

Se calcularon la media (μ) y la desviación estándar (σ) de los rendimientos históricos para cada activo.

### 4. Simulación Monte Carlo

Mediante un modelo de Movimiento Browniano Geométrico se generaron 2500 escenarios de rendimientos futuros para cada acción.

### 5. Proyección de precios

Los rendimientos simulados fueron transformados en trayectorias de precios utilizando el último precio histórico disponible como punto de partida.

### 6. Probabilidad de superar un umbral

Se estableció un precio objetivo equivalente al 110% del último precio histórico de cada activo y se calculó la probabilidad de que los precios simulados superaran dicho umbral.

### 7. Validación

Los resultados simulados fueron comparados con los precios reales observados durante el año 2021.

---

## Resultados

El proyecto genera:

* Simulación de 2500 escenarios para cada activo.
* Caminatas aleatorias de precios simulados.
* Probabilidades de superar un umbral del 110%.
* Comparación entre precios simulados y precios reales observados en 2021.

---

## Habilidades aplicadas

* Obtención de datos financieros
* Manipulación y transformación de datos
* Estadística descriptiva
* Simulación Monte Carlo
* Modelado estocástico
* Visualización de datos
* Automatización mediante funciones y ciclos `for`

---

## Estructura del proyecto

```text
MonteCarlo-Stock-Simulation/
│
├── README.md
├── Modelo_Log_Normal.ipynb
│
└── images/
    ├── Probabilidades.png
    ├── Real_vs_Umbral.png
    └── Simulaciones.png
```

---

## Limitaciones

El modelo asume que los rendimientos siguen una distribución normal y que la volatilidad permanece constante durante el horizonte de simulación. Eventos extremos de mercado, cambios estructurales o distribuciones con colas pesadas pueden generar desviaciones respecto a los resultados simulados.
