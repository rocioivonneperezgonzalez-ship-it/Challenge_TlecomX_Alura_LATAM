# Telecom X (LATAM) — Análisis de Evasión de Clientes (Churn)

Este repositorio contiene un análisis exploratorio de datos (EDA) para comprender la **evasión de clientes (Churn)** en Telecom X (LATAM), identificar **patrones de comportamiento** y detectar variables asociadas a una mayor probabilidad de cancelación.

---

## 1) Propósito del análisis

El objetivo principal del proyecto es:

- Analizar la **distribución del Churn** (clientes que se van vs. se quedan).
- Explorar cómo se relaciona el Churn con variables **categóricas** (p. ej., género, tipo de contrato, tipo de internet, método de pago).
- Evaluar variables **numéricas** (p. ej., antigüedad/tenure, valor mensual, total cobrado, cuentas diarias) para detectar diferencias entre clientes con y sin churn.
- Obtener **insights accionables** que permitan orientar estrategias de **retención**.

> El dataset se carga desde un archivo JSON público y se transforma a un DataFrame plano con `pd.json_normalize()`.

---

## 2) Estructura del proyecto y organización de archivos

Estructura recomendada del repositorio:

```bash
.
├── TelecomX_LATAM.ipynb         # Notebook principal con el EDA completo
├── README.md                    # Documentación del proyecto (este archivo)
└── (opcional)
    ├── outputs/                 # Gráficas exportadas (png/html) para reportes
    └── data/                    # Datos descargados localmente (si se decide guardar)

## 3) Ejemplos de gráficas e insights obtenidos

A lo largo del notebook se generan visualizaciones para entender el comportamiento del churn. Ejemplos:

Distribución general del churn

Gráfica: Distribución de Churn (conteo + porcentaje).

Insight: el churn representa una fracción relevante de la base de clientes (aprox. 1 de cada 4).

Variables categóricas

Género

Gráfica: Churn por género (barras agrupadas).

Insight: no se observan diferencias fuertes entre géneros (variable menos determinante en este dataset).

Tipo de contrato

Gráficas: Proporción por tipo de contrato (dona) + Churn por tipo de contrato (barras).

Insight: el contrato mensual concentra más cancelaciones; contratos de mayor duración suelen mostrar mayor estabilidad.

Tipo de internet

Gráficas: Proporción por tipo de internet (dona) + Churn por tipo de internet (barras).

Insight: la fibra óptica concentra gran parte del churn, consistente con ser el grupo más numeroso.

Método de pago

Gráficas: Proporción por método de pago (dona) + Churn por método de pago (barras).

Insight: el cheque electrónico presenta un churn particularmente alto; pagos automáticos se asocian a mayor retención.

Variables numéricas

Antigüedad del contrato (tenure / tiempo_contrato)

Gráfica: Churn por antigüedad (barras / bins).

Insight: el churn se concentra en los primeros meses; clientes con más antigüedad tienden a permanecer.

Valor mensual

Gráfica recomendada: Boxplot / Violin por churn.

Insight: diferencias en mediana y dispersión sugieren relación entre cargo mensual y churn (además de outliers que conviene analizar por segmentos).

Total cobrado

Nota analítica: suele estar fuertemente relacionado con la antigüedad (variable acumulada), por lo que se interpreta con cautela y en conjunto con tiempo_contrato.
