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

Un sistema de coordenadas geográficas es un sistema de referencia utilizado para ubicar puntos precisos en la superficie de la Tierra. Está basado en líneas imaginarias que dividen la Tierra en círculos y segmentos que permiten describir la posición de cualquier punto en términos de su latitud y longitud. Este tipo de sistema se utiliza para proporcionar una manera estándar y universal de expresar ubicaciones geográficas usando dos números: **latitud** y **longitud**. 

La latitud es la medida angular de la distancia al norte o al sur del ecuador de la Tierra. Se mide en grados, minutos y segundos, y varía desde 0° en el ecuador hasta 90° en los polos norte y sur. La latitud norte se representa con valores positivos y la latitud sur con valores negativos. Por su parte, la longitud es la medida angular de la distancia al este o al oeste del meridiano principal, que es el Meridiano de Greenwich (0° de longitud). También se mide en grados, minutos y segundos, y varía desde 0° hasta 180° hacia el este y hacia el oeste desde el meridiano principal.

<div align="center">
<br>
<img alt="MOHI" src=".img/SistemaCoordenadas.png" width="400px"><br>
<sub>Esta imagen muestra cómo se determinan la latitud y la longitud utilizando el sistema de grados decimales.</sub>[^2]<br> 
</div>

La forma teórica que convencionalmente se utiliza para definir la Tierra es el Geoide qué se define teóricamente a partir del nivel medio de los mares. Debido a su forma irregular y para la definición de una forma geométrica que pueda ser resuelta matemáticamente de forma simple se utilizan los conceptos de esfera y elipsoide.

- Sistema de coordenadas geográficas esféricas: se basa en una superficie esférica que aproxima la forma de la Tierra, y se usa para fines astronómicos o de navegación. Las coordenadas se expresan en grados sexagesimales o centesimales1.
- Sistema de coordenadas geográficas elipsoidales: se basa en una superficie elipsoidal que se ajusta mejor a la forma real de la Tierra, y se usa para fines geodésicos o cartográficos. Las coordenadas se expresan en grados decimales.

<div align="center">
<br>
<img alt="MOHI" src=".img/Geoide.jpg" width="350px"><br>
<sub>Relaciones geométricas entre la superficie topográfica de la Tierra, 
el geoide y el elipsoide, necesarias para una cartografía de precisión.</sub>[^1]<br> 
</div>

Existen varios sistemas de coordenadas geográficas que se utilizan en todo el mundo para representar ubicaciones en la Tierra. En la siguiente tabla se presentan algunos los más comunes.

|                            Nombre                            | Descripción                                                                                                                                                                                                                                                                                                                                                                     |
|:------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              WGS84 (World Geodetic System 1984)              | Este es el sistema de referencia global utilizado por el Sistema de Posicionamiento Global (GPS) y muchos otros sistemas de navegación por satélite. Es ampliamente utilizado en aplicaciones de cartografía y geolocalización.                                                                                                                                                 |
|              NAD83 (North American Datum 1983)               | Este sistema es utilizado en América del Norte y es la base para muchos sistemas de referencia de coordenadas utilizados en los Estados Unidos y Canadá.                                                                                                                                                                                                                        |
| SIRGAS (Sistema de Referencia Geocéntrico para las Américas) | Utilizado en América Latina para la representación de ubicaciones geográficas.                                                                                                                                                                                                                                                                                                  |
|                  ED50 (European Datum 1950)                  | Utilizado en gran parte de Europa antes de la adopción del WGS84. Aunque ha sido en gran medida reemplazado por el WGS84, todavía puede encontrarse en algunos mapas y datos antiguos.                                                                                                                                                                                          |
|                             UTM                              | Es un sistema de coordenadas rectangulares que se utiliza para el mapeo. El sistema UTM se divide en 60 zonas, cada una de las cuales cubre 6 grados de longitud. Cada zona tiene un código de dos letras, que se basa en su ubicación geográfica. El sistema UTM se utiliza para una variedad de propósitos, como la navegación, la cartografía y la investigación científica. |

### Códigos EPSG

