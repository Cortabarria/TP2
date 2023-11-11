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
### Enfoque 1 'Eliminar nulos'
Los archivos relacionados a este enfoque se encuentran en la carpeta [`enfoque-1`](enfoque-1)

### Enfoque 2 'Conservar todo'
