<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="J.HRAS" width="100%" border="0" /></a></div>

# QGIS. Herramientas de Geoprocesamiento
Keywords: `GIS` `Software` `QGIS` `Tools` `Geoprocessing`

<div align="center">
<br>
<img alt="MOHI" src="../../Contenido/.icons/MOHI.svg" width="200px">
<br><b>Universidad Escuela Colombiana de Ingeniería Julio Garavito</b><br> 
Juan David Rodríguez <a href="https://github.com/juanrodace/"><i>(ver GitHub)</i></a><br>
Profesor del Centro de Estudios Hidráulicos<br>
</div>

## Funciones espaciales o de geoprocesamiento

Una función espacial o de geoprocesamiento en un SIG es una operación o proceso que se aplica a datos geoespaciales para realizar análisis, manipulación o transformación de esos datos. Estas herramientas y funciones permiten a los usuarios realizar una variedad de tareas relacionadas con la gestión, análisis y visualización de datos geográficos. A continuación presento algunas de las herramientas y funciones espaciales más utilizadas en QGIS.

### Selección, identificación y medición

 Permite seleccionar entidades en capas vectoriales basándose en diferentes criterios, como la ubicación espacial o sus atributos. Así mismo, esas funciones permiten obtener información detallada sobre una entidad específica en una capa seleccionada. Igualmente, algunas funciones, permiten medir distancias, áreas, perímetros y ángulos en el mapa.

<div align="center"><br>
<img alt="MOHI" src=".img/QGIS_Identify2.png" width="650px"><br>
<img alt="MOHI" src=".img/QGIS_Identify.png" width="650px"><br>
<sub>Selección e identificación en QGIS.</sub>
</div>

> Existen diferentes plugins que pueden ser instalados en QGIS y permiten la visualización de los datos y atributos por medio de gráficas. <br><br> Por ejemplo el plugin [**DataPloty**](https://github.com/ghtmtt/DataPlotly) sirve para crear gráficos interactivos con la biblioteca plotly en QGIS, puedes usar capas y tablas del proyecto como fuentes de datos y vincular el mapa con el gráfico, también puedes filtrar los objetos en el gráfico por el estado de selección o la visibilidad en el mapa principal. <br><br> Otro ejemplo es [**Line Profile**](https://github.com/wiscsims/line_profile) que permite crear gráficas de perfil a partir de capas vectoriales o archivos raster.

### Edición y digitalización

Crear, editar y modificar entidades geoespaciales, como puntos, líneas y polígonos, en una capa vectorial. Dentro de esta funcionalidad, se tienen varias herramientas de edición como las listadas a continuación:

- Recortar: Permite recortar entidades vectoriales para ajustarlas a una ubicación o límite específico.
- Unión: Combina dos o más capas vectoriales en función de un atributo común.
- Buffer: Crea zonas de influencia alrededor de entidades, útil para análisis de proximidad y disolución espacial.
- Intersección: Encuentra las áreas donde las entidades de dos capas vectoriales se cruzan o se superponen.
- Disolución: Combina entidades que comparten un atributo común en una capa vectorial.
- Fusionar Geometrías: Combina geometrías de entidades vecinas en una sola entidad en una capa vectorial.

### Análisis espacial

### Estadísticas Espaciales

### Geoprocesamiento de imágenes




