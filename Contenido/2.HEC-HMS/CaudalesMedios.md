<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="R.LTWB" width="100%" border="0" /></a></div>

# Caudales Medios. Metodología de tanques sucesivos

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

Keywords: `HEC-HMS` `Balance Hidrológico` `Caudales Medios` `Escorrentía` `Tanques Sucesivos`

## Introducción

En el presente apartado se describirán los procedimientos y los conceptos necesarios para la estimación de caudales medios para diferentes intervalos de tiempo utilizando Hec-Hms. Se desarrollarán los conceptos a partir de un ejemplo práctico aplicado a una lluvia total diaria para una extensión superior a 20 años de registros. 

Se utilizarán los conceptos de balance de masas en una cuenca hidrográfica aplicando la metodología de los tanques sucesivos. La metodología se centrará en determinar el caudal medio diario para una extensión igual a la extensión de la lluvia media diaria.  

## Objetivos

El objetivo principal del presente apartado es comprender, analizar y aplicar las herramientas básicas de HEC-HMS para la determinación de caudales medios para diferentes intervalos de tiempo utilizando las herramientas incorporadas de HEC-HMS en su versión más reciente correspondiente al modelo de tanques sucesivos. 

## Caudales medios. Modelo de tanques

El modelo de tanques disponible en el software “HEC-HMS” es un modelo que permite estimar los caudales diarios tomando como valores de entrada una serie continua de registros de precipitación diaria y valores de evapotranspiración potencial y evapotranspiración real. Este modelo también necesita diferentes parámetros que dependen del tipo de cobertura vegetal y del tipo de suelo. 

El módulo de tanques del “Hec-Hms” divide el proceso de transformación de lluvia – escorrentía a nivel diario en cinco (5) tanques o etapas. Los dos primeros tanques corresponden a los procesos de retención y de escorrentía en la superficie. Los tres tanques restantes modelan los procesos de retención y escorrentía subsuperficial. En la Figura 12 se presenta un esquema general que representa las diferentes etapas o tanques que considera este modelo. 

En la siguiente figura se presenta gráficamente lo mencionado en el párrafo anterior:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_88.PNG" width="500px"> 
</div>

Cada uno de los tanques del modelo de HECHMS corresponden subetapas que permiten simplificar los procesos de abstracción que ocurren en una cuenca. Los procesos de abstracción corresponde a la pérdida de masa de agua que sufre la precipitación desde el inicio de la lluvia, pasando por la retención en las plantas (canopy), seguido de las pérdidas en la superficie del suelo hasta finalizar por los diferentes procesos en el subsuelo hasta convertirse en escorrentía superficial y/o escorrentía subsuperficial. 

En la siguiente figura se define gráficamente lo mencionado en el párrafo anterior y que corresponde a los procesos de abstracción que el modelo HECHMS simplifica en los cinco tanques. 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_89.PNG" width="800px"> 
</div>

### Tanque 1: Canopy Interception

Corresponde al tanque que simula la intercepción del agua de precipitación debido a la cobertura vegetal de las plantas. Uan fracción de la lluvia se pierde en este tanque (es retenido por las hojas y posteriormente se evapotranspira). La fracción no retenida continua al siguiente tanque.

### Tanque 2: Surface depression

Corresponde al tanque que simula el almacenamiento en las depresiones o imperfecciones de la superficie. En este tanque, las entradas corresponden a la fracción que sale del tanque 1 y las salidas corresponden a la infiltración del suelo (que ingresa al tanque 3) y a la evapotranspiración. Si la diferencia de las entradas y salidas es positivo (mayor a cero), generará escorrentía superficial. 

### Tanque 3: Primer almacenamiento en el suelo

Este tanque simula el suelo en la zona parcialmente saturada y que HEC-HMS divide en dos procesos: La retención permanente debido a la tensión superficial y que, posteriormente, se pierde en evapotranspiración y la retención temporal cuya fracción puede derivarse en percolación por el medio porozo, el cual corresponde a la entrada del tanque 4.