Las iniciales **EPSG** representan "European Petroleum Survey Group", que era un grupo de trabajo que originalmente se creó en Europa en la década de 1980 para desarrollar estándares y recomendaciones técnicas para la industria petrolera y del gas. Uno de los logros más notables del grupo fue la creación de un conjunto de códigos numéricos únicos llamados "Códigos EPSG" que se utilizan para identificar sistemas de referencia de coordenadas y transformaciones geodésicas en aplicaciones de Sistemas de Información Geográfica (SIG) y otros sistemas relacionados.

Estos códigos, conocidos como "Códigos EPSG" o "ID EPSG", proporcionan una forma estándar y global de identificar sistemas de coordenadas geográficas, sistemas de proyección cartográfica y transformaciones entre diferentes sistemas de referencia espacial. Cada sistema de coordenadas geográficas o proyección cartográfica tiene un código EPSG único asignado a él.

Aunque el grupo original EPSG ya no está activo, sus estándares y códigos siguen siendo ampliamente utilizados en la industria de los SIG y la cartografía. Los códigos EPSG son utilizados por muchos software y herramientas SIG para asegurarse de que los sistemas de coordenadas y las transformaciones geodésicas se interpreten correctamente en diferentes aplicaciones y plataformas. En la siguiente tabla se presentan algunos de los códigos EPSG más conocidos que representan sistemas de coordenadas geográficas y proyecciones cartográficas utilizadas en todo el mundo.

| Código EPSG | Sistema de Coordenadas / Proyección     | Descripción                                                                                            |
|:-----------:|-----------------------------------------|--------------------------------------------------------------------------------------------------------|
|    4326     | WGS 84 (Latitud y Longitud)             | Sistema global de coordenadas geográficas basado en el WGS 84.                                         |
|    3857     | WGS 84 / Pseudo-Mercator (Web Mercator) | Proyección utilizada en mapas web y aplicaciones de navegación en línea.                               |
|    3395     | WGS 84 / World Mercator                 | Proyección Mercator modificada para representar áreas polares con menos distorsión.                    |
|    32633    | WGS 84 / UTM zona 33                    | Sistema de coordenadas UTM para la zona 33 en Europa.                                                  |
|    26912    | NAD83 / UTM zona 12                     | Sistema de coordenadas UTM para la zona 12 en América del Norte.                                       |
|    23030    | ED50 / UTM zona 30                      | Sistema de coordenadas UTM para la zona 30 basado en el ED50.                                          |
|    25832    | ETRS89 / UTM zona 32                    | Sistema de coordenadas UTM para la zona 32 en Europa basado en el ETRS89.                              |
|    54009    | Mollweide                               | Proyección cartográfica utilizada para representar áreas extensas con distorsiones de forma reducidas. |
|   102013    | Albers Equal Area Conic                 | Proyección cónica utilizada para representar áreas con distorsiones de área mínimas.                   |
|    27700    | OSGB 1936 / British National Grid       | Sistema de coordenadas utilizado en el Reino Unido.                                                    |
|    32718    | WGS 84 / UTM zona 18 sur                | Sistema de coordenadas UTM para la zona 18 en el hemisferio sur.                                       |

### Sistema de proyección de coordenadas

Un sistema de proyección de coordenadas es un conjunto de reglas y fórmulas matemáticas que se utilizan para representar la superficie curva de la Tierra en un plano bidimensional, como un mapa. Debido a que la Tierra es tridimensional y curva, es necesario aplicar una proyección para representar su forma en un mapa plano, lo que puede resultar en distorsiones en áreas, formas, distancias o direcciones. Los sistemas de proyección son esenciales para la cartografía y la representación precisa de la información geográfica en un formato utilizable. Existen muchas proyecciones diferentes, cada una con sus propias características y aplicaciones específicas. Algunos tipos comunes de sistemas de proyección de coordenadas incluyen:

- Proyecciones cilíndricas: Estas proyecciones proyectan puntos desde la superficie de la Tierra sobre un cilindro imaginario que rodea el globo. Ejemplos incluyen la proyección de Mercator y la proyección de Lambert.

- Proyecciones cónicas: En estas proyecciones, los puntos se proyectan desde la superficie de la Tierra sobre un cono imaginario que se coloca sobre el globo. Ejemplos incluyen la proyección de Albers y la proyección de Lambert cónica conforme.

