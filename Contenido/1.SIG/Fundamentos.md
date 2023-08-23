<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-hidraulicos/" target="_blank"><img src="https://github.com/rcfdtools/R.TeachingResearchGuide/blob/main/CaseUse/.icons/IconCEHBanner.jpg" alt="J.HRAS" width="100%" border="0" /></a></div>

# Fundamentales Generales SIG 
Keywords: `SIG` `GIS` `Georeferencing` `Coordinate systems` `Data types` `Geographic`

<div align="center">
<br>
<img alt="MOHI" src="../../Contenido/.icons/MOHI.svg" width="200px">
<br><b>Universidad Escuela Colombiana de Ingeniería Julio Garavito</b><br> 
Juan David Rodríguez <a href="https://github.com/juanrodace/"><i>(ver GitHub)</i></a><br>
Profesor del Centro de Estudios Hidráulicos<br>
</div>

## Georreferenciación

La georreferenciación es el proceso de asignar una ubicación espacial a una **entidad cartográfica** (incluyendo sus atributos), usando un sistema de coordenadas y un datum específicos. En otras palabras, es la técnica utilizada para vincular datos no geoespaciales con coordenadas geográficas para que puedan ser representados y analizados en un contexto espacial. Por ejemplo, se puede georreferenciar una imagen satelital, un mapa antiguo, un punto de interés, entre otros. 

La georreferenciación es un componente fundamental de la capacidad de los Sistemas de Información Geográfica (SIG) y otras herramientas que trabajan con datos espaciales, ya que permite la integración y el análisis efectivo de datos en un contexto geográfico.

Algunos ejemplos de cómo se aplica la georreferenciación incluyen:

- Cartografía digital: Convertir mapas físicos o imágenes en mapas digitales georreferenciados para su uso en sistemas de información geográfica (SIG).
- Fotografía aérea o satelital: Asociar imágenes capturadas desde el aire o desde satélites con coordenadas geográficas, lo que permite la superposición y análisis de datos en el contexto geoespacial.
- Levantamientos topográficos: Asignar coordenadas a puntos de elevación, líneas de contorno y otros elementos en un terreno para crear modelos digitales de elevación.
- Análisis de datos de campo: Registrar ubicaciones precisas donde se han tomado mediciones o recopilado datos para su análisis posterior en un contexto geográfico.
- Sistemas de navegación: Determinar la posición y la dirección de un vehículo o una persona en tiempo real utilizando señales GPS (Sistema de Posicionamiento Global).

> Una *entidad cartográfica* es un elemento que representa una característica geográfica en un mapa o en un SIG. Por ejemplo, un punto, una línea, un polígono, un píxel, etc. Cada entidad cartográfica tiene una geometría (forma y ubicación) y unos atributos (información descriptiva) asociados.

### Sistema de coordenadas geográficas

La forma teórica que convencionalmente se utiliza para definir la Tierra es el Geoide qué se define teóricamente a partir del nivel medio de los mares. Debido a su forma irregular y para la definición de una forma geométrica que pueda ser resuelta matemáticamente de forma simple se utilizan los conceptos de esfera y elipsoide.
 
### Sistema de proyección de coordenadas

Un sistema de proyección de coordenadas es un conjunto de reglas y fórmulas matemáticas que se utilizan para representar la superficie curva de la Tierra en un plano bidimensional, como un mapa. Debido a que la Tierra es tridimensional y curva, es necesario aplicar una proyección para representar su forma en un mapa plano, lo que puede resultar en distorsiones en áreas, formas, distancias o direcciones. Los sistemas de proyección son esenciales para la cartografía y la representación precisa de la información geográfica en un formato utilizable. Existen muchas proyecciones diferentes, cada una con sus propias características y aplicaciones específicas. Algunos tipos comunes de sistemas de proyección de coordenadas incluyen:

- Proyecciones cilíndricas: Estas proyecciones proyectan puntos desde la superficie de la Tierra sobre un cilindro imaginario que rodea el globo. Ejemplos incluyen la proyección de Mercator y la proyección de Lambert.

- Proyecciones cónicas: En estas proyecciones, los puntos se proyectan desde la superficie de la Tierra sobre un cono imaginario que se coloca sobre el globo. Ejemplos incluyen la proyección de Albers y la proyección de Lambert cónica conforme.

- Proyecciones pseudocilíndricas: Estas proyecciones buscan un equilibrio entre la distorsión de forma y área. Ejemplos incluyen la proyección de Mollweide y la proyección de Robinson.

No existe una proyección perfecta que sea adecuada para todas las situaciones, por lo que la elección depende de las necesidades específicas y los compromisos entre diferentes tipos de distorsiones.

## Tipos de datos