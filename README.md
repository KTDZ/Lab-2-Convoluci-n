# Lab-2-Convolución y Correlación
Este Laboratorio tiene como objetivo el reconocimiento de la convolución entre señal y sistema,la correlación como operación entre señales y hacer uso de la transformada de Fourier para analizar la señal en el dominio de la frecuencia. El código esta implementado en Python y utiliza bibliotecas como `numpy`, `matplotlib` y `wfdb`.
## Tabla de Contenido
1.[Introducción](#introducción)
2.[Requisitos](#requisitos)
3.[Convolución](#convolución)
4.[Correlación](#correlación)
5.[Transformada de Fourier](#transformada-de-fourier)
6.[Conclusión](#conclusión)

## Introducción
La **correlación** es una medidad para saber la similitud que hay entre dos señales que son dependientes del espacio o del tiempo y la **convolución** es una operación que combina dos señales para obtener una tercera señal. Ambas serán analizadas en este laboratorio y se empleará una señal EEG para usar como herramienta la transformada de Fourier, y analizar su dominio en la frecuencia. En este laboratorio se realiza lo siguiente:

1. **Convolución (item a)** tanto a mano como en python y con representación gráfica y secuencial.
2. **Correlación (item b)** de dos señales en python con representación gráfica y secuencial.
3. **Transformada de Fourier (item c)** de una señal EEG descargada desde la base de datos [PhysioNet`](https://physionet.org/) y haciendo análisis estadisticos descriptivos en función de la frecuencia (frecuencia media, frecuencia mediana, desviación estándar, histograma de frecuencias).