- Proyecciones pseudocilíndricas: Estas proyecciones buscan un equilibrio entre la distorsión de forma y área. Ejemplos incluyen la proyección de Mollweide y la proyección de Robinson.

No existe una proyección perfecta que sea adecuada para todas las situaciones, por lo que la elección depende de las necesidades específicas y los compromisos entre diferentes tipos de distorsiones.

### Sistema de coordenadas en Colombia

Mediante resolución No. 068 de 2005 se adoptó como único datum oficial de Colombia el Marco Geocéntrico Nacional de Referencia - MAGNA, que por estar referida a SIRGAS, se denomina convencionalmente **MAGNA-SRIGAS**. El Instituto Geográfico Agustín Codazzi (IGAC), entidad gubernamental encargada de los sistemas geodésicos nacionales de referencia, promueve la adopción de MAGNA-SIRGAS como sistema de referencia oficial del país, en reemplazo del Datum BOGOTÁ, definido en 1941. **MAGNA-SIRGAS** garantiza la compatibilidad de las coordenadas colombianas con las técnicas espaciales de posicionamiento, por ejemplo los sistemas GNSS (Global Navigation Satellite Systems), y con conjuntos internacionales de datos georreferenciados. Los parámetros del sistea de coordenadas se presentan en la siguiente tabla.

<div align="center">

| Parámetro                 | Valor                                           |
|---------------------------|-------------------------------------------------|
| Código EPSG               | 4686                                            |
| Datum geodésico*          | MAGNA-SIRGAS*                                   |
| Elipsoide                 | GRS 1980                                        |
| Meridiano Principal       | Greenwich 0,000000000000000000 Grados decimales |
| Semieje mayor (a), metros | 6378137                                         | 
| Semieje menor (b), metros | 6356752.314                                     |
| ITRF                      | 1994, Época 1995.4                              |
</div>

La utilización del sistema **MAGNA-SIRGAS** está directamente relacionada con la definición de una superficie de referencia vertical (geoide) que permita obtener alturas clásicas (referidas al nivel medio del mar) a partir de información GPS. El Geoide en Colombia se ha determinado mediante la técnica remove/restore, la cual permite relacionar las características regionales (longitudes de onda larga) del campo de gravedad, expresadas en un Modelo Geopotencial Global (MGG), y sus detalles (longitudes de onda corta), obtenidos a través de la evaluación local del modelo físico matemático de Strokes (o Molodensky). Con ayuda de la herramienta QGIS podemos visualizar la información del sistema de coordenadas.

<div align="center">
<br>
<img alt="MOHI" src=".img/MAGNA-SIRGAS.jpg" width="1000px"><br>
</div>




## Tipos de datos


### Control de versiones

| Versión | Descripción                                                    |                    Autor                    | Horas |
|:-------:|:---------------------------------------------------------------|:-------------------------------------------:|:-----:|
| 2023.08 | Versión inicial, definición de estructura general y contenido. | [juanrodace](https://github.com/juanrodace) |  1.0  |
| 2023.08 | Inclusión de conceptos, esquemas y ejemplos.                   | [juanrodace](https://github.com/juanrodace) |  3.0  |

| [:arrow_backward:Anterior](Conceptos.md) | [:house: Inicio](../../Readme.md) | [:beginner: Ayuda](https://github.com/juanrodace/MOHI/discussions) | [Siguiente:arrow_forward:](QGIS.md) |
|------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-------------------------------------|

_MOHI es de uso libre para fines académicos, conoce nuestra licencia, cláusulas, condiciones de uso y como referenciar los contenidos publicados en este repositorio, dando [clic aquí](../../License.md)._

_¡Encontraste útil este repositorio!, apoya su difusión marcando este repositorio con una ⭐ o síguenos dando clic en el botón Follow de [juanrodace](https://github.com/juanrodace) en GitHub._ 

[^1]: http://www.albireotopografia.es/wp-content/uploads/2015/01/Topografia-geoide-y-elipsoide.jpg
[^2]: Preparation for Orienteering at the Priory. Geospatial Field Methods Couse. 2014.