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

En el Python, en el código se usa la libreria numpy para operaciones y matplotlib.pyplot para gráficar la señal resultante. Para hacer la convolución, se crea los respectivos vectores haciendo uso de un arreglo `array`para almacenar multiples elementos que son del mismo tipo en una sola variable y asi facilitar las operaciones entre los vectores. Se usa la función `convolve`que permite realizar la operación de convolución.

## Correlación
La correlacion nos dice que tan parecidas son dos señales cuando una se desliza sobre la otra, en la grafica de correlacion entre x1[n] y x2[n] muestra las señales originales
En la muestra un comportamiento periodicocon una diferencia de fa

![Código-convolución](https://github.com/user-attachments/assets/70693ded-dee6-486d-be25-582cf1787787)
### *Figura 1: Lineas de código para realizar la convolución.*

![Código_gráfica](https://github.com/user-attachments/assets/158c42b2-0e79-4d8e-afc7-dde772455b9e)
### *Figura 2: Lineas de código para realizar la gráfica.*

![Captura de pantalla 2025-02-12 231524](https://github.com/user-attachments/assets/3bdabc9f-0510-42ab-83d4-763fe5c8c752)
### *Figura 3: Gráfica en Python de la convolución.*

## Descarga y Análisis de la señal EEG 
1. **Procedimiento para descarga de la señal EEG**
   Para este laboratorio se descargo una señal de physionet siguendo estos pasos:
   ##
- Acceder al sitio web de Physionet [Physionet](https://physionet.org/))
- Seleccionar la base de datos correspondiente a EEG
- Elegir dos archivos con el mismo nombre y que uno sea .hea y el otro .dat
- Descargar los archivos en la computadora
- Guardar los archivos descargados en la misma carpeta donde se guardo el código
- Verificar o Instalar todas las librerias necesarias
- Usar la función wfdb.rdrecord() para leer el archivo
 ##
  ![image](https://github.com/user-attachments/assets/ebde78fe-81fd-4ac1-a340-e7a8a2a5bfcb)
  ### *Figura 4: Lectura de la señal EEG.*

## Caracterización de la señal

Una vez que ya cargamos la señal EEG, se calcularon los siguientes estadisticos descriptivos y se le aplicaron SNR a la señal orginal: 
 1. **Media** El valor promedio de la señal
 2. **Desviación estandar** Variabilidad de la señal con respecto a su media
 3. **Coeficiente de variación** Media relativa de la variabilidad de la señal donde se relaciona la desviación estandar y la media
 4. **Frecuencia de muestreo** Numero de muestras por segundo
 5. **SNR de artefacto**
 6. **SNR de impulso**
 7. **SNR gaussioano**
##
![image](https://github.com/user-attachments/assets/6f9a8320-222c-4f9d-8000-9f010579ba63)
### *Figura 5 : Calculos de los estadisticos descriptivos*
##
![image](https://github.com/user-attachments/assets/41fbc393-f27c-4f36-a24b-22537ac2cb05)
### *Figura 6 : Calculo del SNR*

## Clasificación de la señal 
Para clasificar la señal EEG, podemos seguir un enfoque basado en las bandas de frecuencia estándar del EEG: 
1. **Delta(0.5 - 4 Hz)**: Asociada al sueño profundo
2. **Theta(4 - 8 Hz)**: Relacionada a la somnolencia,relajación profunda o estados meditativos
3.**Alpha (8 -13 Hz)**:Presente en estados de relajación y vigilia tranquila
4.**Beta (13 -30 Hz)**: Asociada con actividad mental activa y de concentración. 
5.**Gamma (30 - 100  Hz)**: Relaciona con procesos cognitivos superiores. 


En este caso nuestra señal varia al rededor de 8 Hz Lo cual nos dice que puede clasificarse tanto como una señal Theta como Alpha, para determinar cual de estas dos señales es nos tocaria realizar calculos mas rigurosos. 

## Análisis de los estadisticos descriptivos 
![image](https://github.com/user-attachments/assets/296cf0c2-b650-4d95-9dce-15a62e108012)
### *Figura 7 : Descriptivos estadisticos de la señal*
 Los diferentes análisis tanto como de los descriptivos como de los SNR calculados nos muestra que: 
 - Ls señal EEG mostró una frecuencia media en el rango esperado para la actividad cerebral normal.
 - la transformada de fourirer reveló la presencia de componentes de baja frecuencia, lo cual es normal en las señales EEG
 - El histograma de frecuencias indicó antes y despues del rudio de la muestra:
 - -**Incremento de la media**: Sugiere un desplazamiento en los valores de la señal por la adición de ruido
   -**Aumento drástico de la desviación estandar**: Indica que hay mayor dispersión en los datos, señla de una mayor 
     perturbación en la señal original.
   -**SNR más bajo con ruido tipo artefacto**: Este tipo de ruido degrada la señal EEG más que los otros tipos de ruidos 
     evaluados
   -**Frecuencia de muestreo de 8 Hz**: Esta frecuencia es adecuada para ciertos análisis de EEG de baja frecuencia, pero 
     insuficientes para captar detalles de alta frecuencia.
   
A continuación se mostraran las diferentes graficas ya explicadas:
![image](https://github.com/user-attachments/assets/9133a78b-68ac-4287-9aa2-43f205290d5e)
### *Figura 8 : Señal original*
![image](https://github.com/user-attachments/assets/928e02f2-de32-4505-9d1b-f7344e0d7048)
### *Figura 9: Histograma* 
![image](https://github.com/user-attachments/assets/a0fcd967-28ae-4b94-b542-594835cf11e7)
### *Figura 10 : Transformada de fourier de la señal*
![image](https://github.com/user-attachments/assets/d02f8427-f001-4b79-bd89-953d81c6380e)
### *Figura 11 : Ruido tipo Gaussiano*
![image](https://github.com/user-attachments/assets/136ad515-7986-4208-8559-957516f0c4dc)
### *Figura 12 : Ruido de tipo impulso*
![image](https://github.com/user-attachments/assets/7aa095df-6227-4f4a-a8bf-986cf9ecc922)
### *Figura 13 : Ruido tipo Artefcato*


## Conclusión
Se evidencia que la convolución a mano es la misma que arroja Python, mostrando como se ve la señal resultante entre una señal x[n] y un sistema h[n] y reconociendo que esta operación sirve para modelar la salida de un sistema LTI ante una entrada específica. En cuanto a la correlación, muestra las similitud que puede tener la señal y los patrones que coinciden entre las señales y la transformada de fourier nos ofrece una perspectiva en el dominio de la frecuencia de la señal EEG, facilitando el análisis y diseño de sistemas.

El análisis estadistico permitió caracterizar una señal EEG en terminos tanto temporales como espectrales. la transformada de fourier due clvase para identificar patrones de frecuencia y distribución en el dominio espectral. Además, el estudio de los estadísticos antes y despues del ruido permitió evaluar cómo diferentes tipos de ruidos pueden afectar la señal EEG. 

Se evidencia que la convolución a mano es la misma que arroja Python, mostrando como se ve la señal resultante entre una señal x[n] y un sistema h[n] y reconociendo que esta operación sirve para modelar la salida de un sistema LTI ante una entrada específica. En cuanto a la correlación, muestra las similitud que puede tener la señal y los patrones que coinciden entre las señales y la transformada de fourier nos ofrece una perspectiva en el dominio de la frecuencia de la señal EEG, facilitando el análisis y diseño de sistemas.






