# Resumen Capitulo 23

### BBA Tools
Todos los principales productos de DBMS proporcionan un sistema de administración de bases de datos completo y funcional que se puede utilizar de forma inmediata para almacenar y administrar datos.  La administración y el mantenimiento de las aplicaciones de la base de datos lleva mucho tiempo si usa solo las características estándar del DBMS. Afortunadamente, muchas herramientas de DBA que mejoran la funcionalidad de los sistemas de gestión de bases de datos relacionales están disponibles en proveedores externos.

### Tipos y beneficios de las herramientas DBA
Una herramienta DBA reduce la cantidad de tiempo, esfuerzo y errores humanos involucrados en el mantenimiento de sistemas y aplicaciones de bases de datos eficientes. Dichas herramientas alivian la carga administrativa y reducen la posibilidad de error.

#### Modelado y diseño de datos
Las herramientas de diseño y modelado de bases de datos proporcionan un medio consistente y coherente para crear modelos de datos conceptuales, lógicos y transformarlos en diseños de bases de datos físicas. Estas herramientas no tienen que ser exclusivas de una base de datos. Las herramientas específicamente compatibles con su DBMS pueden reducir significativamente el tiempo de desarrollo.

Al elegir una herramienta de diseño y modelado, busque una que pueda: 

    * Apoyar las tareas estándar asociadas con el modelado de datos lógicos, como el diagramación y la normalización de la relación entre entidades.
    * Crea un modelo de datos físicos orientado a cada una de sus plataformas DBMS de destino.
    * Proporciona un sistema experto para verificar la precisión del modelo de datos físicos y sugerir soluciones alternativas.
    * Hace una referencia cruzada del modelo lógico con el modelo físico.
    * Genere DDL estándar automáticamente para implementar completamente la base de datos definida en el modelo de datos físicos.
    * Interfaz con herramientas de desarrollo de aplicaciones y productos de repositorio utilizados dentro de la organización.

#### Herramientas de gestión de cambios
Estas herramientas optimizan y automatizan múltiples tareas de gestión de cambios, incluida la alteración de la base de datos, la comparación de la base de datos, la autorización de seguridad, el seguimiento de auditorías, las consultas de catálogo, la gestión del espacio y el manejo de la integridad referencial.
La declaración ALTER está funcionalmente paralizada en la mayoría de los productos DBMS

Las herramientas de gestión de cambios deben poder:
    
    * Mantener las tablas fácilmente sin requerir manualmente que el DBA codifique DDL.
    * Retener o volver a aplicar todos los objetos dependientes, autorizaciones y datos afectados por ALTER si se requiere una caída. 
    * Navegar jerárquicamente de un objeto a otro.
    * Proporcionar modificaciones basadas en GUI que muestren las definiciones de "antes" y "después" de los objetos antes de que se apliquen los cambios.
    * Cambios en un grupo que se puede ejecutar en primer plano o en segundo plano.
    * Proporcionar la capacidad de monitorear los cambios a medida que se aplican.
    * Asegurarse de que las modificaciones solicitadas no violen ninguna regla DDL.

El impacto de los cambios se puede examinar antes de implementar cualquier cambio.

#### Database Comparison Tools
Una herramienta de comparación de bases de datos permite al DBA comparar una base de datos con otra en términos de sus objetos y estructuras de base de datos. Dichas herramientas identificarán las diferencias y generarán automáticamente el DDL para que las bases de datos sean las mismas, desde una perspectiva estructural, no desde una perspectiva de contenido de datos. La herramienta de comparación de bases de datos debe permitir que el DBA realice los siguientes tipos de comparaciones:

    * Una base de datos en vivo a otra base de datos en vivo (en el mismo servidor u otro servidor).  
    * Una base de datos en vivo a un archivo de script DDL .
    * Un archivo de script DDL a otro archivo de script DDL.

 Sin embargo, algunos proveedores ofrecen herramientas que pueden comparar el contenido de una tabla con el contenido de otra. Dichas herramientas suelen ser útiles durante las pruebas y depuración de programas de aplicación.

 #### Database Object Migration Tools
