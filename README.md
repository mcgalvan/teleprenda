# teleprenda
Mostra dun sistema loxístico para o sector textil.
Consiste nun traballo para a asignatura de Sectores de Negocio impartida na Facultade de Informática, na UDC.

El proyecto esta dividido en tres partes, con tres grupos asignados a ellas respectivamente, que son: Materias primas, Ropa, y Transporte.

Grupo de Transporte (Castellano):
Este grupo se encarga del diseño de la base de datos que gestiona el
transporte de los productos de esta empresa. 

A continuación se muestran las características que el sistema de transporte debe cumplir:

Cada transporte es realizado por un conductor, que transporta un conjunto de ropas y/o materias primas, identificadas por un número de pedido, con fecha y tiempo de salida desde el centro logístico, con fechas y horas de llegada y salida de las fabricas, y con identificación de la actividad (recogida de ropa, envio de materias primas, devolución de ropa defectuosa, etc).
Se necesitan informes para la actividad de todos los transportes, informes por cada conductor, por cada número de pedido, etc.

A partir de estas características se diseñó la base de datos que se puede ver en la imagen adjunta.

Como podemos observar, tenemos una entidad conductor en la que se guarda la información relacionada con los diferentes conductores que trabajan para la empresa( nombre, número de telefono, fecha de contratación,...)
Tenemos una entidad vehículo, para guardar la información relacionada con los vehículos que usan los conductores para los distintos transportes, como la matrícula del vehículo o el modelo.
Una parte importante de la base de datos es la entidad transporte, en la que guardamos la información relacionada con los diferentes envíos que se realizan en la empresa. En esta entidad guardamos datos como el número del pedido que se transporta, origen, destino, etc. En esta entidad se especifica el tipo de transporte, el cual determina la información que guardamos del origen y destino del mismo, como por ejemplo las ids de las fábricas, o de las materias primas.
Por último, tenemos la entidad albarán para guardar la información tanto de salida como de llegada, como puede ser la cantidad transportada y la firma de confirmación.

Con esta base de datos, se cumplen todas las caracteristicas necesarias para la gestion de la informacion de los transportes de la empresa, así como la obtención de los informes de actividad de los mismos.
Además, también se diseñaron formularios para la inclusión de información en la base de datos de manera fácil y cómoda.