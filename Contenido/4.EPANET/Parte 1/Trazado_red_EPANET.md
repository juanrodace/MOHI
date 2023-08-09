<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="R.LTWB" width="100%" border="0" /></a></div>

# Curso de Epanet - Módulo 2 - Elaboración y trazado de una red hidráulica. Construcción del esqueleto del modelo hidráulico

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

Keywords: `EPANET` `geometría` `trazado` `nodos` `red`

## Introducción

En este módulo se detallan algunas metodologías para la creación del esqueleto o el borrador de la red que posteriormente debe ser alimentada con información. Se explica como cargar una red utilizando AutoCAD, como crear directamente la red en EPANET y como crear los principales elementos (tuberías y nodos) a partir de una imagen de fondo.

## Objetivos

El objetivo principal de esta actividad es presentar diferentes alternativas para la creación del esqueleto o geometría de un sistema hidráulica a presión conformado por una red abierta o una red cerrada. El usuario decidirá cuál de los procedimientos aquí explicado es el más adecuado teniendo en cuenta la magnitud y dificultad de su red.  


<br>

<br>

<div align="center">
       <a href="https://youtu.be/u-O-luVKyp8">
        <img src="../../.icons/INICIO_ACTIVIDAD.PNG" width="800px">
    </a>
</div>


## Trazar una red con las herramientas de EPANET

A continuación se detallan los procedimientos sugeridos para realizar el trazado de una red hidráulica (mismo procedimiento si la red es abierta o cerrada), tomando como referencia esquemas previamente realizados. 


**1. Definir el esquema general de la red:** Para el primer trazado se utilizará la red abierta planteada en el ejercicio 1F y que se presenta nuevamente a continuación:

<div align="center">
  <img src="../ModuloNo.1/Imagenes/FiguraNo.1.36.PNG" width="500px">
</div>

**2. Crear nuevo archivo y área de trabajo:** Abrir el programa y guardar un nuevo archivo

_a. Buscar el software en su computador personal_
<div align="center">
  <img src="Imagenes/FiguraNo.2.18.PNG" width="400px">
</div>

_b. Definir en la barra de herramienta la opción "Menu"_
<div align="center">
  <img src="Imagenes/FiguraNo.2.19.PNG" width="700px">
</div>

_c. Definir en la barra de herramienta la opcion "Guardar" o "Guardar Como"_
<div align="center">
  <img src="Imagenes/FiguraNo.2.20.PNG" width="700px">
</div>

_d. Buscar la ruta y la carpeta donde desea crear su nuevo archivo de EPANET. Crear un nombre corto, sin tilde evitando los caracteres especiales"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.21.PNG" width="700px">
</div>

**3. Creación de nodos, tanques y tramos de tuberías**

_a. Seleccionar la opción "Añadir Embalse"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.22.PNG" width="700px">
</div>

_b. Picar en cualquier zona del área de trabajo_

<div align="center">
  <img src="Imagenes/FiguraNo.2.23.PNG" width="700px">
</div>

_c. Para simular los tres tanques, debe repetir el trabajo, agregando dos tanques más._

<div align="center">
  <img src="Imagenes/FiguraNo.2.24.PNG" width="700px">
</div>

_d. Seleccionar la opción "Añadir Nudo Caudal"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.25.PNG" width="700px">
</div>

_d. Picar en la zona de trabajo, procurando simular de manera aproximada la ubicación del nodo según la imagen de guía._

<div align="center">
  <img src="Imagenes/FiguraNo.2.26.PNG" width="700px">
</div>

_e. Seleccionar la opción "Añadir tubería""._

<div align="center">
  <img src="Imagenes/FiguraNo.2.27.PNG" width="700px">
</div>

_e. Para agregar los segmentos de tuberías, siempre se debe seleccionar como primer punto el nodo o el tanque aguas arriba en el sistema y picar posteriormente el nudo o el tanque aguas abajo de dicho tramo_