Las herramientas de migración facilitan la migración rápida de objetos de base de datos.
Una herramienta de migración puede reducir el tiempo requerido por los administradores de bases de datos para mover bases de datos de un entorno a otro. Una respuesta más rápida da como resultado una respuesta más rápida a las necesidades del usuario, lo que aumenta la eficiencia de su negocio.

#### Referential IntegrityTools
La integridad referencial (RI) es utilizada por las bases de datos relacionales para garantizar la validez de la clave primaria a las relaciones de clave externa.

Las herramientas de RI eliminan esta dificultad: 
    
    *  Análisis de datos para violaciones de restricciones de integridad referencial administradas por el sistema y por el usuario
    * Ejecución más rápida que la instalación o utilidad de comprobación de integridad proporcionada por DBMS 
    * Permitir que se admitan tipos adicionales de RI; por ejemplo, analizando las claves primarias para las que no existen claves externas y eliminando la fila de la clave primaria (procesamiento pendiente DELETE).

#### Catalog 
El catálogo del sistema o diccionario de datos contiene una gran cantidad de información esencial para el funcionamiento del DBMS. La información sobre todos los objetos de la base de datos, la autoridad y la recuperación se almacena y mantiene en el catálogo del sistema. 

#### Catalog Query and Analysis Tools
 Estas herramientas se denominan herramientas de visibilidad del catálogo porque facilitan el acceso a la información almacenada en el catálogo del sistema. La característica básica común a todas las herramientas de catálogo es la capacidad de solicitar información de catálogo utilizando una interfaz GUI (o panel) sin utilizar sentencias SQL.

 #### Table Editors
Una herramienta de edición de tablas puede reducir el tiempo necesario para realizar alteraciones de datos simples al proporcionar la capacidad de edición de pantalla completa para las tablas de la base de datos. El usuario especifica la tabla a editar y se inicia un editor de tablas. Los datos se presentan al usuario como una serie de filas, con las columnas separadas por espacios. Una línea de encabezado indica los nombres de columna. Los datos se pueden desplazar hacia arriba y hacia abajo, así como a izquierda y derecha. Para cambiar los datos, el usuario simplemente escribe sobre los datos actuales. Puede reducir el tiempo necesario para realizar alteraciones de datos simples.

### Performance Management
Las herramientas de gestión del rendimiento ayudan al DBA a medir la capacidad de respuesta y la eficiencia de las consultas SQL, las estructuras de la base de datos y los parámetros del sistema. Dichas herramientas se ejecutan en segundo plano para capturar estadísticas de rendimiento de la base de datos y alertar al DBA cuando se producen problemas. Las herramientas de rendimiento avanzadas pueden tomar medidas proactivas para corregir los problemas a medida que ocurren.
Para ofrecer rendimiento, el DBA debe poder monitorear el sistema, la base de datos y la aplicación.

#### System Performance Tools
Las herramientas de rendimiento del sistema examinan el servidor de la base de datos, su configuración y uso. La herramienta mas utilizada es el monitor de rendimiento.
Algunas herramientas de rendimiento del sistema se centran en un componente específico del DBMS, como el caché de datos.

#### Database Performance Tool
Son herramientas de análisis de bases de datos que pueden monitorear de manera proactiva y automática su entorno de base de datos. Estas herramientas de análisis de bases de datos.

#### Application Performance Tools
Las herramientas de análisis SQL simplifican en gran medida este proceso al automatizar las partes principales del proceso de revisión de código. Revisan que el código SQL escrito en la aplicación sea el optimo. Estas herramientas generalmente capturan información detallada sobre los programas a medida que se ejecutan y proporcionan informes que especifican qué áreas del código consumen la mayor cantidad de recursos.

