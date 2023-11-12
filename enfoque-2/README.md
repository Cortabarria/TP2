### <ins>Enfoque 2 'Conservar todo'</ins>
Este enfoque se realizo con [XGBoost](https://xgboost.readthedocs.io/en/stable/get_started.html)

Los archivos relacionados a este enfoque se encuentran en la carpeta [`enfoque-2`](enfoque-2)
* Numero de filas: 8.921.483
* Numero de filas: 83

No se elimino ninguna columna y los valores nulos quedaron como NaN.

A continuacion se muestra la correlatividad de las columnas del enfoque-2 con `HasDetections`
![imagen](https://github.com/Cortabarria/TP2/assets/131315165/8f546288-3dbe-497e-b235-b174385e6761)


Los resultados obtenidos de los siguientes modelos basados en este enfoque fueron:
```
1. XGBoost - Exactitud: 65.78%
2. XGBoost Random Forest - Exactitud: 62.16%
3. XGBoost Regressor - Error Cuadrático Medio: 0.21233367732551084
```