### Tanque 4: Segundo almacenamiento en el suelo. Acuífero superficial

El modelo de tanques incorporado en el HECHMS define los acuíferos en dos etapas: Una etapa superficial (tanque 4) y una etapa profunda (tanque 5). El tanque 4 permite la retención del flujo del agua proveniente de la percolación del tanque 3. Una parte continua por percolación al acuífero profundo y otra parte que fluye como caudal subsuperficial que hace parte del caudal base que finalmente se convierte en escorrentía superficial del cauce natural.  


### Tanque 5: Segundo almacenamiento en el suelo. Acuífero superficial

 El tanque 5 permite la retención del flujo del agua proveniente de la percolación del tanque 4. Una parte continua por percolación a una fracción del suelo que no genera escorrentía (agua que no retorna a la superficie) y otra parte que fluye como caudal subsuperficial que hace parte del caudal base que finalmente se convierte en escorrentía superficial del cauce natural.  

## Información. Calidad y cantidad de las variables conocidas

Para la elaboración de los modelos de balance de masas utilizando los tanques sucesivos, se deben conocer más de 18 variables del suelo, la evapotranspiración real y potencial en la cuenca y la precipitación media base en el sistema. Debido a la gran cantidad de información que este modelo requiere, se recomienda su aplicación con prudencia, ya que, es posible que sea necesario de información secundaria para determinar las variables del suelo. La cantidad y calidad de la información dependerá de la magnitud del proyecto, la caracterización de la cuenca y los recursos de tiempo y presupuesto disponibles.

## Ejercicio de aplicación para el desarrollo de la actividad

Con el objetivo de aprender a usar el software HEC-HMS para la estimación de caudales medios diarios, a continuación se presenta un ejercicio que se irá desarrollando:

Una empresa de ingeniería ha sido contratada para elaborar un estudio de impacto ambiental, en el que se requiere estimar la curva de duración de caudales medios diarios para la solicitud de un punto de demanda de agua superficial. 

Debido a que la cuenca no cuenta con registros de caudales medios diarios, es necesario la elaboración de un modelo lluvia escorrentía, que permita estimar el caudal medio diario en un punto de control utilizando registros de lluvia diaria con una extensión de 25 años. 

### Información disponible para el ejercicio

Con ayuda de información cartográfica se ha caracterizado la cuenca en estudio. En el siguiente cuadro se presentan las principales características de la cuenca:

| Característica               | Valor | Unidades | 
|------------------------------|:------|----------|
| Área                         | 2.12  | km²      | 
| Perímetro                    | 4.22  | km       | 
| Longitud del cauce principal | 1.80  | km       | 
| Longitud axial de la cuenca  | 1.92  | km       | 
| Tiempo de concentración      | 1.12  | horas    | 


Utilizando los registros de dos estaciones pluviométricas cercanas a la cuenca en estudio, se creó una serie anual de precipitación diaria con una extensión de 41 años, desde el 01 de enero de 1980 hasta el 31 de diciembre de 2020. En el siguiente link se encuentra la lluvia total diaria de la cuenca: <a href="https://github.com/AndresOtalora92/MOHI/tree/master/Contenido/2.HEC-HMS/diapositivas/RegistroPrecipitacion.csv"><i>Registros de Precipitacion Diaria</i></a>

Utilizando los registros de temperatura media diaria y a partir de ecuaciones empíricas, se determinó la evapotranspiración potencial mensual multianual de la cuenca. Los valores se presentan en la siguiente tabla:

| Mes        | Evapotranspiración <br/> potencial (mm/mes) |
|------------|:--------------------------------------------|
| Enero      | 193.0                                       |
| Febrero    | 204.0                                       |
| Marzo      | 219.0                                       | 
| Abril      | 162.0                                       | 
| Mayo       | 140.0                                       | 
| Junio      | 140.0                                       | 
| Julio      | 162.0                                       | 
| Agosto     | 151.0                                       | 
| Septiembre | 131.0                                       | 
| Octubre    | 126.0                                       | 
| Noviembre  | 123.0                                       | 
| Diciembre  | 157.0                                       | 


