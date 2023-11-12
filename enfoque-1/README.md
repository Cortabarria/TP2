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
![imagen](https://github.com/Cortabarria/TP2/assets/131315165/8f546288-3dbe-497e-b235-b174385e6761)


Los resultados obtenidos de los siguientes modelos basados en este enfoque fueron:
```
1. Random Forest - max_depth=25 - Exactitud: 63.29%
2. Gradient Boosting - n_estimators=15, max_depth=5 - Exactitud: 60.44%
3. Decision Tree - max_depth=25 - Exactitud: 60.19%
4. Regresion Logica - Exactitud: 49.95%
```
