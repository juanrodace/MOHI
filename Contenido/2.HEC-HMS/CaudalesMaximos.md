<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="R.LTWB" width="100%" border="0" /></a></div>

# Caudales Máximos e hidrogramas de escorrentía directa utilizando HEC-HMS

<div align="center">
  <img src="../.icons/HMS.png" width="150px">
</div>

<div align="center">
<b> Universidad Escuela Colombiana de Ingeniería Julio Garavito</b>
<br></div>

<div align="center">
Andrés Humberto Otálora Carmona
<br></div>

<div align="center">
Profesor del Centro de Estudios Hidráulicos
<br></div>

<div align="center">
andres.otalora@escuelaing.edu.co
<br></div>

Keywords: `HEC-HMS` `Hidrograma` `Caudal Máximo` `Escorrentía` `Hidrograma Unitario`

## Introducción

En este módulo se resumen los conceptos fundamentales de los caudales máximos instantáneos que se presentan en una cuenca hidrográfica. Se recuerdan de manera general el concepto de un hidrograma unitario y de un hidrograma de escorrentía directa. Adicionalmente, se explica paso a paso el procedimiento necesario para determinar el hidrograma de escorrentía directa en una cuenca para un evento de lluvia particular y considerando un tránsito hidrológico.

## Objetivos

El objetivo general de esta actividad es permitirle al estudiante recordar los conceptos generales de un caudal máximo y los conceptos fundamentales que gobiernan hidrogramas de escorrentía directa para finalmente estimarlos en una cuenca hidrográfica utilizando un ejercicio práctico en HEC-HMS.


## Caudales máximos instantáneos
Un cauce natural puede transportar caudales con diferentes magnitudes dependiendo de la época del año, del ciclo hidrológico de la zona, de las características morfométricas de la cuenca, del tipo de suelo, del uso del suelo y de la cobertura vegetal de la cuenca. En un cauce natural se pueden presentar caudales mínimos, caudales medios y caudales máximos. Estos últimos corresponden a caudales que ocurren en muy corto tiempo, por lo cual son denominados caudales instantáneos. Estos caudales se presentan durante eventos extraordinarios generados por lluvias intensas con un cierto periodo de retorno.


## Hidrograma de escorrentía directa

Un hidrograma corresponde a la representación gráfica en un plano cartesiano convencional del caudal que escurre en un cauce o canal en un intervalo de tiempo determinado. En la siguiente figura se presenta un ejemplo de un hidrograma de un cauce natural. 


<div align="center">
  <img src="Imagenes/FiguraHECHMS_24.PNG" width="700px"> 
</div>

Los hidrogramas de escorrentía directa corresponden hidrogramas generados por lluvias intensas en la cuenca. Son hidrograma de corta duración los cuales no tienen en cuenta el caudal o flujo base generado por la escorrentía subsuperficial que puede alimentar un cauce.

El agua de un hidrograma de escorrentía directa en un cauce es generado por los excedentes de escorrentía, una vez la precipitación ha superado las abstracciones iniciales (infiltración y encharcamiento) en una cuenca.

## Caudal base. Flujo subsuperficial

Corresponde al caudal transportado por una corriente natural cuyo flujo proviene de la escorrentía subsuperficial. Lo adecuado para obtener la magnitud del caudal base es a partir de mediciones de campo. También es posible estimar el caudal base a partir de ecuaciones y metodologías empíricas que estiman la magnitud del caudal base en función de la respuesta de la cuenca a largo plazo, considerando todas las entradas y salidas en la cuenca (balances hidrológicos)

## Método del hidrograma unitario

El hidrograma unitario corresponde al hidrograma construido para una cuenca que, para un evento de lluvia con una magnitud de una unidad 1.0 (1 cm/h, 1 pulg/h, etc.) genera una escorrentía en el cauce con una magnitud igual a una unidad de volumen (1 m³, 1 pie³, etc.). Conocido el hidrograma unitario y asumiendo condiciones de linealidad entre la precipitación y la escorrentía directa, es posible conocer el hidrograma de escorrentía directa al realizar el producto entre el hidrograma unitario y una lluvia definida.