Para la estimación de la evapotranspiración real mensual multianual en la cuenca, utilice un factor de 0.75 si la evapotranspiración mensual multianual es igual o menor que 157 mm/mes y 0.80 si es mayor a 157 mm/mes.


Finalmente, a partir de información de campo y de planchas tomadas de diferentes fuentes de dominió público, se determinaron las principales características del suelo y de la cobertura vegetal de la cuenca. Las características se resumen en la siguiente tabla:


| Característica                                           | Valor | Unidades | 
|----------------------------------------------------------|:------|----------|
| Canopy:Almacenamiento inicial                            | 50    | %        | 
| Canopy:Máximo almacenamiento                             | 10    | mm       | 
| Almacenamiento inicial en el suelo                       | 50    | %        |
| Almacenamiento inicial acuífero<br/>superficial          | 10    | %        |
| Almacenamiento inicial acuífero<br/>profundidad          | 5     | %        |
| Máxima tasa de infiltración                              | 2     | mm/hr    |
| Área impermeable                                         | 10    | %        |
| Almacenamiento máximo de agua en el suelo                | 80    | mm       |
| Tensión superficial máxima                               | 5     | mm       |
| Tasa máxima de percolación del suelo al acuífero         | 0.35  | mm/hr    |
| Almacenamiento máximo en el acuífero superficial*        | 10    | mm       |
| Tasa máxima de percolación<br/>acuífero superficial*     | 3.5   | mm/hr |
| Tasa de retardo desde el acuífero a flujo subsuperficial | 2.0   | hr |

*Se asumirá que no existe acuífero profundo.


## Creación de un nuevo documento en HEC-HMS

Para iniciar con el modelo, se recomienda crear una carpeta sin caracteres especiales, tales como:"%,&,*;$,#,´,+,-,/,?,¡" entre otros. Adicionalmente, la ruta de la carpeta debe ser lo más corta posible. 

En la siguiente figura se presenta un ejemplo de lo mencionado. Se ha creado una carpeta con el nombre "hechms" en la carpeta documentos.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_90.PNG" width="700px"> 
</div>

Una vez creada la carpeta en la ruta, se creará un documento en blanco. 
Para realizar esto, en la barra de "herramientas y menús", buscar el botón "nuevo". Al dar clic en este botón se abrirá una nueva ventana, la cual solicitará el nombre del proyecto, el cual corresponderá al nombre de la cuenca, la ubicación del archivo y el sistema de unidades.  En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_91.PNG" width="700px"> 
</div>

Para este ejemplo, llamaremos "QmedioDiario" el archivo principal de HEC - HMS. La ruta donde se guardará el archivo corresponderá a la carpeta que se acaba de crear y el sistema de unidades corresponderá al sistema métrico o sistema internacional.

Al realizar esto, se creará una carpeta con el mismo nombre del archivo en la barra de "exploración de cuenca". En la barra de estado (parte superior del software) se verá la ruta de guardado del archivo principal.

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_92.PNG" width="700px"> 
</div>

Al abrir la carpeta donde se guardó el archivo, el usuario podrá notar que se crearon subcarpetas y otros archivos aparentemente en blanco y con distintas extensiones. Estas subcarpetas y archivos corresponden a todos los archivos que HEC-HMS requiere para funcionar adecuadamente.

En la siguiente figura se presenta lo mencionado.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_93.PNG" width="700px"> 
</div>


## Características morfométricas y modelo lluvias escorrentía. Definición en HEC-HMS

Una vez creado el archivo principal, se deben crear la cuenca prinicipal y la subcuenca que define el sistema hidrológico. Para realizar esto, inicialmente se creará el espacio de trabajo que corresponderá a la cuenca principal. En la barra de herramientas y menús, damos clic en "Components" y en la subcategoría "Basic Model Manager"

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_33.PNG" width="700px"> 
</div>

