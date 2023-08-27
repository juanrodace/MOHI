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

Para realizar esto no crearemos el espacio de trabajo que corresponderá a la cuenca principal. 

#### Tipo, uso de suelo y condición de humedad antecedente. Número de curva (CN)

#### Tiempo de retardo (Tlag).

#### Modelo lluvia escorrentía y caudal base.


## Definición de los parámetros hidrológicos. Definición en HEC-HMS

### Lluvia de diseño. Hietograma.

## Definición de la lluvia en las subcuencas

## Definición de los parámetros de la ejecución

## Elaboración de una corrida

## Análisis de resultados

### Control de versiones

| Versión    | Descripción   | Autor                                      | Horas |
|------------|:--------------|--------------------------------------------|:-----:|
| 2023.08.23 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   4   |

_MOHI es de uso libre para fines académicos, conoce nuestra licencia, cláusulas, condiciones de uso y como referenciar los contenidos publicados en este repositorio, dando [clic aquí](../../License.md)._

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [AndresOtalora92](https://github.com/AndresOtalora92?tab=repositories) en GitHub._


| [Anterior](Generalidades_HECHMS) | [:house: Inicio](../../Readme.md) | [:beginner: Ayuda / Colabora] | [Siguiente](CaudalesMedios.md) |
|--------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------|

<div align="center"><a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBotonCertificado.png" alt="R.LTWB" width="260" border="0" /></a></div>

<div align="center"><a href="http://www.escuelaing.edu.co" target="_blank"><img src="../../.icons/Banner1.svg" alt="Support by" width="100%" border="0" /></a><sub><br>Este curso guía ha sido desarrollado con el apoyo de la Escuela Colombiana de Ingeniería - Julio Garavito. Encuentra más contenidos en https://github.com/uescuelaing</sub><br><br></div>