## Método del hidrograma unitario adimensional

El hidrograma unitario adimensional o hidrograma unitario universal corresponde a un hidrograma unitario cuyas componentes no tienen unidades. Estos hidrogramas son obtenidos o generados por alguna institución, departamento o centro de investigación.

A partir del hidrograma unitario adimensional y conocidas las características morfométricas de la cuenca y del cauce, es posible determinar el hidrograma unitario de la cuenca en estudio.

El hidrograma unitario adimensional más usado en el mundo corresponde al hidrograma elaborado por el Cuerpo de Ingeniero de los Estados Unidos (SCS). 

En las siguientes figuras se presenta gráficamente y numéricamente el hidrograma unitario adimensional del SCS.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_25.PNG" width="600px"> 
</div>

<div align="center">
  <img src="Imagenes/FiguraHECHMS_26.PNG" width="400px"> 
</div>

## Ejercicio de aplicación para el desarrollo de la actividad

Con el objetivo de aprender a usar el software HEC-HMS para la estimación de un hidrograma de escorrentía directa, a continuación se presenta un ejercicio que se irá desarrollando:

Una empresa de ingeniería ha sido contratada para diseñar el vertedero que permitirá controlar los niveles en una bocatoma qe estará ubicada en el fondo de una corriente natural.

Desde el punto de control correspondiente a la ubicación de la bocatoma, se ha trazado una cuenca. Debido a los afluentes que ingresan al cauce principal, la cuenca se ha dividido en 4 subcuencas tal y como se presenta en la siguiente figura.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_27.PNG" width="400px"> 
</div>

Cada una de las subcuencas fue caracterizada, determinando sus características físicas y morfométricas. También se caracterizó el tipo y uso del suelo. En la siguiente tabla se resumen las principales características de las subcuencas.

| Subcuenca | Área (km²) | Longitud cauce principal (km) | Longitud axial (km) | Pendiente Media de la corriente (m/m) | CN | Condición de Humedad |
|:---------:|:----------:|:-----------------------------:|:-------------------:|:-------------------------------------:|:--:|:--------------------:|
|     1     |     34     |              3.5              |         3.8         |                   0.008857                  | 80 |        Normal        |
|     2     |     40     |              2.5              |         2.8         |                    0.001000                   | 82 |         Seca         |
|     3     |     50     |              4.2              |         5.0         |                    0.001905                  | 81 |        Húmeda        |
|     4     |     74     |              7.0              |         8.0         |                   0.001000                   | 89 |        Norma         |


Para la estimación del tiempo de concentración de cada subcuenca utilice la ecuación de Kirpich.

## Creación de un nuevo documento en HEC-HMS

Una vez se ha instalado el software y se han aceptado todas las condiciones, 
se recomienda crear una carpeta sin caracteres especiales, tales como:
"%,&,*;$,#,´,+,-,/,?,¡" entre otros. Adicionalmente la ruta de la carpeta
debe ser lo más corta posible. 

En la siguiente figura se presenta un ejemplo de lo mencionado. Se ha creado una
carpeta con el nombre "Qmax" en la carpeta documentos.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_28.PNG" width="700px"> 
</div>

Una vez creada la carpeta en la ruta, se creará un documento en blanco. 
Para realizar esto, en la barra de "herramientas y menús", buscar el botón "nuevo"
Al dar clic en este botón se abrirá una nueva ventana, la cual solicitará el nombre del proyecto,
el cual corresponderá al nombre de la cuenca, la ubicación del archivo y el sistema de unidades. 
En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_29.PNG" width="700px"> 
</div>

