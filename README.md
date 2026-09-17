# CC3092 — Deep Learning — Proyecto 2

Detección de lavado de dinero sobre secuencias transaccionales con una LSTM
encoder–decoder (etapa A, no supervisada) y un clasificador con atención
inicializado por transferencia (etapa B), comparado contra una línea base
supervisada entrenada desde cero.

## Autores

- tismajo — gir23559@uvg.edu.gt
- DufreyM — mej23648@uvg.edu.gt

## Datasets requeridos

Los datasets **no están versionados en este repositorio** por su tamaño. Se
asume que ya se cuenta con ellos; se descargan de Kaggle y se colocan en la
raíz del proyecto con la estructura indicada abajo.

### PaySim

https://www.kaggle.com/datasets/ealaxi/paysim1

```
paysim/
└── PS_20174392719_1491204439457_log.csv
```

### IBM AML (IBM Transactions for Anti Money Laundering)

https://www.kaggle.com/datasets/ealtman2019/ibm-transactions-for-anti-money-laundering-aml

```
ibm-transactions/
├── HI-Small_Trans.csv
├── HI-Small_Patterns.txt
├── LI-Small_Trans.csv
└── ...
```

El proyecto usa **HI-Small** como dataset principal. La justificación de esa
decisión, y el descarte de PaySim, están en `analisis_dataset.ipynb`.

## Instalación

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

## Ejecución

1. `analisis_dataset.ipynb` — exploración inicial y selección del dataset.
2. `proyecto2.ipynb` — pipeline completo, de la carga de datos a la
   exportación del MVP. Se ejecuta de principio a fin en orden.

Las rutas se configuran en el Bloque 0 de `proyecto2.ipynb` (`CFG.DATA_DIR`).

## Artefactos

`proyecto2.ipynb` escribe en `artifacts_aml/` los pesos entrenados, el
preprocesador, los umbrales y las predicciones de prueba. Esa carpeta tampoco
se versiona: se regenera ejecutando el notebook.

## Estructura

```
.
├── analisis_dataset.ipynb   # EDA y selección de dataset
├── proyecto2.ipynb          # pipeline completo (Bloques 0–15)
├── requirements.txt
├── paysim/                  # descargar de Kaggle (ignorado)
├── ibm-transactions/        # descargar de Kaggle (ignorado)
└── artifacts_aml/           # generado por el notebook (ignorado)
```