#### End-to-End Performance Tools
Son herramientas monitoreo de rendimiento de extremo a extremo que rastrean una solicitud de aplicación desde el inicio hasta la finalización. Estas soluciones proporcionan una visibilidad mejorada específicamente en el rendimiento de las aplicaciones, lo que brinda a las organizaciones el poder de comprender cuándo y por qué el rendimiento se ha degradado, y la información necesaria para mejorar los asuntos de una manera priorizada para las empresas. Las herramientas de monitoreo de rendimiento de extremo a extremo rastrean las solicitudes de aplicaciones desde el inicio hasta la finalización.

### Backup and Recovery
Son herramientas que pueden hacer respaldo y recuperación de alta velocidad, pueden hacer copias de seguridad de bases de datos u objetos de bases de datos completos utilizando técnicas de enmascaramiento y comodines.
La herramienta de recuperación basada en registros se puede usar para examinar el registro y producir SQL inverso, como se discutió en el Capítulo 15. Por ejemplo, suponga que el DBA emitió una declaración DELETE por error. Usando la herramienta de recuperación basada en el registro, el DBA ingresaría el nombre del programa y el tiempo de ejecución. La herramienta examinaría el registro, buscaría ELIMINAR y crearía instrucciones INSERTAR para reproducir los datos eliminados. 

### Utilidades de Base De Datos
Son programas simples, sin lujos, que son conocidos por su bajo rendimiento, especialmente en tablas muy grandes. Sin embargo, estas utilidades son necesarias para completar, administrar y organizar sus bases de datos. Las utilidades típicas que se proporcionan son LOAD, UNLOAD, REORG, BACKUP y RECOVER, así como las utilidades para la verificación de integridad. Las herramientas de terceros son mucha mas rápidas.

#### Utility Management Tools
Este tipo de herramienta proporciona soporte administrativo para la creación y ejecución de secuencias de trabajos de utilidad de base de datos.

### Protección de datos, gobierno, riesgo y herramientas de cumplimiento
Es una propuesta de negocio, y la mayoría de las soluciones en esta categoría no son relevantes para los administradores de bases. 

#### Auditoria  
Ayuda en el seguimiento de control, definición de datos y la integridad de los datos en el entorno de base de datos. Proporcionan la capacidad de auditoría a un nivel más granular y
simplifican la capacidad de informar sobre las pistas de auditoría. Debido al volumen potencial de los cambios realizados en los datos de base de datos, una instalación de auditoría útil debe permitir la creación selectiva de los registros de auditoría para reducir al mínimo los problemas de rendimiento y de almacenamiento. 

Estos datos pueden ser :

    • Todos los accesos por usuarios de alto nivel(como DBADMIN y SYSADMIN)
    • errores de autorización
    • sentencias GRANT y REVOKE de SQL
    • DDL emitidos
    • DML emitieron
    • peticiones SQL BIND o nuevas invocaciones de programa
    • ejecuciones de servicios públicos

#### Herramientas de acceso de tendencias
Las herramientas de tendencias generalmente dependen de la tecnología de auditoría de bases de datos para observar los accesos a las bases de datos y establecer tendencias y patrones. Dichas herramientas son útiles para identificar y prohibir el comportamiento fuera de la norma para detener proactivamente los ataques a la base de datos.

#### Herramientas de perfil de datos
Perfilar sus datos es una metodología para obtener información sobre los datos de su empresa y refinar sus procesos para mejorar la calidad de los datos. Se utiliza una herramienta de perfil de datos para descubrir anomalías en la estructura, los datos y las relaciones en sus datos. Las técnicas de creación de perfiles lo ayudan a descubrir instancias de datos inadecuados donde los datos no coinciden con la definición de metadatos, los patrones no coinciden, los valores son inexactos y se producen datos redundantes.

#### Herramientas de enmascaramiento de datos
El enmascaramiento de datos es una categoría adicional de solución de protección de datos que se puede utilizar para ofuscar(OCULTAR) valores reales en la base de datos.

#### Herramientas de seguridad
La seguridad de la base de datos generalmente se proporciona de forma interna a la base de datos mediante el uso de sentencias SQL GRANT y REVOKE, que otorgan autorización explícita e implícitamente a los usuarios de la base de datos. 
Una base de datos de seguridad add-on herramienta normalmente analiza los efectos de un REVOKE.