Se abrirá una ventana en la cual seleccionaremos la opción "New". Se abrirá una pequeña ventana la cual solicitará el nombre de la cuenca. Para este caso, el nombre elegido es "Cuenca1"

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_34.PNG" width="700px"> 
</div>

Al realizar esto, en la barra de exploración de la cuenca, se creará un ícono que representa la cuenca principal. Adicionalmente, la zona o "ventana de mapa" cambiará de color gris a color blanco.

En la siguiente figura se presenta lo mencionado:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_35.PNG" width="700px"> 
</div>

Ahora, con la cuenca creada, se deberán definir la subcuenca. Para realizar esto, en la barra de herramientas y menús, se debe selecionar la ópción "Subbasin Creation Tool", tal como se presentan en la siguiente figura:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_36.PNG" width="700px"> 
</div>

Al dar clic en el botón "Subbasin Creation Tool" se debe picar sobre la ventana de mapa en el lugar deseado. Una vez se pique sobre la ventana del mapa, se abrirá una ventana que solicita el nombre de la subcuenca. Para este caso se definirán el mismo nombre indicado en el ejercicio: "Subcuenca1".

## Modelo lluvia - escorrentía. Modelo de pérdidas y modelo de balance.

Inicialmente, se diligenciará el campo del área hidráulica. Para realizar esto, se da clic sobre la subuenca creada y en la opción "Área(km²)" se define escribe el área de la subcuenca, tal como se presenta en la siguiente imagen.

<div align="center">
  <img src="Imagenes/FiguraHECHMS_94.PNG" width="700px"> 
</div>

Ahora se definirán los métodos de la determinación de la retención en la cobertura vegetal (canopy), el método de pérdidas (modelo de transformación lluvia escorrentía de tanques sucesivos: "Soil Moisture Accounting") y el método para la estimación del caudal base (BaseFlow Method).

Para realizar esto, en la misma ventana donde se ingresan los datos de área, en la parte inferior, se encuentran los elementos mencionados. Se seleccionan las opciones indicadas en el párrafo anterior, tal como se presenta en la siguiente imágen:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_95.PNG" width="700px"> 
</div>

A continuación se definirán las variables que permiten la estimación de la retención de agua en las hojas de la cobertura vegetal en la cuenca. Para realizar esto, en la segunda opción "Canopy" se deben diligenciar los valores solicitados y que corresponden al "Almacenamiento inicial" (almacenamiento inicial de la retención en las hojas) "máximo almacenamiento" (en las hojas) y el coeficiente de cultivo o "Crop Coefficient", que describe la capacidad de evapotranspirar de la planta. Este último parámetro depende del tipo de cultivo presente en la cuenca y de la etapa de desarrollo. 

En las siguientes tablas se encuentra un consolidado de los coeficientes de cultivo (Kp) más usado disponibles en la literatura y que pueden servir de guía al lector para futuros trabajos o investigaciones:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_96.PNG" width="600px"> 
</div>

<div align="center">
  <img src="Imagenes/FiguraHECHMS_97.PNG" width="600px"> 
</div>

<div align="center">
  <img src="Imagenes/FiguraHECHMS_98.PNG" width="600px"> 
</div>

<div align="center">
  <img src="Imagenes/FiguraHECHMS_99.PNG" width="600px"> 
</div>

<div align="center">
  <img src="Imagenes/FiguraHECHMS_100.PNG" width="600px"> 
</div>


En la siguiente imágen se presenta el resultado final de los datos ingresados:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_101.PNG" width="700px"> 
</div>

Notas:

1. Para la estimación de la evapotranspiración del agua almacenada en los árboles, se ha definido que esta sea calculada tanto en épocas húmedas como en épocas secas.

2. El coeficiente de cultivo (Kp o "Drop Coefficient") se ha definido con un valor de Kp: 0.5, que corresponde a pastos bajos o maleza. 