Para este ejemplo, llamaremos "Ejercicio 1" el archivo principal de HEC - HMS.
La ruta donde se guardará el archivo corresponderá a la carpeta que acabamos de crear 
y el sistema de unidades corresponderá al sistema métrico o sistema internacional.

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_30.PNG" width="700px"> 
</div>

Al realizar esto, se creará una carpeta con el mismo nombre del archivo en la barra de 
"exploración de cuenca". En la barra de estado (parte superior del software) se verá la ruta
de guardado del archivo principal.

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_31.PNG" width="700px"> 
</div>

Al abrir la carpeta donde se guardó el archivo, el usuario podrá notar que se crearon subcarpetas y otros archivos 
aparentemente en blanco y con distintas extensiones.
Estas subcarpetas y archivos corresponden a todos los archivos que HEC-HMS 
requiere para funcionar adecuadamente.

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_32.PNG" width="700px"> 
</div>

## Características morfométricas y modelo lluvias escorrentía. Definición en HEC-HMS

Una vez creado el archivo principal, se deben crear las subcuencas que definen el sistema
hidrológico de la cuenca principal (subcuencas y la red fluvial).

Para realizar esto, inicialmente crearemos el espacio de trabajo que corresponderá a la cuenca principal. 
En la barra de herramientas y menús, damos clic en "Components" y en la subcategoría "Basic Model Manager"

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_33.PNG" width="700px"> 
</div>

Se abrirá un ventana, en la cual seleccionaremos la opción "New". Se abrirá una pequeña ventana
la cual solicitará el nombre de la cuenca. Para este caso, el nombre elegido es "Cuenca1"

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_34.PNG" width="700px"> 
</div>

Al realizar esto, en la barra de exploración de la cuenca, se creará un ícono que representa la cuenca principal. 
Adicionamente la zona o "ventana de mapa" cambiará de color gris a color blanco.

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_35.PNG" width="700px"> 
</div>

Ahora, con la cuenca creada, se deberán definir las subcuencas. Para realizar esto, en la barra de herramientas y menús , 
seleccionaremos la ópción "Subbasin Creation Tool", tal como se presentan en la siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_36.PNG" width="700px"> 
</div>

Al dar clic en el botón "Subbasin Creation Tool" se debe picar sobre la ventana de mapa en el lugar deseado.
Para conocer la distribución aproximada de cada subcuenca (ubicación donde se debe picar) en la cuenca principal, 
se debe analizar con calma la figura definida en el ejercicio.

Una vez se pique sobre la ventana del mapa, se abrirá una ventana que solicita el nombre de la subcuenca. Para este
caso se definirán el mismo nombre indicado en el ejercicio: "Subcuenca1".

Se repetirá este procedimiento para cada una de las subcuencas que definen el problema.

La ventana de dibujo del mapa se debe ver similar al presentado en la siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_37.PNG" width="700px"> 
</div>

Ahora, crearemos el punto de control donde descargarán todas las aguas de las subcuencas. Este punto corresponderá al 
punto final de la cuenca. 

Para realizar, esto nos dirigimos a la barra de herramientas y menús,
seleccionamos el botón "Create a New Sink Element", posteriormente se debe picar sobre la ventana de dibujo del mapa 
en el lugar que el usuario desee, en este caso, la zona más aguas abajo de la cuenca.

Se abrirá una nueva ventana, la cual solicitará el nombre del elemento. Para este caso, se seleccionará
como nombre "PuntoControl", tal como se presenta en las siguientes figuras:


<div align="center">
  <img src="Imagenes/FiguraHECHMS_38.PNG" width="700px"> 
</div>


<div align="center">
  <img src="Imagenes/FiguraHECHMS_39.PNG" width="700px"> 
</div>

Una vez realizado este procedimiento, la ventana de dibujo del mapa se debe ver similar al presentado en la 
siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_40.PNG" width="700px"> 
</div>


