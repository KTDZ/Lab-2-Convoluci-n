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

## Requisitos
- **Phyton** Instalado en tu sistema.
- **Spyder** (Puedes instalarlo como parte de [Anaconda](https://www.anaconda.com/)).
- **Bibliotecas de Python:** `numpy`,`matplotlib`,`wfdb`.
- **Una señal fisiológica en formato `.dat` y `.hea` (Se puede descargala de [Physionet](https://physionet.org/))**.

## Convolución
Se tiene el sistema h[n]={5,6,0,0,6,7,7} y la señal x[n]={1,0,7,3,1,5,2,5,0,6}.Para calcular la convolución (x*h) a mano se hace una tabla, donde en la fila va a ir todas las muestras del sistema y en la columna las muestras de la señal. Luego, se multiplica fila por columna, llenando asi toda la tabla y por último se realiza una suma en diagonal (guiada por el lápiz rojo) para asi obtener una nueva señal y[n] con sus respectivas muestras. A continuación se muestra un enlace para acceder a una imagen y tener una mejor comprensión del procedimiento:

[Convolución a mano](Convolución.pdf)

Para gráficar la señal resultante, se hace uso de un plano cartesiano donde en el eje X va la posición del vector, y en el eje Y va cada dato o muestra que esta en esa posición. por ejemplo tengo la señal resultante y[n]={4,5,7,2,1}, en ese caso la primera posición del vector es 0 y en ese lugar se encuentra la muestra 4, es decir en el eje X iria 0 y en el eje Y iria 4, y asi sucesivamente. A continuación se muestra un enlace para acceder a una imagen y tener una mejor comprensión de la gráfica:

[Gráfica a mano](Gráfica_convolución.pdf)

En el Python, en el código se usa la libreria numpy para operaciones y matplotlib.pyplot para gráficar la señal resultante. Para hacer la convolución, se crea los respectivos vectores haciendo uso de un arreglo (`array`) para almacenar multiples elementos que son del mismo tipo en una sola variable y asi facilitar las operaciones entre los vectores. Se usa la función `convolve`que permite realizar la operación de convolución.


![Código-convolución](https://github.com/user-attachments/assets/70693ded-dee6-486d-be25-582cf1787787)
### *Figura 1: Lineas de código para realizar la convolución.*

![Código_gráfica](https://github.com/user-attachments/assets/158c42b2-0e79-4d8e-afc7-dde772455b9e)
### *Figura 2: Lineas de código para realizar la gráfica.*

![Captura de pantalla 2025-02-12 231524](https://github.com/user-attachments/assets/3bdabc9f-0510-42ab-83d4-763fe5c8c752)
### *Figura 3: Gráfica en Python de la convolución.*