Posteriormente, se deben definir las variables que definen las pérdidas de masa y la retención en los diferentes niveles (tanques) que definen el modelo de tanques sucesivos implementado en el HECHMS. Estos parámetros definirán la escorrentía superficial diaria. 

En la siguiente imágen se presenta el resultado final de los datos ingresados:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_102.PNG" width="700px"> 
</div>

Nota: El cuadro verde resalta las variables que deben ingresarse al acuífero profundo. Si se deja en blanco las celdas, como en este caso, se está asumiendo que no existe acuífero profundo y la última etapa del balance finaliza en el acuífero superficial. 

Finalmente, se definen las variables del modelo para la estimación de los caudales base o flujo base. Para este caso, al inicio del ejercicio se definió como metodología de cálculo del caudal base el método de "Recession". Este método corresponde a una función potencial, que inicia en un caudal Qo para un tiempo t:0 y finaliza en un límite Qf. Dicho límite puede definirse como una relación porcentual entre el Caudal Pico del hidrograma de escorrentía superficial y el caudal base.

El modelo se puede escribir como:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_103.PNG" width="150px"> 
</div>

Donde,

Qb, Caudal base (m³/s).
Qo, Caudal inicial del flujo base (m³/s).
K, Constante de recesión.
t, tiempo (hr)

Notas: 

1. Para este problema se escoge un límite del caudal base en 20% (relación entre el caudal base y el caudal pico del hidrograma de escorrentía: "Ratio", en el software HECHMS).

2. Para el presente ejercicio se definirá un caudal inicial Qo de 0.50 m³/s y un valor de K de 0.50. 
En la siguiente imágen se presenta el resultado final de los datos ingresados:

<div align="center">
  <img src="Imagenes/FiguraHECHMS_104.PNG" width="700px"> 
</div>


## Definición de los parámetros hidrológicos. Definición en HEC-HMS

Una vez cargada toda la información morfométrica y los parámetros del modelo de tanque sucesivos, se dispone a carga la lluvia diaria difinida en el enunciado. 

Como ya se mencionó, HEC-HMS agrupa las lluvias en paquetes que denomina "Metereología". Para la definición de los hietogramas que corresponderán a la lluvia diaria , inicialmente se debe crear el elemento "Metereorologia", posteriormente carga la lluvia y finalmente asociar cada lluvia a la respectiva subcuenca. 

### Modelo de metereología 

En la barra de herramientas y menús, seleccionar la opción "Components", seleccionar la categoría "Meteorologic Model Manager", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_105.PNG" width="700px"> 
</div>


Al realizar esto, se desplegará una ventana. En esta ventana se debe seleccionar la opción "New". Se abrirá una nueva ventana, en la cual se solicitará el nombre, escriba para este ejemplo "LluviaDiaria", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_106.PNG" width="700px"> 
</div>

Una vez se acepte el nombre, se creará en la ventana de exploración de la cuenca una carpeta denominada "Meteorologic Model" que al ser desplegada, se abrirá el archivo creado "LluviaDiaria", tal como se presenta en la siguiente figura:

Ahora se debe definir como se ingresarán los valores de la lluvia, que para este caso corresponderá a un hietograma. Para realizar esto, en la ventana de exploración de la cuenca, se debe seleccionar el modelo de lluvia creado (LluviaDiaria) y en la parte inferior, en la ventana de componentes, seleccionar la categoría "Meteorologic Model" y en la opción "Precipitation", seleccionar la opción "Specified Hyetograph", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_107.PNG" width="700px"> 
</div>

En la opción "Basin" definir "yes". Este procedimiento permite que el programa utilice las lluvias (hietogramas) que se crearán para cada subcuenca. Lo mencionado se presenta en la siguiente figura.

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_108.PNG" width="700px"> 
</div>


## Creación y definición de la lluvia en la subcuenca

