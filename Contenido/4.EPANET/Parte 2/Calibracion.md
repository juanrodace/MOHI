<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="R.LTWB" width="100%" border="0" /></a></div>

# Curso de Epanet - Módulo 3 - Incorporación de datos de calibración de una red hidráulica utilizando EPANET

<div align="center">
  <img src="../../.icons/IconoEpanetV3.png" width="600px">
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

Keywords: `Calibración` `Iteraciones` `Variables base`

## Introducción

En esta actividad se presenta el procedimiento para la incorporación de datos tomados en campo de una red existente, en pocas palabras información base real que puede ser utilizada para la calibración de un modelo numérico, como por ejemplo en EPANET.

## Objetivos

El objetivo principal de esta actividad es mostrarle al usuario el procedimiento sugerido para cargar información tomada en campo de un sistema hidráulico construido y en funcionamiento que servirá de base para calibrar el modelo numérico. 

## Datos base para calibración

Las herramientas "Datos de calibración" e "informe de calibración" permiten al usuario cargar los resultados de una toma de campo de diferentes variables (presión, demanda, alturas en los nodos y caudale y velocidades en las tuberías) a partir de un archivo plano previamente elaborado en un software de lectura tales como "block de nota", "note++" entre otros. 

En este [link](https://pruebacorreoescuelaingeduco-my.sharepoint.com/:u:/g/personal/andres_otalora_escuelaing_edu_co/EQM5r75s9V1OrFoeRJvThvwBxdvi0i0KgDXksAGGGK_Hmw?e=YcY1nu) podrá descargar un ejemplo del formato elaborado en "block de nota" y guardado con extensión ".dat", el cual puede utilizar para sus proyectos cambiando las columnas de "Location" (nombre del objeto: nodo, tubería, tanque, etc.), "Time" (tiempo de la modelación si se analiza con "periodo extendido") y "Value" (parámetro de calibración tomado en campo).

Una vez ingresado los datos y generado los informes, es necesario que el usuario, si así lo desea, modifique los parámetros hidráulicos o geométricos que requiera cambiar en la red (generalmente el coeficiente de rugosidad) para que los resultados obtenidos del modelo numérico se acerquen lo más posible a los datos tomados en campo y que su modelo este "calibrado"

Cabe destacar que el software EPANET no integra herramientas que le permitan realizar múltiples iteraciones modificando una variable tal que se pueda calibrar la red a partir de variables de entrada tomados en campo. Es posible crear desarrollos en otros lenguajes (o en el mismo programador de EPANET) para que esto sea posible.

<br>

<br>

<div align="center">
       <a href="https://youtu.be/TFpLtc_It1k">
        <img src="../../.icons/INICIO_ACTIVIDAD.PNG" width="800px">
    </a>
</div>



## Ejemplo de aplicación

Utilizando la red hidráulica construida y presentada en las actividades anteriores de este módulo, se desarrollará esta actividad. 

Se requiere ingresar los datos de calibración presentados en el siguiente cuadro que corresponden a valores de presión medidos en campo en los seis (6) nodos qfr la red con el objetivo que, en posteriores procedimientos, la red pueda ser calibrada modificando los parámetros hidráulicos y geométricos, como por ejemplo el coeficiente de rugosidad:

<div align="center">

| Nombre del Nodo | Presión (m.c.a) | 
|-----------------|:----------------|
| N2              | 7               |
| N3              | 5               |
| N4              | 6               |
| N5              | 6               |
| N6              | 7               |

</div>



## Datos para calibración e informe de calibración en EPANET


_a Se tomará como modelo hidráulico base la red presentada en la siguiente imagen._

<div align="center">
  <img src="Imagenes/FiguraNo.2.145.PNG" width="700px">
</div>


_b. En la barra de herramientas "Proyecto" buscar la opción "Datos de calibración"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.146.PNG" width="700px">
</div>

_c. Se abrirá una ventana en la cual se presentan las variables que pueden ser ingresadas como datos base de una posible calibración_

<div align="center">
  <img src="Imagenes/FiguraNo.2.147.PNG" width="700px">
</div>

_d. Se crea el archivo base en el editor de texto. Se editan las tres columnas que se presentan en el formato indicado anteriormente revisando detalladamente el nombre de los objetos a los cuales se les ingresarán estos valores de calibración_

<div align="center">
  <img src="Imagenes/FiguraNo.2.148.PNG" width="700px">
</div>

_e. En la ventana de "Datos de calibración", en el campo "Presión" se da clic en el botón "Examinar" y se busca la ubicación del documento con formato ".dat" creado previamente, se selecciona y se da clic en el botón aceptar._

<div align="center">
  <img src="Imagenes/FiguraNo.2.149.PNG" width="700px">
</div>

_f. Una vez ingresado los datos se procede a ejecutar el modelo. Para realizar la revisión y la comparación que hace EPANET entre los datos modelados y los datos ingresados, se procede a buscar la opción "Calibración" de la barra de herramientas "Informe"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.150.PNG" width="700px">
</div>

_g. Se abrirá una ventana con el tipo de variables que puede hacer un informe de comparación. En este caso seleccionamos la opción "presión"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.151.PNG" width="700px">
</div>

_h. Se selecciona la primera opción y se obtiene un primer reporte numérico a manera de tabla que puede ser importado o copiado a un editor de cálculo como por ejemplo Excel. En este reporte se comparan los valores modelados en los objetos seleccionados con los valores de calibración. También se presenta el error natural y error cuadrático medios entre los dos valores de cada objeto_

<div align="center">
  <img src="Imagenes/FiguraNo.2.152.PNG" width="700px">
</div>

_i. En la segunda opción se abrirá una gráfica de dispersión en la cual se comparan los datos obtenidos con los datos calibrados. Entre más cerca estén los puntos a la gráfica (línea a 45°) mejor será la aproximación numérica y menor será el error._

<div align="center">
  <img src="Imagenes/FiguraNo.2.153.PNG" width="700px">
</div>

_j. En la tercera opción se presenta, también de manera gráfica pero esta vez con un diagrama de barras (histograma), la comparación entre los valores obtenidos con la simulación numérica con los datos tomados en campo para cada uno de los objetos seleccionados._

<div align="center">
  <img src="Imagenes/FiguraNo.2.154.PNG" width="700px">
</div>

### Control de versiones

| Versión    | Descripción   | Autor                                      | Horas |
|------------|:--------------|--------------------------------------------|:-----:|
| 2022.08.12 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |  2.0  |


_CursoEpanetBasico-Intermedio es de uso libre para fines académicos.

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [AndresOtalora92](https://github.com/AndresOtalora92?tab=repositories) en GitHub._


| [Anterior](../ModuloNo.3/ValvulasyAccesorios.md) | [:house: Inicio](../../README.md) | [Fin del curso](../../README.md) |
|-------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------|

<div align="center"><a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBotonCertificado.png" alt="R.LTWB" width="260" border="0" /></a></div>

<div align="center"><a href="http://www.escuelaing.edu.co" target="_blank"><img src="../../.icons/Banner1.svg" alt="Support by" width="100%" border="0" /></a><sub><br>Este curso guía ha sido desarrollado con el apoyo de la Escuela Colombiana de Ingeniería - Julio Garavito. Encuentra más contenidos en https://github.com/uescuelaing</sub><br><br></div>