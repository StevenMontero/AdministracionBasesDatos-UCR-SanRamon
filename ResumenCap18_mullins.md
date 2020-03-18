 # Administración de datos y almacenamiento

Los DBMS depende de los archivos de datos para almacenar datos y esos archivos de datos residen en medios o dispositivos físicos. La administración de los datos es una parte de trabajo de un DBA, saber los distintos tipos de almacenamiento y como operan estos es parte esencial de un DBA.

### Administración de almacenamiento básico

Normalmente los proveedores de DBMS no trabajan la parte de dispositivos para el almacenamiento de los datos, por eso es parte del DBA encargarse de elegir la mejor forma de almacenar esos datos. Existen muchas formas de almacenar datos y lo más común son los discos duros, que cada vez son más confiables, pero aun así es el componente más vulnerable a fallos      que un computador presenta. El DBA debe prever como tratar con este problema buscando técnicas como lo son los RAID, para minimizar el riesgo de pérdida de información.

### Uso moderno del disco DBMS

Los DBA deben estar preparados para los picos por el uso en los discos, ya que los DBMS hacen mas probables a que sucedan, y si hablamos de su uso de aplicaciones en línea aumenta el doble de riesgo ya que estas aplicaciones usan objetos sombra. Las operaciones de las bases de datos depende de las entradas y salidas en un computador, y el disco es uno de los elementos mas lentos para procesar estas entradas y salidas, si estos sufren de frecuentes picos de uso, ocasiona un rendimiento bajo en las operaciones, sumándole a esto el potente crecimiento en la información a nivel mundial, hacen que los DBA busque soluciones para optimizar el rendimiento de las bases de datos y brindar la mejor disponibilidad de los datos para los usuarios y aplicaciones. Algunas de las tareas para garantizar el mejor rendimiento son:

* Prevenir la perdida de datos
* Asegurar la capacidad que adecuada está disponible y que las soluciones de almacenamiento pueden fácilmente escalar según la necesidad de la creciente información
* Seleccionar soluciones que permitan un rápido acceso a los datos con el mínimo tiempo de interrupción
* Elegir soluciones de almacenamiento tolerante a fallos y rápidos de reparar

### Conjuntos de archivos y datos

Un DBA debe determinar cuánto espacio se va a requerir para la base de datos, un archivo de datos es un objecto donde se almacena la tabla de espacios, los índices y el registro de transacciones, y que quizás para un mayor rendimiento se deban separa, el DBA debe elegir qué tipos de dispositivos de almacenamiento usar para los diferentes tipos de datos, para poder sepáralos de acuerdo con su importancia. Por eso el DBA debe:

* Separa los índices de los datos por cuestiones de rendimiento
* Aislar el registro de transacciones en un dispositivo muy rápido
* Aislar los archivos temporales y de trabajo en un mismo volumen, si un error de disco ocurre los archivos temporales se pueden redefinir sin necesidad de un respaldo o implicaciones de recuperación
* Distribuir los datos en múltiples dispositivos para facilitar el acceso paralelo.

### Colocación de archivo en disco

El DBA debe determinar un optimo lugar para los archivos en el disco, una de las tareas es mover archivos de un disco a otro para mejorar el rendimiento utilizando técnicas como separa los índices de los datos, para cuando se utilizan las operaciones de entrada y salida del computador sean más eficientes, y que el brazo físico del disco no se deba mover tantas veces, esta y otras técnicas pueden mejorar el proceso de entradas y salidas del computador y también ayuda al rendimiento de las piezas mecánicas de los dispositivos de almacenamiento.

Obviamente en el caso de usar almacenamiento moderno que ya implementan técnicas adecuadas para el manejo de los archivos, no es necesario gastar tiempo en esto. Algunos DBMS ya proveen algunas opciones de almacenamiento, por ejemplo;

**Segmentos de Sybase (**permite seleccionar el tamaño de las tablas para que no puedan crecer más de lo que se le asigna, así el DBA puede crear segmentos específicos de tamaño y controlar los espacios en disco **)**

Estas herramientas permiten organizar los archivos de mayor frecuencia de acceso, separar archivos mas importantes de otros y reducir problemas físicos y lógicos.

**Particiones sin procesar versus sistemas de archivos**

Para los DBA muchas veces es mejor almacenar datos en archivos sin particiones que en un sistema de archivos con un sistema instalado, ya que el sistema interviene en el almacenamiento y muchas veces los sistemas de archivos no aseguran la recuperación del 100 por ciento de la información en cambio usar discos sin particiones no hay intervención de algún sistema, además el DBA se asegura una mayor capacidad de almacenamiento.

**Archivos temporales de bases de datos**

Los DBMS modernos, suelen crear objectos de bases de datos temporales utilizados por una transacción en un momento especifico, cuando esa transacción termina el objecto se pierde, pero esos objetos guardan archivos temporales que también requieren de alguna forma de almacenamiento a corto plazo durante la transacción y es por eso que también es necesario el manejo adecuado de esos datos.

**Administración del espacio**