Con el modelo de metereología creado y definido para la cuenca principal, es siguiente paso corresponde a crear la lluvia específica para la subcuenca a partir de un hietograma. 

Con esta información ya es posible crear los aguaceros o hietogramas de lluvias diarias HEC-HMS.

Para realizar estos, nos dirigimos a la barra de herramientas y menús, damos clic en "Components" y en la opción "Time series data manager", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_109.PNG" width="700px"> 
</div>

Paso seguido, se debe seleccionar la opción "Precipitation Gage" tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_110.PNG" width="700px"> 
</div>


Damos clic en "New" y definimos un nombre del aguacero. Para el aguacero que corresponde a la primera subcuenca se escogerá el nombre "Lluvia1980_2020" tal como se presenta en la figura:


<div align="Center">
  <img src="Imagenes/FiguraHECHMS_111.PNG" width="700px"> 
</div>


Al realizar este procedimiento, en la ventana de exploración de la cuenca, se creará una carpeta denominada "Time-Series data", que al ser desplegada se abrirá el archivo de lluvia creado. 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_112.PNG" width="700px"> 
</div>

Ahora diligenciaremos este nuevo elemento con la lluvia mencionada presentada en el enunciado. Damos clic en la lluvía, seleccionamos la opción "Time Series Gage" buscamos la opción "Units" y seleccionamos "Incremental Milimeters" y en la opción "Time interval" seleccionamos "1 day".

El resultado debe verse similar al presentado en la siguiente figura.

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_113.PNG" width="700px"> 
</div>


Como siguiente paso, seleccionamos en la opción "Time Window" y definimos el tiempo de inicio y el tiempo final de nuestro hietograma (se debe tener presente que el aguacero tarda 41 años).

El resultado debe verse similar al presentado en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_114.PNG" width="700px"> 
</div>


Ahora, se debe dar clic en la opción "Table", posteriormente se diligencia la lluvia. El resultado debe verse similar al presentado en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_115.PNG" width="700px"> 
</div>

Finalmente, con la lluvia creada, se debe indicar que, la lluvia creada corresponderá a la subcuenca 1, para realizar esto, en el modelo "metereología", al desplegar la lluvia y en la opción "Specified Hietograph", definir que la subcuenca 1 tiene la lluvia "lluvia1980_2020". Lo anterior se presenta explicado en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_116.PNG" width="700px"> 
</div>

## Definición de la evapotranspiración

Para ingresar los datos de la evapotranspiración total para cada mes (a nivel multianual: Promedio Multianual) se debe activar la opción de evapotranspiración en la "meteorología" definida y creada en pasos anteriores.

En la siguiente figura se presenta lo mencionado:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_117.PNG" width="600px"> 
</div>

Nota: Las metodologías para la estimación de la evapotranspiración mensual están fuera del alcance de este curso. 

Al realizar esto, se creará un nuevo elemento, en el que, al ser desplegado, permite introducir la evapotranspiración total mensual multianual y el coeficiente de reducción de la evapotranspiración real. 

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_118.PNG" width="600px"> 
</div>

Con base en los datos definidos en el enunciado, se procede a diligenciar los datos, tal y como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_119.PNG" width="600px"> 
</div>

## Definición de los parámetros de la ejecución

Con los parámetros morfométricos de la subcuenca, los parámetros del modelo de tanques sucesivos, la evapotranspiración mensual y de la lluvia (incluyendo la "metereología"), ya es posible definir los parámetros para la ejecución del modelo.

Debido a que el modelo de tanques integrado en el HECHMS, depende de las variables que cambian en el tiempo, es necesario definir un intervalo total de evaluación (inicio y final) y un intervalo de iteración "dt" para la ejecución del modelo. Este intervalo dependerá del intervalo de la lluvia. Para una adecuada estabilidad numérica del modelo computacional, se recomienda que el "dt" de la modelación sea inferior al intervalo del hietograma de la lluvia en la subcuenca. 

