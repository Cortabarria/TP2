# TP2 - Cortabarria Anguera, Felipe
Dataset: [Microsoft Malware Prediction](https://www.kaggle.com/competitions/microsoft-malware-prediction)

Tarea a realizar: Obtener un modelo que pueda predecir que equipo posee malware. 

En el dataset de entrenamiento, este valor se encuentra en la columna `HasDetections`.

El dataset de entrenamiento [`train.csv`](https://www.kaggle.com/competitions/microsoft-malware-prediction/data?select=test.csv) contiene 83 columnas y 8.921.483 filas
* Columnas con valor 'Entero': 17
* Columnas con valor 'Flotante': 36
* Columnas con valor 'String': 30


## KDD

Las tareas de KDD sobre el dataset `train.csv`.
* En la etapa de limpieza, no se tuvo que realizar ninguna accion ya que no se poseían errores / datos con ruido
* En la etapa de Seleccion, se realizaron 2 enfoques diferentes:
  * Eliminación de las columnas con un alto índice de valores nulos (Enfoque 1)
  * Conservación de todas las columnas (Enfoque 2).

* En la etapa de transformacion, todos los datos fueron convertidos a formatos numéricos (enteros o flotantes). Esta conversión se realizó con el fin de facilitar su utilización por los modelos de Aprendizaje Automático seleccionados, con el objetivo de obtener los mejores resultados posibles.

## Enfoques sobre la Mineria de Datos
### <ins>Enfoque 1 'Eliminar columnas con un alto índice de valores nulos'</ins>
Este enfoque se realizo con [scikit-learn](https://scikit-learn.org/stable/user_guide.html)

Los archivos relacionados a este enfoque se encuentran en la carpeta [`enfoque-1`](enfoque-1)
* Numero de filas: 8.921.483
* Numero de filas: 63

Las columnas que se eliminaron debido a su indice de valores nulos:
 * PuaMode
 * Census_ProcessorClass
 * DefaultBrowsersIdentifier
 * Census_IsFlightingInternal
 * Census_InternalBatteryType
 * Census_ThresholdOptIn
 * Census_IsWIMBootEnabled
 * SmartScreen
 * OrganizationIdentifier
 * SMode
 * CityIdentifier
 * Wdft_IsGamer
 * Wdft_RegionIdentifier
 * Census_InternalBatteryNumberOfCharges
 * Census_FirmwareManufacturerIdentifier
 * Census_IsFlightsDisabled
 * Census_FirmwareVersionIdentifier
 * Census_OEMModelIdentifier
 * Census_OEMNameIdentifier
 * Firewall
   
Los valores nulos que quedaron en las otras columnas se decidio darle el valor `0`.

A continuacion se muestra la correlatividad de las columnas del enfoque-1 con `HasDetections`
![imagen](https://github.com/Cortabarria/TP2/assets/131315165/53f1f72a-7a9b-44d0-b116-39f08e9e9cff)


Los resultados obtenidos de los siguientes modelos basados en este enfoque fueron:
```
1. Random Forest - max_depth=25 - Exactitud: 63.29%
2. Gradient Boosting - n_estimators=15, max_depth=5 - Exactitud: 60.44%
3. Decision Tree - max_depth=25 - Exactitud: 60.19%
4. Regresion Logica - Exactitud: 49.95%
```

### <ins>Enfoque 2 'Conservar todo'</ins>
Este enfoque se realizo con [XGBoost](https://xgboost.readthedocs.io/en/stable/get_started.html)

Los archivos relacionados a este enfoque se encuentran en la carpeta [`enfoque-2`](enfoque-2)
* Numero de filas: 8.921.483
* Numero de filas: 83

No se elimino ninguna columna y los valores nulos quedaron como NaN.

A continuacion se muestra la correlatividad de las columnas del enfoque-2 con `HasDetections`
![imagen](https://github.com/Cortabarria/TP2/assets/131315165/fbeda6ea-f252-473e-ad05-2c1e5fcdac99)


Los resultados obtenidos de los siguientes modelos basados en este enfoque fueron:
```
1. XGBoost - Exactitud: 65.78%
2. XGBoost Random Forest - Exactitud: 62.16%
3. XGBoost Regressor - Error Cuadrático Medio: 0.21233367732551084
```
## Conclusion
La comparación de resultados revela que el Enfoque 2 ha generado un rendimiento superior al emplear la herramienta de XGBoost. Contrario a la intuición inicial que sugería que la eliminación de columnas y valores nulos, abordada en el Enfoque 1, conduciría a un modelo más precario.