Ahora, se crearán los puntos de unión de las corrientes que coinciden en un punto (corrientes que continuan sobre 
el cauce principal). Para realizar esto, en la barra de herramientas y menús, seleccionar el botón "Juction Creation Tool".
Una vez se pica sobre este botón, se debe picar sobre la ventana de dibujo, en la zona indicada por el ejercicio.
Posteriormente, se abrirá una ventana que solicitará el nombre del elemento. Para el primer elemento (primer nodo)
se definirá como nombre "PuntoA". 

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_41.PNG" width="700px"> 
</div>

Este procedimiento se debe realizar para el siguiente nodo (PuntoB). 
Una vez realizado este procedimiento, la ventana de dibujo del mapa se debe ver similar al presentado en la 
siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_42.PNG" width="700px"> 
</div>

Al picar sobre el ícono de la "Cuenca1", se desplegará los íconos que representan las subcuencas, los nodos y el punto
final de la cuenca o punto de control, tal como se presenta en la siguiente figura.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_43.PNG" width="700px"> 
</div>

Ahora, se debe definir el punto aguas abajo de cada elemento. Un punto aguas abajo puede corresponder a otro elemento.
Por ejemplo, la subcuenca 1, según el ejercicio, descarga al punto de unión "PuntoA". Para realizar esto, despliegue, 
desde el ícono de "Subcuenca1", en el elemento "Subbasin", en la harremienta "DownStream" y seleccionar el punto 
"PuntoA"

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_44.PNG" width="700px"> 
</div>

Al realizar esto, en la ventana de dibujo del mapa, debe aparecer una línea simbólica que representa la descarga de un
elemento a otro, tal como se presentan en la siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_45.PNG" width="700px"> 
</div>

Debe repetirse este procedimiento para cada una de las subcuencas.
En la siguiente figura se presenta el resultado de este procedimento:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_46.PNG" width="700px"> 
</div>

Ahora, considerando el tránsito hidráulico del cauce principal desde los puntos de unión, se debe crear un tramo de 
cauce. Para realizar esto, en la barra de herramientas y menús, seleccionar el botón "Reach Creation Tool". Se deberá
picar el elemento que inicia el tramo y posteriormente el elemento final. 

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_47.PNG" width="700px"> 
</div>

Para el primer tramo, se picará el elemento "PuntoA "y el elemento "PuntoB".
Una vez se realiza esto, se abrirá una  ventana que solicitará el nombre. Para el primer tramo, se ha seleccionado el 
nombre "TramoAB". 

En la siguiente figura se presenta el resultado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_48.PNG" width="700px"> 
</div>

Se debe repetir el procedimiento para el tramo que inicia desde el Punto B hasta el punto de control. 

Al finalizar este paso, la ventana de dibujo de la cuenca, se debe parecer a la presentada en la siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_49.PNG" width="700px"> 
</div>

Con las subcuencas creadas en la ventana de dibujo del mapa, el punto de control definido, las descargas o puntos aguas abajo y los tramos de tránsito trazados, se dispone a definir el área de drenaje de cada cuenca y las características del modelo lluvia-escorrentía definido. 

Para realizar esto, en la ventana de exploración de la cuenca, se debe seleccionar una de las subcuencas y en la parte inferior, en la ventana de componentes, seleccionar la categoría "Subbasin" y realizar los siguientes cambios:

a. Área (km²): Corresponde al área de la subcuenca definido en el ejercicio
<div

</div>

b. Loss Method: Método utilizado para determinar las abstracciones inicial de la lluvia bruta. En este caso, seleccionar el método "SCS Curve Number"

<div align="center">
  <img src="Imagenes/FiguraHECHMS_50.PNG" width="700px"> 
</div>

c. Transform Method: Método utilizado para realizar la transformación de la lluvia (hietograma) a escorrentía superficial (hidrograma de escorrentía directa). En este caso, seleccionar el método "SCS Unit Hydrograph" que corresponde al método del hidrograma unitario del Cuerpo de Ingenieros de los Estados Unidos.

