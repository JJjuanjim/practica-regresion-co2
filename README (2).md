# Regresión Lineal Simple — Consumo de Combustible y Emisiones de CO2

Práctica Guiada del **Módulo III**. Se implementa una **regresión lineal simple**
con `scikit-learn` para predecir las emisiones de CO2 de vehículos ligeros a
partir del tamaño del motor (`ENGINESIZE`), usando el dataset
`FuelConsumptionCo2.csv`.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `Regresion_Lineal_Simple_CO2.ipynb` | Notebook con todo el desarrollo y las salidas ejecutadas |
| `FuelConsumptionCo2.csv` | Conjunto de datos utilizado |
| `README.md` | Este archivo |

## Flujo de trabajo

1. Carga y exploración descriptiva de los datos (`describe`, histogramas).
2. Visualización de la relación de `ENGINESIZE`, `CYLINDERS` y
   `FUELCONSUMPTION_COMB` con `CO2EMISSIONS`.
3. División en conjuntos de **entrenamiento (~80%)** y **prueba (~20%)**.
4. Entrenamiento del modelo de regresión lineal simple con `scikit-learn`.
5. Evaluación con MAE, MSE y R².
6. Predicción de valores desconocidos.

## Resultados obtenidos

**Polinomio (ecuación) generado por el modelo:**

```
CO2EMISSIONS = 39.53 * ENGINESIZE + 124.18
```

**Métricas de evaluación (conjunto de prueba):**

| Métrica | Valor |
|---|---|
| Error medio absoluto (MAE) | 22.58 g/km |
| Suma residual de cuadrados (MSE) | 851.05 |
| R² (R-cuadrado) | 0.74 |

> Nota: los valores pueden variar ligeramente según la división aleatoria
> train/test. En este notebook se fijó `np.random.seed(42)` para que los
> resultados sean reproducibles.

## Análisis de la precisión del modelo

Existe una relación **lineal positiva fuerte** entre el tamaño del motor y las
emisiones de CO2. Un R² de **0.74** indica que aproximadamente el 74% de la
variabilidad en las emisiones queda explicada únicamente por el tamaño del
motor, lo cual confirma que `ENGINESIZE` es un buen predictor. El MAE de
**22.58 g/km** representa el error promedio de las predicciones.

El modelo simple captura bien la tendencia general; podría mejorarse usando
regresión lineal **múltiple** (combinando `ENGINESIZE`, `CYLINDERS` y
`FUELCONSUMPTION_COMB`) o regresión **polinómica**.

## Cómo ejecutar

```bash
pip install pandas numpy matplotlib scikit-learn
jupyter notebook Regresion_Lineal_Simple_CO2.ipynb
```
