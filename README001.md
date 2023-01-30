# OBTENCIÓN AGROINDICADORES CLIMÁTICOS DIARIOS ⚙️

_En esta API se detallará el proceso de la obtención de los datos, dependiendo de los proveedores (de los cuales se especificará más adelante),
ya que en base a esto es que se procesa la información obtenida, dependiendo de los sensores y proveedores, ya que se tendrán mas o menos datos, las mediciones que se hacen,
estan basadas
en minutos, ya que cada medición se hace en un tiempo diferente desde los 15 minutos hasta los 60, dicho esto es relevante mencionar que existen 6 tipos de sensores,
los cuales nos sirven para obtener estas midiciones, los cuales son: Temperatura, Radiación, Viento, Humedad Relativa, Punto Rocío y la Eto Evotranspiración,
además de esto se presentará la generación de agroindicadores climaticos y los tipos de estos, junto con una brevre explicación de su uso, tiempo en que se generan y sus funciones._

## Proveedores Climáticos (logo)

_Las estaciones climáticas están divididas en 2 proveedores, los cuales son, Morpho: la cual es una empresa especializada en soluciones de monitoreo y telemetría, enfocada en facilitar la introducción de tecnología tanto en la industria como las instituciones de investigación y desarrollo. Genera soluciones integrales desde la evaluación, instalación y la ejecución de los proyectos. 
y Vilab: cuya finalidad es proporcionar estudios y análisis en línea de nuestros cultivos a partir de imágenes satelitales, estaciones meteorológicas, sensores y otras fuentes de información.
los cuales a su vez posen un tipo de " plataformas que nos sirven comoVISUALIZADR DE LA INFORMACIÓN" que son AGViewer y Privada/Publica respectivamente.

### Link Documentación (logo)
#### Morpho: 
panel de administración de AGViewer: http://agviewer.com/
usuario: agricolagarces
contraseña: user12345
Endpoint de obtención de data climática
Link API y documentación con swagger: http://agviewer.com/api/v1/
Data Climática de un huerto: http://agviewer.com/api/v1/device/data/?stations=6018,6015&start=2021-01-01&end=2021-02-28

#### Vilab:
https://api.vilab.cl
Endpoint huertos Vilab: https://api.vilab.cl/index.php/api/predios/key/7df5d2f73a99ed699a1955c87050ea7d
key:7df5d2f73a99ed699a1955c87050ea7d


### Mediciones (logo)

_Para contribuir al desarrollo de la API, es imperativo que tengas las siguientes herramientas instaladas en tu equipo:_

Las mediciones, provenientes de las estaciones climáicas, como se mencionó antes se hacen en base al tiempo, se tienen cada 15, 30, 45 y 60 minutos, estas, se hacen mediante una variedad de sensores, las cuales
dependen del proveedor de quien las hace, ya que como se dice anteriormente, los proveedores nos la ofrecen en diferente cantidad, cada proveedor
posee una cantidad diferente de mediciones que nos ofrece, en el caso de Morpho, en los sensores de temperatura y humedad relativa, nos ofrece el máximo, mínimo y el promedio de estas
sin embargo esto no pasa en Vilab, ya que en todas las mediciones, solamente nos ofrece el AVG (promedio) como valor final._

### Agroindicadores Climáticos (logo)
Gracias a los datos provenientes de las mediciones de los huertos/proveedores, es posible obtener agroindicadores, los cuales nos ayudan para una mayor comprensión y un 
análisis más completo del huerto y de lo que está sucediendo dentro de el, ya que como es bien sabido, los disntitos huertos, al poseer una vasta cantidad de hectareas, poseen unos
microclimas propios que no necesariamente tienen que ser los mismos entre los demas huertos. Los agroindicadores que se obtienen despues de procesar las mediciones son los de Porciones frio, Horas frio y dias grados, los cuales se explicarán
con maypr detalle para una mejor comprensión de este:

#### Porciones Frio: 
Se basa en el concepto de “porción de frío”, introducido por Fishman, que corresponde a una exposición de 6 °C por 24 – 28 horas. Se dice que el frío ha sido fijado por la planta y no es revertido por altas T° posteriores. 
Se calcula desde la caída del 50% de las hojas, lo que viene a ser a principios de noviembre, hasta unos días antes del desborre de yemas, normalmente a mitad de febrero en zonas templadas (+ 15 d si se trata de zonas frías y -15 d en caso de zonas cálidas). En nuestro caso los datos
obtenidos por las porciones frio se nos muestran cada hora, es decir, en un dia tenemos 24 registros por huerto y todo esto se conoce como el consolidado diario

#### Horas Frio: 
Algunos tipos de arboles necesitan de una acumulación de frío para salir del estado de reposo, las cantidades de frío requeridas varían por especie y variedad. ,y esta estrategia de acumular horas frio en realidad es
un mecanismo de defensa para evitar la brotación durante el periodo invernal, con lo cual los brotes jóvenes quedarían indefensos a las posteriores heladas 
de la estación del año. Las horas frio se refiere a la cantidad de tiempo (horas) en que la planta ha estado
por debajo de una temperatura de 7 °C. Las horas frío representan una hora de exposición a temperaturas adecuadas para que la planta 
salga del estado de dormancia. El evento conocido como dormancia o latencia y es un periodo de reposo que comienza cuando los frutales de hoja caduca tiran sus hojas como una estrategia de sobrevivencia a las condiciones adversas del clima.
En este agroindicador, al igual que Porciones Frío se obtiene data por hora, 24 datos en un día
   

#### Dias Grados: 
Días Grado corresponde a la diferencia de la temperatura media diaria por sobre o debajo de un umbral determinado, que puede variar entre 5 y 10°C, según cultivo. Los dias grados a diferencia de los otros dos indicadores, se obtiene un dato por dia




## identificación Huertos (logo)

|  Orchard |  Id |
| ------------ | ------------ |
|Almahue | 0020361D|
|Bodega	| 00203D2B|
|Ceresur | No hay estación
|Chumpirro | 00203D28|
|El_Condor | 002035D4|
|El_Descanso | 00203D27|
|El_Espino | 00203F32|
|El_Parque | 00203D29|
|El_Recurso | 00203D29|
|El_Retiro | 00203D26|
|El_Rosario | 00203E78|
|Entre_Rios | 00203E6F|
|La_Esperanza | 00205018|
|La_Morera | 00203B04|
|La_Robleria | 002035D5|
|Las_Cabras | 00205016|
|Las_Vertientes | z6-12950|
|Los_Encinos | 00203581|
|Los_Maitenes | z6-10298|
|Los_Toldos | No hay estación|
|Mallorca | 00203E70|
|Panquehue | 00205015|
|Puente_Negro | 002035D7|
|Rio_Claro | 00203E6E|
|San_Hernan | 0020500D|
|Santa_Margarita | 002035D6|
|Santa_Monica | 00203580|