d. BaseFlow Method: Corresponde al caudal base o caudal aportado por el flujo subsuperficial y que no corresponde a la lluvia definida para la estimación del caudal. Para este caso, se asumirá que no existe caudal base o que es despreciable frente a la magnitud de los caudales máximos. 

En la siguiente figura se presenta el resumen de lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_50.PNG" width="700px"> 
</div>

Se debe repetir el procedimiento para todas las subcuencas, llenado el espacio de "Área(km²)" con el valor respectivo definido en el ejercicio base. 

#### Tipo, uso de suelo y condición de humedad antecedente. Número de curva (CN)

Teniendo en cuenta que el método utilizado para la estimación de las abstracciones iniciales(encharcamiento e infiltración en la cuenca) se basa en el Número de Curva (CN) desarrollado por el Cuerpo de Ingenieros de los Estados Unidos. Es necesario definir y seleccionar este número a partir de las características de la cobertura, tipo de suelo y uso del  suelo de la cuenca.

En términos simples, el Número de Curva (CN) corresponde a un valor entre 0 y 100, que indica la capacidad de retención del suelo o la capacidad de dejar pasar la escorrentía. Entre mayor es el coeficiente CN, más alta es la capacidad del suelo a permitir escurrir. Un CN 100 es perfectamente liso e impermeable. Un CN de 0 es un orificio de altura infinita, que no permite escurrir nada, todo lo "atrapa".

El CN depende de diferentes factores, tales como el tipo de suelo, el uso del suelo (cobertura vegetal) y la condición de humedad antecedente. Estos conceptos están fuera del alcance del curso, pero es apropiado que el lector conozca los conceptos básicos antes de ingresar la información en el modelo y en el programa.

En el caso del ejercicio, el valor del CN de cada subcuenca ya está definido. Queda pendiente "ajustarlo" por la condición de humedad. Un CN tipo II, corresponde a una zona con humedad media. Un CN tipo I, corresponde a una zona propensa a épocas de estiaje (poca humedad y bajas precipitaciones). Un CN tipo III, corresponde a zona con alta humedad.

El enunciado del ejercicio menciona un suelo tipo II e indica las condiciones de humedad. Para ajustar el CN, se deben aplicar las siguientes ecuaciones:

##### CN_i

<div align="center">
  <img src="Imagenes/FiguraHECHMS_51.PNG" width="200px"> 
</div>


##### CN_iii

<div align="center">
  <img src="Imagenes/FiguraHECHMS_52.PNG" width="200px"> 
</div>

<br> 

</br>

#### Tiempo de concentración y tiempo de retardo en la cuenca (Tlag).

#### Modelo lluvia escorrentía y caudal base.


## Definición de los parámetros hidrológicos. Definición en HEC-HMS


Una vez cargada toda la información geométrica, se dispone a carga la lluvia para un periodo de retorno definido. En esta caso, cada subcuenca tiene un evento de lluvia (aguacero) con diferente magnitud (intensidad) y diferente duración, pero con la misma frecuencia de ocurrencia (5 años). 

HEC-HMS agrupa las lluvias en paquetes que denomina "Metereología". Para la definición de los hietogramas que corresponderán a los aguaceros para cada cuenca, inicialmente se debe crear el elemento "Metereorologia", posteriormente carga los hietogramas y finalmente asociar cada lluvia a la respectiva subcuenca. 

### Modelo de metereología. 

En la barra de herramientas y menús, seleccionar la opción "Components", seleccionar la categoría "Meteorologic Model Manager", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_61.PNG" width="900px"> 
</div>


Al realizar esto, se desplegará una ventana. En esta ventana se debe seleccionar la opción "New". Se abrirá una nueva ventana, en la cual se solicitará el nombre, escriba para este ejemplo "Pe_5", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_62.PNG" width="900px"> 
</div>

