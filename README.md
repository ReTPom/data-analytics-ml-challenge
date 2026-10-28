# data-analytics-ml-challenge

Data Analytics ML Challenge 2026-2 · Universidad Central · Ingeniería de Sistemas
Profesor: Elias Buitrago Bolivar

**Estudiante ID:** 01 (semilla 1001)

## Caso

Predicción de entregas tardías en comercio electrónico con el conjunto público
[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
Cada observación es un pedido y la variable objetivo `is_late` vale 1 cuando la
entrega real ocurre después de la fecha estimada.

## Laboratorio 1 (Semana 12): modelos supervisados y métricas

- Muestra individual de 35.000 pedidos: 24.500 entrenamiento, 5.250 validación y 5.250 prueba (reservada para la semana 16).
- 28 variables predictoras (24 numéricas y 4 categóricas), sin fuga de información.
- Modelo de referencia (`DummyClassifier`) y regresión logística con `class_weight='balanced'`.
- Métricas en validación, errores por mes y estado, costo empresarial (R$ 8 por falso positivo, R$ 35 por falso negativo) y ejemplo guiado de regresión (Ridge).

### Resultados en validación (regresión logística, `balanced`)

| Métrica | Valor |
|---|---|
| Accuracy | 0.669 |
| Precision | 0.121 |
| Recall | 0.623 |
| F1 | 0.203 |
| ROC-AUC | 0.707 |
| Average Precision | 0.160 |
| Costo de errores | R$ 17.538 |
| MAE regresión (Ridge) | 5.07 días |

La interpretación de negocio y la propuesta de mejora para la semana 13 están en la sección 6 del cuaderno.

## Estructura del repositorio

```
notebooks/
  S12_ML_Challenge.ipynb        # cuaderno ejecutado con actividades e interpretación
reports/
  S12_resultados_ID_01.json     # reporte generado por el cuaderno
README.md
```

## Cómo reproducir

1. Abrir `notebooks/S12_ML_Challenge.ipynb` en Google Colab o en Jupyter.
2. Verificar que `ID_ESTUDIANTE = 1`.
3. Reiniciar y ejecutar todas las celdas en orden. Los CSV de Olist se leen directamente desde una copia pública con revisión fija (`fa0cc6d1aff713d3c8b9a1e633b56889881848bf`); no se incluyen en el repositorio.
4. El cuaderno escribe el reporte en `reports/S12_resultados_ID_01.json`.

Dependencias: Python 3, pandas, numpy y scikit-learn.

## Datos

Los datos originales no se publican en este repositorio. La misma muestra, variables y particiones se mantienen entre las semanas 12 a 16 para poder comparar modelos.