Como la base de datos siempre esta expuesta a modificaciones y constante crecimiento, el DBA debe ser capaz de controlar y administrar el espacio correctamente y poder rastrear lo siguiente:

* Números de extensiones secundarias
* Fragmentación del dispositivo
* Espacio libre disponible
* Tamaño de la partición o segmento
* Tablas e indicen alojados por segmentos
* Cantidad de espacio utilizado actualmente

Un DBA debe estar preparado para cuando la base de datos esta en crecimiento y queda poco espacio de almacenamiento, y una forma de prevenir es soltando objectos que están ocupando espacio, pero no están siendo utilizados. Y en caso de que no haya suficiente, deberá agregar más espacio de almacenamiento.



###  Diseños de paginas de datos

Cada DBMS tiene su propio formato de diseñar sus páginas de datos, pero generalmente son tres elementos básicos: encabezado de página (contiene bits de información acerca de la página, como enlaces, punteros y espacio), filas de datos (contiene las filas reales de la tabla que a su vez contienen los datos de los usuarios) y offset table (contiene desplazamientos de punteros a cada fila en la página de datos).

**Páginas de asignación:** además los DBA utilizan otros tipos de paginas para controlar el uso del espacio y son usadas para gestionar otras paginas de objetos de la base de datos. Pueden existir varias páginas de asignación dentro de una base de datos, cada una controla un bloque de otras páginas de datos.

**Diseño de registro de datos**

Una tabla está compuesta de filas y columnas. Cada fila individual se debe almacenar por completo en una sola página de datos Cada fila está contenida dentro de un registro que consta de datos adicionales de limpieza junto con el contenido actual de datos de la fila. Cada registro de tabla comprende los siguientes elementos:encabezado de la fila (Consiste en el contenido de datos reales de las columnas de datos para la fila), offset Tables (el registro puede contener una tabla de desplazamiento con punteros para administrar y controlar dónde se almacenan los campos de longitud variable dentro de la fila.)

**Calculo del tamaño de la tabla.**

Una vez que se conocen los diseños de página y el DBA puede calcular con precisión las longitudes de registro, Calcular el tamaño de una tabla es fácil. Después de calcular la longitud del registro, el siguiente paso es determinar cuántas filas caben en una página física. Esto depende también del DBMS con el que se trabaja.

**Diseños de páginas de índice**

Cuando se almacenan filas en una página sin índices, las filas solo se agregan al final de la tabla, cuando la tabla se llena, y se agrega otra fila, esta se agrega a otra pagina y para luego encontrar esta fila, las paginas manejan punteros para adelante y para atrás para unir estas tablas, en el caso de las filas con índices, se almacenan en una sola tabla de índices y tiene los siguientes elementos: Encabezado de información (bytes de información física que detalla la estructura y composición del registro de índices), tamaño de la fila (longitud real de los datos indexados), índice de valores claves(), puntero de página (apunta a la tabla donde realmente están los datos) y offset y tablas ajustables (administran y controlan la posición de campos de longitud variable almacenados dentro de la fila del índice.)

**Calcular el tamaño de índice** El primer paso para calcular el espacio requerido para almacenar un índice es calcular el tamaño de fila para el índice, debe calcular el tamaño de un registro de índice no solo el tamaño de la fila después calcule el espacio de almacenamiento requerido para el índice.

**Registro de transacciones**

Cada insertar, actualizar y eliminar en cualquier tabla de la base de datos se registra en el registro de transacciones. Llegar a un tamaño exacto para el registro de transacciones puede ser más un arte que una ciencia, porque la actividad de la transacción es por naturaleza aleatoria. Una de las cosas mas importante es asegurar suficiente espacio para este tipo de transacciones ya que si no se generan respaldos y no hay suficiente espacio puede perder esta información o hacer que el servicio de transacciones se ralentice o se pare por completo.

**Fragmentación y almacenamiento**

El termino fragmentación es la dispersión de partes de un archivo a través de un disco, como cuando el sistema operativo divide un archivo y lo ajusta en los espacios vacíos por archivos eliminados previamente. Esto ocurre cada vez que se agregan, modifica archivos o se eliminan de las tablas donde se construyen índices

La fragmentación afecta el rendimiento porque no solo los datos se encuentran subóptima mente ubicados, sino que cuando un motor de lectura de base de datos escanea los índices para el procesamiento de lectura anticipada, la fragmentación puede causar páginas de datos adicionales para escanear en el caché de datos, lo que degrada el rendimiento.



### Opciones de almacenamiento

Una vez calculado la cantidad requerida de espacio en almacenamiento por la base de datos, los DBA  deben elegir entre múltiples opciones de almacenamiento, el principal y mas usado es el disco duro, por su confiabilidad, su capacidad de grande volúmenes de datos y bajo costo, pero existen otras opciones como los discos de estado sólido, que son más rápidos pero más caros, o los discos ópticos, entre otros, esto depende de las características que el DBA consideren adecuados para la base de datos.

**RAID**