<div align="center">
  <img src="Imagenes/FiguraNo.2.28.PNG" width="700px">
</div>

### Carga una imagen de fondo para el trazado (cargar imagen desde GoogleEarth) 

Una de las herramientas de EPANET más usadas y prácticas corresponde al cargue de imágenes de fondo, tomando como referencia una imagen con formato ".BPM". 

Para orientar al usuario a manera de ejemplo a continuación se presenta el procedimiento sugerido para cargar imágenes tipo ".BPM" usando como base una imagen tomada de Google Earth.

_a. Buscar y abrir el software previamente instalado_

<div align="center">
  <img src="Imagenes/FiguraNo.2.29.PNG" width="700px">
</div>


_b. Seleccionar la zona que desea tomar como referencia para el trazado de la red_

<div align="center">
  <img src="Imagenes/FiguraNo.2.30.PNG" width="700px">
</div>

_c. Ubicar adecuadamente la zona donde solicitará al software descargar la imagen, picar el botón "guardar imagen" el cual se guardará por defecto con formato ".jpg" o ".png"_

<div align="center">
  <img src="Imagenes/FiguraNo.2.31.PNG" width="700px">
</div>

<div align="center">
  <img src="Imagenes/FiguraNo.2.32.PNG" width="700px">
</div>

_d.Con el siguiente link convertir la imagen descargada de Google Earth y guardada en una carpeta del pc. Debe buscar el archivo en la ruta donde guardó el archivo e indicar que el archivo lo desea transformar a formato ".BPM"_ 

[Link de descarga para convertir el formato de una imagen a formato ".BPM"](https://convertio.co/es/download/3ef514d1b96e6cc159c006dea82a1738a67b94/)

<div align="center">
  <img src="Imagenes/FiguraNo.2.33.PNG" width="700px">
</div>

_e.Desde el EPANET, en la barra de herramientas Ver, seleccionar la opción "Mapa de Fondo" y seleccionar la subcategoría "Cargar"_ 

<div align="center">
  <img src="Imagenes/FiguraNo.2.35.PNG" width="700px">
</div>

_f. Buscar la ubicación del archivo y cargarlo al EPANET_ 

<div align="center">
  <img src="Imagenes/FiguraNo.2.37.PNG" width="700px">
</div>

_g. Iniciar con la creación de nodos, tanques y tuberías tal como se indicó en el primer apartado de esta actividad. El usuario puede apagar y encender la imagen de fondo para evaluar como está realizado el trazado_

<div align="center">
  <img src="Imagenes/FiguraNo.2.38.PNG" width="700px">
</div>

### Control de versiones

| Versión    | Descripción   | Autor                                      | Horas |
|------------|:--------------|--------------------------------------------|:-----:|
| 2022.01.12 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   1   |
| 2022.03.12 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   3   |
| 2022.04.12 | Versión No. 1 | [AndresOtalora92](https://github.com/AndresOtalora92)  |   4   |

_CursoEpanetBasico-Intermedio es de uso libre para fines académicos.

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [AndresOtalora92](https://github.com/AndresOtalora92?tab=repositories) en GitHub._


| [Anterior](../ModuloNo.2/Generalidades_EPANET.md) | [:house: Inicio](../../README.md) | [:beginner: Ayuda / Colabora] | [Siguiente](../ModuloNo.2/ImportardesdeCAD.md) |
|----------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------|---------------|

<div align="center"><a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBotonCertificado.png" alt="R.LTWB" width="260" border="0" /></a></div>

<div align="center"><a href="http://www.escuelaing.edu.co" target="_blank"><img src="../../.icons/Banner1.svg" alt="Support by" width="100%" border="0" /></a><sub><br>Este curso guía ha sido desarrollado con el apoyo de la Escuela Colombiana de Ingeniería - Julio Garavito. Encuentra más contenidos en https://github.com/uescuelaing</sub><br><br></div>