### Almacenamiento de datos, análisis y Business Intelligence

#### Herramientas ETL
ETL significa extraer, transformar y cargar.
Las herramientas ETL alivian la carga del movimiento y la transformación de datos porque las herramientas comprenden el formato de datos y el entorno de cada DBMS con el que trabajan. Las herramientas ETL pueden ser útiles para convertir datos de DBMS a DBMS incluso fuera de las necesidades de almacenamiento.

#### Herramientas de recopilación 
Extraen datos de sistemas de aplicaciones externas y de bases de datos heterogéneas para la población en tablas de bases de datos de destino; en otras palabras extraen datos de diferentes bases de datos de marcas distintas y las agregan a la nueva base de datos. Elija herramientas de replicación con cuidado.

#### Herramientas de propagación
Una herramienta de propagación es similar en función a una herramienta de replicación, pero las herramientas de propagación están activas. Capturan constantemente las actualizaciones realizadas en el sistema externo, ya sea para la aplicación inmediata a las tablas de destino o para la posterior actualización por lotes.

#### Herramientas de consulta e informes
La capacidad de informes en formato sin necesidad de
programación es probablemente su mayor activo. Otra característica importante es una interfaz gráfica de usuario que le permite desarrollar las solicitudes de manipulación de datos sin escribir SQL complejas.

#### Analítica avanzada
La analítica avanzada es un enfoque centrado en los negocios, que comprende técnicas que ayudan a construir modelos y simulaciones para crear escenarios, comprender realidades e hipotetizar estados futuros.

### Herramientas de programación y desarrollo

#### Herramientas de punto de control / reinicio
herramientas disponibles para algunos productos DBMS para almacenar información de puntos de control que los programas de aplicación pueden usar durante los reinicios. La automatización del proceso de reinicio es otro beneficio proporcionado por algunas soluciones de punto de control / reinicio. Dichos productos son útiles para aplicaciones de bases de datos de lotes grandes que emiten muchos coomits.

#### Herramientas de Pruebas 
Las herramientas de prueba le permiten emitir una serie de pruebas en contra de una base de prueba y analizar los resultados. Las
herramientas de prueba normalmente se utilizan para todo tipo de aplicaciones, pero algunos se han ampliado específicamente para apoyar
las pruebas contra las tablas de bases de datos.

#### Herramientas de Depuración 
Son útiles para identificar y corregir los errores de sintaxis y lógica en las instrucciones SQL difíciles.

### Herramientas Varias 

#### Herramientas de gestión de espacio 
Ayudan en la gestión de espacio y optimizan el rendimiento mas aun en tareas pesadas. Asigna cada DBMS espacio diferente.

#### Herramientas de Compresión 
Reducen los costos de almacenamiento de los datos. Este tipo de herramienta opera mediante la
aplicación de un algoritmo a los datos en una tabla de tal manera que los datos se codifican en un área más compacta. 

#### Manuales en línea
Manuales en línea pueden funcionar como formación económica en la nueva versión de DBMS.

### Herramientas de desarrollo propio
Tales herramientas suelen ser desarrollados y mantenidos por los administradores de bases o programadores de sistemas dentro de la misma organización. 

## Nota 
Antes de comprar herramientas de terceros asegúrese de revisar bien las herramientas nativas del DBMS porque siempre si las nativas ofrecen lo mismo es mejor ahorrar costos y utilizar las nativas.

Pero herramientas de terceros pueden mejorar significativamente la eficiencia de las aplicaciones que accedan a datos relacionales. Al evaluar
los productos, buscar las características que son importantes para su organización. Considerar la adopción de listas de comprobación para las
comparaciones de productos en base a las características que se describen en este capítulo. Recuerde, la mayoría de los DBMS dejan
bastante que desear en la administración, acceso a datos, la supervisión del rendimiento, y las áreas de desarrollo de aplicaciones.
Herramientas de terceros DBA pueden ayudar a minimizar estas deficiencias y aliviar sus dolores de administración de bases de datos.