Para este ejercicio, teniendo en cuenta que el intervalo de la lluvia es diaria, se asumirá un intervalo de modelación (dt) de 1.0 día. 



Para definir esta condición de modelación en el software, nos dirigimos a la barra de "herramientas y menús", en la categoría "Components", seleccionamos "Creat Component" y damos clic en la subcategoría "Control Specifcation", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_120.PNG" width="700px"> 
</div>

Al realizar esto, se abrirá una ventana que solicitará el nombre del "Control". Para este caso, se dejará el nombre por defecto y que corresponde a "Control 1", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_121.PNG" width="700px"> 
</div>

Al realizar esto se creará un nuevo objeto en la ventana de exploración de la cuenca, tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_122.PNG" width="700px"> 
</div> 

Finalmente, se debe ingresar los valores correspondientes al inicio de la modelación (fecha y hora), el final de la modelación (fecha y hora) y el intervalo (dt) de la modelación, tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_123.PNG" width="700px"> 
</div> 

## Elaboración de una secuencia de modelación ("run")

Con el "Control" creado, el último procedimiento antes de ejecutar el modelo es crear un "run" o "secuencia de modelación". Para realizar esto, nos dirigimos a la barra de "herramientas y menús", en la categoría "Compute", seleccionar "Create Compute" y en seleccionar la subcategoría "Simulation Run", tal como se presenta en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_124.PNG" width="700px"> 
</div> 

Al realizar esto, se abrirá una nueva ventana que preguntará, a partir de 4 pasos, las características del modelo. Las características se asocian a los objetos que se modelarán. Para este caso, el modelo solicitará: El nombre del "run", la cuenca principal, la agrupación de lluvias (metereología) y el control. Para nuestro ejercicio, las ventanas se verán así:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_125.PNG" width="700px"> 
</div> 

El último paso para ejecutar el modelo corresponde a "correr" el modelo (ejecutar la secuencia de modelación). Para realizar esto, nos dirigimos nuevamente a la barra de "herramientas y menús". En la barra principal, en el primer "scroll", seleccionar la secuencia de modelación "Run 1", tal como se observa en la siguiente figura:


<div align="Center">
  <img src="Imagenes/FiguraHECHMS_126.PNG" width="700px"> 
</div> 

Finalmente, en el ícono de "la gota que está sobre una explosión" ejecutamos el modelo, tal como se observa en la siguiente figura:

<div align="Center">
  <img src="Imagenes/FiguraHECHMS_127.PNG" width="700px"> 
</div> 

Para verificar que todo esté bien, se recomienda revisar la ventana de texto y leer los posibles comentarios o advertencias generadas por el modelo.

## Análisis de resultados


### Control de versiones

| Versión    | Descripción   | Autor                                      | Horas |
|------------|:--------------|--------------------------------------------|:-----:|
| 2023.09.10 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   8   |
| 2023.10.10  | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   8   |

_MOHI es de uso libre para fines académicos, conoce nuestra licencia, cláusulas, condiciones de uso y como referenciar los contenidos publicados en este repositorio, dando [clic aquí](../../License.md)._

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [AndresOtalora92](https://github.com/AndresOtalora92?tab=repositories) en GitHub._


| [Anterior](CaudalesMaximos.md) | [:house: Inicio](../../Readme.md) | [:beginner: Ayuda / Colabora] | [Siguiente](Contenido/3.HEC-RAS/Readme.md) |
|-------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------|---------------------------------------------|

<div align="center"><a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBotonCertificado.png" alt="R.LTWB" width="260" border="0" /></a></div>

<div align="center"><a href="http://www.escuelaing.edu.co" target="_blank"><img src="../../.icons/Banner1.svg" alt="Support by" width="100%" border="0" /></a><sub><br>Este curso guía ha sido desarrollado con el apoyo de la Escuela Colombiana de Ingeniería - Julio Garavito. Encuentra más contenidos en https://github.com/uescuelaing</sub><br><br></div>