Una vez se acepte el nombre, se creará en la ventana de exploración de la cuenca una carpeta denominada "Meteorologic Model" que al ser desplegada, se abrirá el archivo creado "Pe_5", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_63.PNG" width="900px"> 
</div>

Ahora se debe definir como se ingresarán los valores de la lluvia, que para este caso corresponderá a un hietograma. Para realizar esto, en la ventana de exploración de la cuenca, se debe seleccionar el modelo de lluvia creado (Pe_5) y en la parte inferior, en la ventana de componentes, seleccionar la categoría "Meteorologic Model" y en la opción "Precipitation", seleccionar la opción "Specified Hyetograph", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_64.PNG" width="900px"> 
</div>

En la opción "Basin" definir "yes". Este procedimiento permite que el programa utilice las lluvias (hietogramas) que se crearán para cada subcuenca. Lo mencionado se presenta en la siguiente figura.

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_65.PNG" width="900px"> 
</div>

## Creación y definición de la lluvia en las subcuencas

Con el modelo de metereología creado y definido para la cuenca principal, es siguiente paso corresponde a crear los aguaceros para cada subcuenca a partir de un hietograma. En las siguientes figuras se presentan los hietogramas para cada una de las subcuencas:

Nota: la generación de hietogramas o tormentas de diseño, están fuera del alcance de este curso, por tanto, los valores que definidos a continuación son meramente académicos y para efectos prácticos del ejercicio.

**Hietograma de la subcuenca 1:**

| Duración (min) | Precipitación (mm) | 
|----------------|:-------------------|
| 0              | 0                  | 
| 15             | 30                 | 
| 30             | 40                 | 
| 45             | 40                 | 
| 60             | 30                 | 
| 75             | 18                 | 

**Hietograma de la subcuenca 2:**


| Duración (min) | Precipitación (mm) | 
|----------------|:-------------------|
| 0              | 0                  | 
| 15             | 35                 | 
| 30             | 45                 | 
| 45             | 48                 | 
| 60             | 32                 | 
| 75             | 18                 | 


**Hietograma de la subcuenca 3:**


| Duración (min) | Precipitación (mm) | 
|----------------|:-------------------|
| 0              | 0                  | 
| 15             | 28                 | 
| 30             | 29                 | 
| 45             | 32                 | 
| 60             | 32                 | 
| 75             | 30                 | 

**Hietograma de la subcuenca 4:**


| Duración (min) | Precipitación (mm) | 
|----------------|:-------------------|
| 0              | 0                  | 
| 15             | 35                 | 
| 30             | 40                 | 
| 45             | 40                 | 
| 60             | 35                 | 
| 75             | 11                 | 

Con esta información ya es posible crear los aguaceros o hietogramas de lluvias intensas en HEC-HMS.

Para realizar estos, nos dirigimos a la barra de herramientas y menús, damos clic en "Components" y en la opción "Time series data manager", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_66.PNG" width="900px"> 
</div>

Paso seguido, se debe seleccionar la opción "Precipitation Gage" tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_67.PNG" width="900px"> 
</div>


Damos clic en "New" y definimos un nombre del aguacero. Para el aguacero que corresponde a la primera subcuenca se escogerá el nombre "P_subcuenca_1" tal como se presenta en la figura:


<div align="Center">
  <img src="Imagenes/FiguraHECHMS_68.PNG" width="900px"> 
</div>


Al realizar este procedimiento, en la ventana de exploración de la cuenca, se creará una carpeta denominada "Time-Series data", que al ser desplegada se abrirá el archivo de lluvia creado. 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_69.PNG" width="900px"> 
</div>

Repetimos este procedimiento para todas las subcuencas. El resultado debe verse similar al presentado en la siguiente figura: 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_70.PNG" width="900px"> 
</div>

Ahora diligenciaremos estos nuevos elementos a partir de la lluvia defina en los cuadros anteriores (cuadros con la precipitación para cada subcuenca).

