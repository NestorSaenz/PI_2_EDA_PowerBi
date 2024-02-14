![Pandas](https://img.shields.io/badge/-Pandas-333333?style=flat&logo=pandas)
![Numpy](https://img.shields.io/badge/-Numpy-333333?style=flat&logo=numpy)
![Matplotlib](https://img.shields.io/badge/-Matplotlib-333333?style=flat&logo=matplotlib)
![Power BI](https://img.shields.io/badge/-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=white)

# PI_2_DATA_ANALYST_POWER_BI

Este proyecto simula el rol de un ***Data Analyst*** para el  `Observatorio de Movilidad y Seguridad Vial` (OMSV) centro de estudios que se encuentra bajo la órbita de la ***Secretaría de Transporte*** del Gobierno de la Ciudad Autónoma de Buenos Aires, Para ello, se cuenta con un dataset sobre homicidios en siniestros viales durante el period 2016-2021 acaecidos en la Ciudad de Buenos Aires durante el periodo 2016-2021. se puede descargar de la siguiente página Web [Buenos Aires Data](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

## Objetivo

El objetivo es hacer un análisis de los datos disponibles incluyendo KPI's, con el fin de generar información que le permita a las autoridades tomar medidas de prevencion y disminuir la tasa de accidentes fatales quer actualemte es de `11 personas por día`.

## Contexto

Actualemnte la muerte por accidentes de transito es la primera causa de muerte violenta en el pais, es mas probable morir de un siniestro vial que por un acto delictivo, de ahi la importancia de generar medidas de prevencion

## Elaboracion del proyecto

La data se extrae de dos archivos formato xlsx: 

*  ** HECHOS.xlsx * información relacionada con la data fisica del accidente. Por ejemplo: la fecha, lugar del hecho, tipo de vehiculos involucrados, latitud y longitud, acusado del hecho entre otras.

*  ** VICTIMAS.xlsx * Informacion relacionada con la victima. Por ejemplo: sexo, edad, rol de la victima y fecha de fallecimiento.

## ETL (extraccion, transformacion y carga)

Se extrae la informacion con pandas y se empieza la transformacion, en este notebook se hace un merged con los dos datasets previamente cargados y se comienzan las transformaciones: normalizacion de columnas, verificacion de los tipos de datos, algunos datos por ejemplo de franja horaria donde no hay datos se sustituyen por la moda del conjunto de datos, para visualizar el ETL hacer click en [ETL](ETL.ipynb)

## EDA (Analisis exploratorio de los datos)

La exploracion de los datos comienza con un análisis descriptivo, donde se visualiza metricas estadisticas como, la media, desviacion estandar y distribucion por percentiles de los datos, el análisis se basa en tres pilares:

### 1. Análisis por victima

En este paso se exploran caracteristicas de las victimas que pueden influir o estan relacionadas con el riesgo de tener un accidente fatal como la edad y  genero, graficamente se visualiza que el género masculino tiene un 76% de probabilidad de morir en carretera con un rango etario de [25-41] años.


### 2. Análisis temporal

Aqui se pretende evaluar como se distribuye la cantidad de víctimas por: mes, franja horaria y dia de la semana, mediante graficas se concluyó que los periodos de tiempo mas criticos son: Diciembre, 5 AM y domingo de madrugada.

### 3. Análisis por ubicacion

Descifrar los lugares donde hay mas incidencias permite personalizar estrategias para prevenir muertes en carretera, despues del analisis se evidencia que los sitios criticos son: las avenidas donde ocurren el 62% de los accidentes, donde la numero uno es la avenida General Paz, y por comuna la [1, 4, 9, 8].

Todas las graficas se pueden visualizar en [EDA](EDA.ipynb) 

Una vez limpios los datos se exportan a la herramienta de visualizacion ![Power BI](https://img.shields.io/badge/-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=white)
donde a traves de graficos, indicadores, KPI's e puede hacer un `storytelling` para la audiencia involucrada en gestionar la prevencion de muertes por accidentes de transito, y tener la informacion para poder tomar desiciones.

## KPI

En este apartado se consideran 3 KPI's los cuales fueron desarrollados en su totalidad desde Power BI

1. Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.
 
Se define la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

Para desarrollarlo se pretende evaluar el segundo semestre  con respecto al primero desde el año 2016 hadsta el año 2021, se define  los calculos matematicos se desarrollan por medio de funciones DAX desde Power BI, las funciones empleadas se pueden visualizar en: [KPI_1](imagenes/kpi_1.png)


2. Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Se define a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100
Las funciones empleadas se pueden visualizar en: [KPI_2](imagenes/kpi_2.png)

3. Reducir en un 5% la cantidad de accidentes que ocurren en las avenidas

Se define a la cantidad de accidentes mortales en avenidas como el número absoluto de accidentes fatales que ocurrieron en avenidas en un determinado periodo de tiempo, su formula para medir la evolución es: (Número de accidentes mortales con víctimas en avenidas en el año anterior - Número de accidentes mortales con víctimas en avenidas en el año actual) / (Número de accidentes mortales con víctimas en avenidas en el año anterior) * 100
Las funciones empleadas se pueden visualizar en:  [KPI_3](imagenes/kpi_3.png)

Despues del revisar los hallazgos se hacen las siguientes recomendaciones: ![Imagen](imagenes/atencion.jpg)