Las interrupciones debido a fallos de medios simples pueden ser evitados implementados discos modernos con técnicas para la tolerancia a fallos y recuperación inmediata como lo son los RAID (arreglos redundantes de discos independientes) combina varios discos en un array y el sistema lo percibe como un solo disco, una gran ventaja es que se pueden cambiar en caliente, sin necesidad de interrumpir o apagar el equipo. Existen varios niveles:

* RAID-0 (La información es dividida en múltiples discos, no es redundante, mejora la capacidad de procesamiento de entradas y salidas si un disco falla, hay perdida de datos)
* RAID-1 (funciona como un espejo, lo que se escribe en un conjunto de discos, se escribe también en el otro conjunto de discos)
* RAID-2 (proporciona codificación de corrección de errores)
* RAID-3 (los datos son divididos entre los discos de la matriz excepto en uno que es el que guarda los bits de paridad para corrección de errores, tiene altas tasas de transferencia)
* RAID-4 (funciona igual que el RAID-3 pero a diferencia de este, RAID-4 permite la reconstrucción en tiempo real de los datos, siendo una opción muy eficiente para almacenar grandes cantidades de datos)
* RAID-5 (funciona similar a RAID-4 excepto que en este los bits de paridad se distribuyen en toda la matriz de discos haciendo que la grabación de datos sea más rápida)
* RAID-6 (funciona igual que el RAID-5 pero este contiene un segundo esquema de bits de paridad)
* RAID-10 (es una matriz de segmentos donde cada segmento es un RAID-1)
* RAID-50 (es una matriz de segmentada, donde cada segmento es un RAID-3)
* RAID-0+1 (combinación de RAID-0 con RAID-1)

### JBOD

Significa, solo un montón de discos es un término usado para diferenciar la tecnología tradicional de discos de la tecnología de almacenamiento más nueva. Por lo general, los discos están conectados directamente a un servidor. Una vez que el DBMS está instalado en esas unidades de disco, se pueden crear archivos de base de datos.

### Redes de área del almacenamiento (SAN)

Red interconectada de dispositivos de almacenamiento, permite administrar una serie de recursos de almacenamiento interconectados por la red, centralizando estos recursos para una mayor eficiencia, y capacidad de procesamiento que en el caso que estos recursos, estuvieran aislados, se utiliza la misma técnica de SCSI y su protocolo de transferencia es el canal de fibra, uno de los propósitos es la compartición de datos por la red.

**Almacenamiento conectado a la red**

NAS, se refiere al almacenamiento al que se puede acceder directamente desde la red. Con NAS, los sistemas host o cliente pueden leer y escribir datos a través de una interfaz de red (como Ethernet, FDDI u otros) utilizando protocolos que incluyen NFS y CIFS. NAS puede ser implementado utilizando servidores de archivos, sistemas host que ejecutan software NAS o servidores delgados llamados accesorios.

**SAN versus NAS**

La diferencia con las NAS es que su capacidad de almacenamiento es menor y tiene menor rendimiento que las SAN, NAS es más adecuado para resolver problemas de almacenamiento multimedia, problemas de intercambio de datos e intercambio de almacenamiento para sistemas más pequeños.

**Almacenamiento escalonado o niveles**

Se asignan diferentes categorías de datos para diferentes tipos de medios de almacenamiento. Esta técnica despliega cuatro categorías: caliente, cálido, frío y latente. La temperatura de los datos se define como una función de la velocidad de acceso para consultas, actualizaciones y mantenimiento de datos, una vez clasificados sus dispositivos de almacenamiento para usar con cada temperatura de datos, las características varían al igual que los costos por ejemplo, caliente: los datos que requieren mucha E/S y requieren alta disponibilidad se pueden colocar en dispositivos de almacenamiento que ofrezcan alto rendimiento, fiabilidad, funciones avanzadas y gran capacidad, a diferencia de los datos latentes a los que no se ha accedido durante mucho tiempo (quizás años) y cuyo modelo de datos es estable, se puede mover a sistemas de almacenamiento fuera de línea como cinta inteligente o disco óptico.

**Planificando para el futuro**

El DBA debe estar siempre atento en la planificación del crecimiento a futuro. El DBA debe estar atento sobre la cantidad de datos y el número de usuarios que acceden a los datos. Cuando cualquiera se expande, el almacenamiento de la base de datos puede tener que modificarse.

**Planificación de capacidad**

Esto significa evaluar todos los recursos con los que se cuenta y de acuerdo al crecimiento en los datos poder medir la capacidad actual, medir el crecimiento de la capacidad a lo largo del tiempo y tener en cuenta los requisitos de capacidad anticipados de nuevas iniciativas corporativas y de TI, puede determinar si su infraestructura existente puede soportar la carga de trabajo anticipada. Si el proyectado el crecimiento supera la capacidad de su entorno informático para soportarlo, necesitará evaluar el costo de modificar y posiblemente ampliar su infraestructura informática. Esto podría generar algunas tareas adicionales como: Rediseño de aplicaciones, Rediseño de las bases de datos, Modificación de los parámetros de los DBMS , reconfiguración de los componentes de hardware.