Damos clic en uno de los elementos de lluvía, por ejemplo en "Pe_subcuenca_1", seleccionamos en la opción "Time Series Game" buscamos la opción "Units" y seleccionamos "Incremental Milimeters" y en la opción "Time interval" seleccionamos "15 minutes".

El resultado debe verse similar al presentado en la siguiente figura.

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_71.PNG" width="900px"> 
</div>


Como siguiente paso, seleccionamos en la opción "Time Window" y definimos el tiempo de inicio y el tiempo final de nuestro hietograma (se debe tener presente que el aguacero tarda 75 min o lo que es lo mismo, 1 hora y 15 minutos). Como se conoce que el hidrograma de salida durará más tiempo que la lluvia, es necesario definir un intervalo más amplio, por ejemplo 10 horas. Como la lluvia dura solo 75 min, el resto del tiempo se asumirá una lluvia de magnitud cero.

El resultado debe verse similar al presentado en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_72.PNG" width="900px"> 
</div>


Finalmente, se debe dar clic en la opción "Table", posteriormente se diligencia la lluvia, teniendo presente que, después de los 75 min (1 hora y 15 min) se definirán aguaceros de 0 mm.

El resultado debe verse similar al presentado en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_73.PNG" width="300px"> 
</div>


Se debe repetir el procedimiento anterior para todas las lluvias (todas las subcuencas).

Una vez realizado esto, debe asignarse a cada subcuenca, la lluvia respectiva. Para realizar esto, damos clic en "Metereologic Model", abrimos la carpeta donde está la opción "Specified Hyetograph". Al realizar esto, se abrirá una ventana que solicitará, para cada subcuenca,la respectiva lluvia. El resultado de la asignación de la lluvia en cada subcuenca se presenta a continuación:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_74.PNG" width="900px"> 
</div>

## Definición de la lluvia en las subcuencas

## Definición de los parámetros de la ejecución

Con los parámetros morfométricos de cada subcuenca y las características de las corrientes (tramos de corriente), de la descarga (punto de control) y de la lluvia (incluyendo la "metereología"), ya es posible definir los parámetros para la ejecución del modelo.

Debido a que el método utiliza el hidrograma unitario adimensional del SCS, el software HEC-HMS requiere definir intervalos de modelación (dt) con el objetivo de aplicar este hidrograma a la lluvia efectiva. Para una adecuada estabilidad numérica del modelo computacional, se recomienda que el "dt" de la modelación sea inferior al intervalo del hietograma de la lluvia en cada subcuenca. 

Para este ejercicio, teniendo en cuenta que el intervalo de los hietogramas son de 15 min, se asumirá un intervalo de modelación (dt) de 1.0 min. 

Para definir esta condición de modelación en el software, nos dirigimos a la barra de "herramientas y menús", en la categoría "Components", seleccionamos "Creat Component" y damos clic en la subcategoría "Control Specifcation", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_75.PNG" width="900px"> 
</div>

Al realizar esto, se abrirá una ventana que solicitará el nombre del "Control". Para este caso, se dejará el nombre por defecto y que corresponde a "Control 1", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_76.PNG" width="900px"> 
</div>

Al realizar esto se creará un nuevo objeto en la ventana de exploración de la cuenca, tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_77.PNG" width="900px"> 
</div> 

Finalmente, se debe ingresar los valores correspondientes al inicio de la modelación (fecha y hora), el final de la modelación (fecha y hora) y el intervalo (dt) de la modelación, tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_78.PNG" width="900px"> 
</div> 


## Elaboración de una secuencia de modelación ("run")

Con el "Control" creado, el último procedimiento antes de ejecutar el modelo es crear un "run" o "secuencia de modelación". Para realizar esto, nos dirigimos a la barra de "herramientas y menús", en la categoría "Compute", seleccionar "Create Compute" y en seleccionar la subcategoría "Simulation Run", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_79.PNG" width="900px"> 
</div> 

Al realizar esto, se abrirá una nueva ventana que preguntará, a partir de 4 pasos, las características del modelo. Las características se asocian a los objetos que se modelarán. Para este caso, el modelo solicitará: El nombre del "run", la cuenca principal, la agrupación de lluvias (metereología) y el control. Para nuestro ejercicio, las ventanas se verán así:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_80.PNG" width="900px"> 
</div> 

El último paso para ejecutar el modelo corresponde a "correr" el modelo (ejecutar la secuencia de modelación). Para realizar esto, nos dirigimos nuevamente a la barra de "herramientas y menús". En la barra principal, en el primer "scroll", seleccionar la secuencia de modelación "Run 1", tal como se observa en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_81.PNG" width="900px"> 
</div> 

Finalmente, en el ícono de "la gota que está sobre una explosión" ejecutamos el modelo, tal como se observa en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_82.PNG" width="900px"> 
</div> 

Para verificar que todo esté bien, se recomienda revisar la ventana de texto y leer los posibles comentarios o advertencias generadas por el modelo.

## Análisis de resultados

Para analizar los resultados, HEC-HMS tiene distintas herramientas, las cuales muestran los resultados como valores puntuales, tablas resumen, tablas detalladas y gráficos. Estas herramientas se encuentran en la barra de "herramientas y menús", en la zona que se resalta en la siguiente figura. 


<div align="Center">
  <img src="Imagenes/FiguraHECHMS_83.PNG" width="900px"> 
</div> 


Es posible consultar los resultados de cada elemento creado en la cuenca (subcuencas, tramos de corrientes, puntos de descarga, etc.). Al seleccionar un elemento en la ventana de "visualización del mapa" y posteriormente hacer clic en algunas de las herramientas de presentación de resultados, se abrirá una nueva ventana con el resumen de la información más relevante del objeto seleccionado.

A manera de ejemplo, a continuación se presentan los resultados obtenidos en una de las subcuencas del modelo (subcuenca 1): 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_84.PNG" width="900px"> 
</div> 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_85.PNG" width="900px"> 
</div> 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_86.PNG" width="900px"> 
</div> 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_83.PNG" width="900px"> 
</div> 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_87.PNG" width="900px"> 
</div> 

Con esta guía de como generar resultados, el usuario ya puede analizar los caudales, las abstracciones, los caudales pico, el tránsito de las crecientes y los diferentes hidrogramas de escorrentía directa de las subcuencas y de la cuenca principal (punto de control) del modelo y tomar decisiones basado en su proyecto o investigación.



### Control de versiones

| Versión    | Descripción   | Autor                                      | Horas |
|------------|:--------------|--------------------------------------------|:-----:|
| 2023.08.23 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   4   |
| 2023.08.24 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   3   |
| 2023.08.25 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   2   |
| 2023.08.29 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   3   |
| 2023.08.30 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   6   |
| 2023.08.31 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   2   |
| 2023.09.03 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   3   |

_MOHI es de uso libre para fines académicos, conoce nuestra licencia, cláusulas, condiciones de uso y como referenciar los contenidos publicados en este repositorio, dando [clic aquí](../../License.md)._

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [AndresOtalora92](https://github.com/AndresOtalora92?tab=repositories) en GitHub._


| [Anterior](Generalidades_HECHMS) | [:house: Inicio](../../Readme.md) | [:beginner: Ayuda / Colabora] | [Siguiente](CaudalesMedios.md) |
|--------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------|

<div align="center"><a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBotonCertificado.png" alt="R.LTWB" width="260" border="0" /></a></div>

<div align="center"><a href="http://www.escuelaing.edu.co" target="_blank"><img src="../../.icons/Banner1.svg" alt="Support by" width="100%" border="0" /></a><sub><br>Este curso guía ha sido desarrollado con el apoyo de la Escuela Colombiana de Ingeniería - Julio Garavito. Encuentra más contenidos en https://github.com/uescuelaing</sub><br><br></div>