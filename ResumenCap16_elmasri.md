## Almacenamiento en disco, estructuras de archivos básicas, hashing y arquitecturas de almacenamiento modernas

La recopilación de datos que conforma una base de datos computarizada debe almacenarse físicamente en algún medio de almacenamiento informático.
El software DBMS puede recuperar, actualizar y procesar estos datos según sea necesario.
Los medios de almacenamiento de la computadora forman una jerarquía de almacenamiento que incluye dos categorías principales:

- **Almacenamiento primario:** Esta categoría incluye medios de almacenamiento que pueden ser operados directamente por la unidad central de procesamiento (CPU) de la computadora, como la memoria principal de la computadora y cachés más pequeños pero más rápidos.

- **Almacenamiento secundario:** Este tipo de almacenamiento se compone principalmente de discos magnéticos los cuales son los mas comunes en almacenamiento de bases de datos empresariales.Sin embargo, las memorias flash se están convirtiendo en un medio común de elección para almacenar cantidades moderadas de datos permanentes por su alta taza de transferencia.

- **Almacenamiento terciario:** Esta categoría incluye los CD-ROM,DVD,..., y las cintas que son medios de almacenamiento que se usan fuera de producción.Se usan generalmente para hacer Backups.

## Jerarquías de memoria y dispositivos de almacenamiento

En un sistema informático moderno, los datos residen y se transportan a través de una jerarquía de medios de almacenamiento. La memoria de mayor velocidad es la más cara y, por lo tanto, está disponible con la menor capacidad. La memoria de menor velocidad es el almacenamiento en cinta sin conexión, que está esencialmente disponible en capacidad de almacenamiento indefinido.

En el nivel de almacenamiento primario, la jerarquía de memoria incluye, en el extremo más caro, la memoria caché, DRAM (RAM dinámica)proporciona el área de trabajo principal para la CPU para mantener las instrucciones y los datos del programa.

La CPU suele utilizar la memoria caché para acelerar la ejecución de las instrucciones del programa utilizando técnicas como la captación previa y la canalización.

En el nivel de almacenamiento secundario y terciario, la jerarquía incluye discos magnéticos; dispositivos de almacenamiento masivo en forma de CD-ROM (disco compacto, memoria de solo lectura) y DVD (disco de video digital o disco versátil digital); y finalmente graba en el extremo menos costoso de la jerarquía.

### Memoria Flash

Este tipo de memoria esta entre la DRAM y el almacenamiento en disco magnético, la memoria flash se está volviendo común, particularmente porque no es volátil. Usan tecnología EEPROM (memoria de solo lectura programable y borrable eléctricamente).

Los dispositivos flash se utilizan en cámaras, reproductores de MP3 / MP4, teléfonos celulares, PDA y USB.

### Unidades Ópticas

La forma más popular de almacenamiento óptico extraíble son los CD y los DVD.

Aunque las máquinas de discos ópticos tienen capacidades en cientos de gigabytes, sus tiempos de recuperación son de cientos de milisegundos, bastante más lentos que los discos magnéticos.

### Cintas Magnéticas

Finalmente, las cintas magnéticas se utilizan para archivar y guardar copias de seguridad de datos. Este medio se están volviendo popular como almacenamiento terciario para almacenar terabytes de datos.

**Para resumir, una jerarquía de dispositivos de almacenamiento y sistemas de almacenamiento está disponible hoy para el almacenamiento de datos.**

## Organización de almacenamiento de bases de datos

Las bases de datos suelen almacenar grandes cantidades de datos que deben persistir durante largos períodos de tiempo y, por lo tanto, los datos a menudo se denominan datos persistentes.
Se accede a partes de estos datos y se procesan repetidamente durante el período de almacenamiento.

La mayoría de las bases de datos se almacenan de forma permanente en el almacenamiento secundario usando disco magnético, por las siguientes razones:

    * Generalmente, las bases de datos son demasiado grandes para caber completamente en la memoria principal.
    * Presentan menos fallas y perdidas de datos.
    * El costo de almacenamiento por unidad de datos es un orden de magnitud menor para el almacenamiento secundario.

Por lo tanto, es importante estudiar y comprender las propiedades y características de los discos magnéticos y la forma en que se pueden organizar los archivos de datos en el disco para diseñar bases de datos efectivas con un rendimiento aceptable.

Los diseñadores de bases de datos y el DBA deben conocer las ventajas y desventajas de cada técnica de almacenamiento cuando diseñan, implementan y operan una base de datos en un DBMS específico.

Las aplicaciones de bases de datos típicas necesitan solo una pequeña porción de la base de datos a la vez para su procesamiento. Siempre que se necesite una cierta parte de los datos, debe ubicarse en el disco, copiarse en la memoria principal para su procesamiento y luego reescribirse en el disco si se modifican los datos. Los registros deben almacenarse en el disco de manera que sea posible localizarlos de manera eficiente cuando sean necesarios.

**Heap file:** (archivo desordenado) coloca los registros en el disco sin ningún orden en particular agregando nuevos registros al final del archivo.
**Sorted file:** (archivo desordenado) mantiene los registros ordenados por el valor de un campo en particular (llamado la clave de clasificación).
**Hash file:** Un archivo hash utiliza una función hash aplicada a un campo en particular (llamada clave hash) para determinar la ubicación de un registro en el disco.

## Secondary Storage Devices

### Descripción del hardware de los dispositivos de disco

Los discos magnéticos se utilizan para almacenar grandes cantidades de datos. Se denomina unidad de disco duro o HDD. Su funcionamiento es magnetizar un área en un disco de ciertas maneras, uno puede hacer que esa área represente un valor de bit de 0 (cero) o 1 (uno). Para codificar la información, los bits se agrupan en bytes (8 bytes es lo mas común). La capacidad de un disco es la cantidad de bytes que puede almacenar, que generalmente es muy grande.
Los discos duros para computadoras personales actualmente contienen desde varios cientos de gigabytes hasta unos pocos terabytes; y los paquetes de discos grandes utilizados con servidores y mainframes tienen capacidades de cientos de gigabytes.

Están hechos de material magnético con forma de disco delgado y protegidos por una cubierta de plástico o acrílico. Un disco es de un solo lado si almacena información en una de sus superficies solamente y de doble cara si se usan ambas superficies. Los dos factores de forma más comunes son 3.5 y 2.5 pulgadas de diámetro.

El prefijo de 10K en los nombres de disco se refiere a las velocidades de rotación en rpm (revoluciones por minuto.

La dirección de hardware de un bloque (una combinación de un número de cilindro, número de pista (número de superficie dentro del cilindro en el que se encuentra la pista) y número de bloque (dentro de la pista) se suministra a la E / S del disco (entrada / salida) hardware.

En muchas unidades de disco modernas, un número único llamado LBA (dirección de bloque lógico), que es un número entre 0 y n (suponiendo que la capacidad total del disco es n + 1 bloques).

A veces, varios bloques contiguos, llamados un grupo, pueden transferirse como una unidad. En este caso, el tamaño del búfer se ajusta para que coincida con el número de bytes en el clúster.

Los paquetes de discos con múltiples superficies están controlados por varios cabezales de lectura / escritura, uno para cada superficie. Todos los brazos están conectados a un actuador conectado a otro motor eléctrico, que mueve los cabezales de lectura / escritura al unísono y los coloca con precisión sobre el cilindro de pistas especificado en una dirección de bloque.
Una vez que el cabezal de lectura / escritura se coloca en la pista correcta y el bloque especificado en la dirección del bloque se mueve debajo del cabezal de lectura / escritura, el componente electrónico del cabezal de lectura / escritura se activa para transferir los datos.

### Interfaces de unidades de disco a sistemas informáticos

Controla la unidad de disco y la conecta al sistema informático.
Una de las interfaces estándar utilizadas para unidades de disco en PC y estaciones de trabajo se llamaba SCSI (interfaz de sistema de computadora pequeña).Hoy, para conectar discos duros, CD y DVD a una computadora, la interfaz elegida es SATA(ATA en serie).
El controlador acepta comandos de E / S de alto nivel y toma las medidas apropiadas para posicionar el brazo y hace que tenga lugar la acción de lectura / escritura.

## Hacer que el acceso a datos sea más eficiente en el disco

### Almacenamiento en búfer de datos:

Como los HDD son mas lentos que la CPU, el almacenamiento en búfer de datos se realiza en la memoria para que los datos nuevos se puedan almacenar en un búfer mientras que los datos viejos es procesado por una aplicación.

### Organización adecuada de los datos en el disco:

La estructura y organización de los datos en el disco, es ventajoso mantener los datos relacionados en bloques contiguos; cuando una relación necesita varios cilindros, se deben usar cilindros contiguos. Hacerlo evita movimientos innecesarios del brazo de lectura / escritura y el tiempo de búsqueda relacionado.

### Lectura de datos antes de la solicitud:

Para minimizar los tiempos de búsqueda, cada vez que se lee un bloque en el búfer, los bloques del resto de la pista también se pueden leer aunque aún no se hayan solicitado. Esto funciona bien para aplicaciones que probablemente necesiten bloques consecutivos.

### Programación adecuada de las solicitudes de E/S:

Se puede minimizar el tiempo de acceso total programándolos para que el brazo se mueva solo en una dirección y recoja los bloques a lo largo de su movimiento. Un algoritmo popular se llama algoritmo de ascensor; Este algoritmo imita el comportamiento de un ascensor que programa solicitudes en varios pisos en una secuencia adecuada.

### Uso de discos de registro para retener escrituras temporalmente:

Se puede asignar un solo disco a una sola función llamada registro de escrituras.Tener el archivo de datos y el archivo de registro en el mismo disco es una solución más barata pero compromete el rendimiento. Aunque la idea de un disco de registro puede mejorar el rendimiento de escritura, no es factible para la mayoría de los datos de aplicaciones de la vida real.

### Uso de SSD o memoria flash para fines de recuperación:

En aplicaciones donde las actualizaciones ocurren con alta frecuencia, las actualizaciones se pueden perder de la memoria principal si el sistema falla. Una medida preventiva sería aumentar la velocidad de las actualizaciones / escrituras en el disco. Un posible enfoque consiste en escribir las actualizaciones en un búfer SSD no volátil, que puede ser una memoria flash o una DRAM que funciona con batería, que funcionan a velocidades más rápidas, los buffers SSD no escritos deben escribirse en el archivo de datos en el HDD.

## Unidad de estado solido (SolidState Device Storage) SSD

El componente principal de un SSD es un controlador y un conjunto de tarjetas de memoria flash interconectadas.
Se asemejan a los discos en términos de la capacidad de almacenar datos en un almacenamiento secundario sin la necesidad de una fuente de alimentación continua. La unidad es más resistente, funciona silenciosamente, es más rápida en términos de tiempo de acceso y proporciona tasas de transferencia más altas que el HDD, no hay restricción en la colocación de datos en un SSD ya que cualquier dirección es directamente direccionable. Su desventaja es su precio.

## Magnetic Tape Storage Devices

Las cintas magnéticas son dispositivos de acceso secuencial; para acceder al enésimo bloque en la cinta, primero debemos escanear el precedente n - 1 bloques. Los datos se almacenan en carretes de cinta magnética de alta capacidad, algo similar a las cintas de audio o video.
Las cintas también se pueden usar para almacenar archivos de bases de datos excesivamente grandes. Los archivos de base de datos que rara vez se usan o que están desactualizados pero que se requieren para el mantenimiento de registros históricos se pueden archivar en cinta.

## Almacenamiento de bloques

Cuando se necesitan transferir varios bloques del disco a la memoria principal y se conocen todas las direcciones de bloque, se pueden reservar varios buffers en la memoria principal para acelerar la transferencia. Mientras se lee o se escribe un búfer, la CPU puede procesar datos en el otro búfer porque existe un procesador de E / S de disco independiente (controlador) que, una vez iniciado, puede proceder a transferir un bloque de datos entre la memoria y el disco independientemente de y en paralelo al procesamiento de la CPU.
El almacenamiento en búfer es más útil cuando los procesos pueden ejecutarse simultáneamente de manera paralela, ya sea porque hay disponible un procesador de E / S de disco separado o porque existen múltiples procesadores de CPU.

### Manejo de Buffer

La gestión real de los buffers y las decisiones sobre qué buffers usar para colocar una página recién leída en el buffer es un proceso más complejo. Usamos el término búfer para referirnos a una parte de la memoria principal que está disponible para recibir bloques o páginas de datos del disco.9 El administrador de búferes es un componente de software de un DBMS que responde a las solicitudes de datos y decide qué búfer usar y qué páginas para reemplazar en el búfer para acomodar los bloques recién solicitados. El tamaño de la agrupación de almacenamiento intermedio compartido suele ser un parámetro para el DBMS controlado por DBA. En esta sección, discutimos brevemente el funcionamiento del administrador de búfer y algunas estrategias de reemplazo.

Hay dos tipos de administradores de búfer:

    * El primer tipo controla la memoria principal directamente, como en la mayoría de los RDBMS.
    * El segundo tipo asigna memorias intermedias en la memoria virtual, lo que permite que el control se transfiera al sistema operativo.

Este segundo tipo de administrador de búfer es común en los sistemas de bases de datos de memoria principal y algunos DBMS orientados a objetos.
El administrador de búfer tiene la siguiente responsabilidad: debe asegurarse de que el número de búferes se ajuste a la memoria principal.

El objetivo general del administrador de búfer es doble:

    * maximizar la probabilidad de que la página solicitada se encuentre en la memoria principal.
    * en caso de leer un nuevo bloque de disco desde el disco, encontrar una página para reemplazar eso causar el menor daño en el sentido de que no se requerirá en breve nuevamente.

El administrador de búfer mantiene dos tipos de información a mano sobre cada página en el grupo de búferes:

     1. Un recuento de pines: la cantidad de veces que se ha solicitado esa página o la cantidad de usuarios actuales de esa página. En general, no se debe permitir que un bloque anclado se escriba en el disco.
     2. Un bit sucio, que inicialmente se establece en cero para todas las páginas, pero se establece en 1 cada vez que cualquier programa de aplicación actualiza esa página.

Si la página no está en el grupo de búferes, el administrador de búferes hace lo siguiente:

    a. Elige una página para su reemplazo, utilizando la política de reemplazo, e incrementa su recuento de pines.
    b.Si el bit sucio de la página de reemplazo está activado, el administrador de búfer escribe esa página en el disco reemplazando su copia anterior en el disco. Si el bit sucio no está activado, esta página no se modifica y el administrador de búfer no está obligado a volver a escribirla en el disco.
    c. Lee la página solicitada en el espacio liberado.
    d.La dirección de memoria principal de la nueva página se pasa a la aplicación solicitante.

## Estrategias de reemplazo del buffer

**Menos utilizado recientemente (Least recently used o LRU):** La estrategia aquí es desechar esa página que no se ha utilizado (leída o escrita) durante mucho tiempo.

**Política de reloj:** es una variante de la política de LRU. Imagine que las memorias intermedias están dispuestas como un círculo similar a un reloj. Cada búfer tiene una bandera con un valor 0 o 1. Los buffers con un 0 son vulnerables y pueden usarse para reemplazo y su contenido se vuelve a leer en el disco. Los tampones con un 1 no son vulnerables. Cuando se lee un bloque en un búfer, el indicador se establece en 1. Cuando se accede al búfer, el indicador también se establece en 1. La manecilla del reloj se coloca en un "búfer actual". Cuando el administrador de búfer necesita un búfer para un nuevo bloque, gira la mano hasta que encuentra un búfer con un 0 y lo usa para leer y colocar el nuevo bloque. (Si el bit sucio está activado para la página que se está reemplazando, esa página se escribirá en el disco, sobrescribiendo así la página anterior en su dirección en el disco).

**Primero en entrar, primero en salir (FIFO):** según esta política, cuando se requiere un búfer, el que ha estado ocupado más tiempo por una página se utiliza para el reemplazo.

Existen algunas otras estrategias de reemplazo, como MRU (la más reciente o most recently used).

## Colocación de registros de archivos en el disco

### Registros y tipos de registros

Los datos generalmente se almacenan en forma de registros.Cada registro consta de una colección de valores o elementos de datos relacionados, donde cada valor está formado por uno o más bytes y corresponde a un campo particular del registro. Los registros generalmente describen entidades y sus atributos.
En algunas aplicaciones de bases de datos, puede surgir la necesidad de almacenar elementos de datos que consisten en grandes objetos no estructurados, que representan imágenes, secuencias de audio o video digitalizadas o texto libre. Estos se conocen como BLOB (objetos binarios grandes).
Para almacenar texto libre, algunos DBMS (por ejemplo, Oracle, DB2, etc.) proporcionan un tipo de datos llamado CLOB (character large object o objeto grande de caracteres); algunos DBMS llaman a este tipo de texto texto.

### Archivos, registros de longitud fija y registros de longitud variable

Un archivo es una secuencia de registros. En muchos casos, todos los registros en un archivo son del mismo tipo de registro. Si cada registro en el archivo tiene exactamente el mismo tamaño (en bytes), se dice que el archivo está compuesto de registros de longitud fija. Si diferentes registros en el archivo tienen diferentes tamaños, se dice que el archivo está compuesto de registros de longitud variable.

Un archivo puede tener registros de longitud variable por varias razones:

- Los registros de archivo son del mismo tipo de registro, pero uno o más de los campos son de tamaño variable (campos de longitud variable).
- Los registros de archivo son del mismo tipo de registro, pero uno o más de los campos pueden tener múltiples valores para registros individuales.
- Los registros de archivo son del mismo tipo de registro, pero uno o más de los campos son opcionales; es decir, pueden tener valores para algunos pero no todos los registros de archivos.
- El archivo contiene registros de diferentes tipos de registros y, por lo tanto, de diferentes tamaños.

Un archivo de registros con campos opcionales se puede formatear de diferentes maneras. Si el número total de campos para el tipo de registro es grande, pero el número de campos que realmente aparecen en un registro típico es pequeño, podemos incluir en cada registro una secuencia de pares <field-name, field-value> en lugar de solo Los valores del campo.Se pueden usar caracteres como separadores pero una opción más práctica es asignar un código de tipo de campo corto, por ejemplo, un número entero, a cada campo e incluir en cada registro una secuencia de pares <field-type, field-value> en lugar de <field-name, field-value > pares.

### Bloqueo de registros y registros distribuidos vs no distribuidos

Los registros de un archivo deben asignarse a bloques de disco porque un bloque es la unidad de transferencia de datos entre el disco y la memoria.
Suponga que el tamaño del bloque es B bytes. Para un archivo de registros de longitud fija de tamaño R bytes, con B ≥ R, podemos ajustar registros bfr = ⎣B / R⎦ por bloque, donde the (x) ⎦ (función de piso) redondea el número x a un entero. El valor bfr se llama factor de bloqueo para el archivo. En general, R puede no dividir B exactamente, por lo que tenemos un espacio no utilizado en cada bloque igual a: B − (bfr \* R) bytes.
Un puntero al final del primer bloque apunta al bloque que contiene el resto del registro en caso de que no sea el siguiente bloque consecutivo en el disco.

Esta organización se denomina distribuida porque los registros pueden abarcar más de un bloque. Siempre que un registro sea más grande que un bloque, debemos usar una organización distribuida.

### Asignación de bloques de archivos en el disco

En la asignación contigua, los bloques de archivos se asignan a bloques de disco consecutivos. Esto hace que la lectura de todo el archivo sea muy rápida utilizando el doble almacenamiento en búfer, pero dificulta la expansión del archivo.

En la asignación vinculada, cada bloque de archivo contiene un puntero al siguiente bloque de archivo. Esto facilita la expansión del archivo, pero hace que sea lento leer todo el archivo.

Una combinación de los dos grupos de bloques de discos consecutivos y los grupos están vinculados. Los clústeres a veces se denominan segmentos de archivo o extensiones.

Otra posibilidad es utilizar la asignación indexada, donde uno o más bloques de índice contienen punteros a los bloques de archivo reales.

### Encabezados de archivo

Un encabezado o descriptor de archivo contiene información sobre un archivo que necesitan los programas del sistema que acceden a los registros de archivo. El encabezado incluye información para determinar las direcciones de disco de los bloques de archivos, así como para registrar descripciones de formato, que pueden incluir longitudes de campo y el orden de los campos dentro de un registro para registros de longitud fija y códigos de tipo de campo, caracteres de separación y registro códigos de tipo para registros de longitud variable.

## Operaciones en archivos

Las operaciones en archivos generalmente se agrupan en operaciones de recuperación y operaciones de actualización. Los primeros no cambian ningún dato en el archivo, sino que solo localizan ciertos registros para que sus valores de campo puedan ser examinados y procesados. Este último cambia el archivo mediante la inserción o eliminación de registros o mediante la modificación de los valores de campo.

Por lo general, los programas de alto nivel, como los programas de software DBMS, acceden a los registros mediante el uso de estos comandos, por lo que a veces nos referimos a las variables del programa en las siguientes descripciones:

**Open:** Prepara el archivo para leer o escribir. Asigna los búferes apropiados (generalmente al menos dos) para contener bloques de archivos del disco y recupera el encabezado del archivo. Establece el puntero del archivo al comienzo del archivo.

**Reset:** Establece el puntero de archivo de un archivo abierto al comienzo del archivo.

**Find (or Locate):** . Busca el primer registro que cumple una condición de búsqueda. Transfiere el bloque que contiene ese registro a un búfer de memoria principal (si aún no está allí). El puntero del archivo apunta al registro en el búfer y se convierte en el registro actual. A veces, se usan diferentes verbos para indicar si el registro localizado se va a recuperar o actualizar.

**Read (or Get):** Copia el registro actual del búfer a una variable de programa en el programa de usuario. Este comando también puede avanzar el puntero de registro actual al siguiente registro en el archivo, lo que puede requerir leer el siguiente bloque de archivo desde el disco.

**FindNext:** Busca el siguiente registro en el archivo que satisface la condición de búsqueda. Transfiere el bloque que contiene ese registro a un búfer de memoria principal (si aún no está allí). El registro se encuentra en el búfer y se convierte en el registro actual. Varias formas de FindNext (por ejemplo, el registro FindNext dentro de un registro padre actual, el registro FindNext de un tipo determinado o el registro FindNext donde se cumple una condición compleja) están disponibles en los DBMS heredados basados en los modelos jerárquicos y de red.

**Delete:** Elimina el registro actual y (eventualmente) actualiza el archivo en el disco para reflejar la eliminación.

**Modify:** Modifica algunos valores de campo para el registro actual y (eventualmente) actualiza el archivo en el disco para reflejar la modificación.

**Insert:** Inserta un nuevo registro en el archivo localizando el bloque donde se va a insertar el registro, transfiriendo ese bloque a un búfer de memoria principal (si aún no está allí), escribiendo el registro en el búfer y (eventualmente) escribiendo el búfer al disco para reflejar la inserción.

**Close:** Completa el acceso al archivo al liberar los búferes y realizar cualquier otra operación de limpieza necesaria.

Es posible simplificar las operaciones Buscar, Buscar siguiente y Leer en una sola operación, Escanear, cuya descripción es la siguiente:

**Scan:** Si el archivo se acaba de abrir o restablecer, Scan devuelve el primer registro; de lo contrario, devuelve el siguiente registro. Si se especifica una condición con la operación, el registro devuelto es el primero o el siguiente registro que cumple la condición.

■ FindOrdered. Recupera todos los registros en el archivo en un orden específico.
■ Reorganize. Inicia el proceso de reorganización. Como veremos, algunas organizaciones de archivos requieren una reorganización periódica.

En este punto, vale la pena notar la diferencia entre la organización del archivo de términos y el método de acceso. Una organización de archivos se refiere a la organización de los datos de un archivo en registros, bloques y estructuras de acceso; Un método de acceso, por otro lado, proporciona un grupo de operaciones, como las enumeradas anteriormente, que se pueden aplicar a un archivo.

## Archivos de registros no ordenados (archivos de montón)

En este tipo de organización más simple y básico, los registros se colocan en el archivo en el orden en que se insertan, por lo que se insertan nuevos registros al final del archivo.

Para eliminar un registro, un programa primero debe encontrar su bloque, copiar el bloque en un búfer, eliminar el registro del búfer y finalmente reescribir el bloque nuevamente en el disco. Esto deja espacio no utilizado en el bloque de disco. Eliminar una gran cantidad de registros de esta manera da como resultado un desperdicio de espacio de almacenamiento. Otra técnica utilizada para la eliminación de registros es tener un byte o bit adicional, llamado marcador de eliminación, almacenado con cada registro. Un registro se elimina al establecer el marcador de eliminación en un cierto valor. Un valor diferente para el marcador indica un registro válido (no eliminado).

## Files of Ordered Records (Sorted Files)

Podemos ordenar físicamente los registros de un archivo en el disco en función de los valores de uno de sus campos, llamados el campo de pedidos. Esto lleva a un archivo ordenado o secuencial.

Si el campo de pedido también es un campo clave del archivo, un campo garantizado para tener un campo único valor en cada registro, entonces el campo se llama clave de orden para el archivo.

Los registros ordenados tienen algunas ventajas sobre los archivos no ordenados. Primero, leyendo el

registros en orden de los valores clave de ordenamiento se vuelve extremadamente eficiente porque no se requiere clasificación.

Se puede realizar una búsqueda binaria de archivos de disco en los bloques en lugar de en los registros.

Insertar y eliminar registros son operaciones costosas para un archivo ordenado porque los registros deben permanecer ordenados físicamente. Para insertar un registro, debemos encontrar su posición correcta en el archivo, en función de su valor de campo de orden, y luego hacer espacio en el archivo para insertar el registro en esa posición. Para un archivo grande, esto puede llevar mucho tiempo porque, en promedio, la mitad de los registros del archivo se deben mover para hacer espacio para el nuevo disco. Esto significa que la mitad de los bloques de archivos deben leerse y reescrito después de mover los registros entre ellos. Para eliminar registros, el problema es menos grave si se utilizan marcadores de eliminación y reorganización periódica.

La modificación de un valor de campo de un registro depende de dos factores: la condición de búsqueda para localizar el registro y el campo a modificar. Si la condición de búsqueda esta ordenada involucra el campo clave, podemos localizar el registro usando una búsqueda binaria; de lo contrario se debe hacer una búsqueda lineal. Un campo no ordenado puede modificarse cambiando el dato y reescribirlo en la misma ubicación física en el disco, suponiendo que registros de va a ser de la misma longitud. Modificar el campo de pedido significa que el registro puede cambiar su posición en el archivo. Esto requiere la eliminación del registro anterior seguido de la inserción de del registro modificado.

## Hashing Techniques

Otro tipo de organización de archivos primaria se basa en el hash, que proporciona un acceso muy rápido a registros bajo ciertas condiciones de búsqueda. Esta organización es usualmente llamado un archivo hash. La idea detrás del hashing es proporcionar una función h, llamada función hash o función aleatoria, que se aplica a valor de campo hash de un registro y proporciona la dirección del bloque de disco en el que el registro está almacenado. Se puede realizar una búsqueda del registro dentro del bloque en un memoria intermedia principal. Para la mayoría de los registros, solo necesitamos un acceso de bloque único a recuperar ese registro. El hash también se usa como una estructura de búsqueda interna dentro de un programa siempre que se accede a un grupo de registros exclusivamente utilizando el valor de un campo.

## Internal Hashing

Para archivos internos, el hash se implementa típicamente como una tabla hash a través del uso de una serie de registros. Supongamos que el rango del índice de matriz es de 0 a M - 1, como mostrado en la figura 16.8 (a); entonces tenemos M ranuras cuyas direcciones corresponden a los índices de matriz. Elegimos una función hash que transforma el valor del campo hash en un número entero entre 0 y M - 1. Una función hash común es el mod h (K) = K
Función M, que devuelve el resto de un valor de campo hash entero K después de la división por M; este valor se usa para la dirección de registro
Una colisión en el sistema hash ocurre cuando el valor del campo hash de un registro que se está insertando a una dirección ya contiene un registro diferente.

Algunas de la soluciones para esto son;

**Direccionamiento abierto.** Procedente del puesto ocupado especificado por eldirección hash, el programa verifica las posiciones posteriores en orden hasta que se encuentra la posición no utilizada (vacía).

**Encadenamiento.** Para este método, se mantienen varias ubicaciones de desbordamiento, generalmente extendiendo la matriz con varias posiciones de desbordamiento. Además, un puntero se agrega a cada ubicación de registro. Una colisión se resuelve colocando el nuevo registro en una ubicación de desbordamiento no utilizada y configurando el puntero de la ubicación de la dirección hash ocupada a la dirección de esa ubicación de desbordamiento.

**Múltiple hashing.** El programa aplica una segunda función hash si la primera resulta en una colisión. Si se produce otra colisión, el programa usa direccionamiento abierto o aplica una tercera función hash y luego utiliza direccionamiento abierto si es necesario. Tenga en cuenta que las series de funciones hash se usan en el mismo orden para su recuperación.

**16.8.2 Hashing externo para archivos de disco (static hashing**).

El hash para archivos de disco se llama hashing externo. Para adaptarse a las características del disco almacenamiento, el espacio de dirección de destino está hecho de cubos, cada uno de los cuales contiene múltiples registros. Un depósito es un bloque de disco o un grupo de bloques de disco contiguos.La función hash asigna una clave a un número de depósito relativo en lugar de asignación de una dirección de bloque absoluta al depósito.

## Técnicas de hash que permiten la expansión dinámica de archivos

Un inconveniente importante del esquema de hash estático que acabamos de comentar es que el hash
El espacio de direcciones es fijo. Por lo tanto, es difícil expandir o reducir el archivo dinámicamente.
Los esquemas descritos en esta sección intentan remediar esta situación.

**Hashing extensible.** En hashing extensible, propuesto por Fagin (1979), un tipo de directorio: una matriz de 2d direcciones de depósito: se mantiene, donde d se llama profundidad global del directorio. El valor entero correspondiente a los primeros d bits (de alto orden) de un valor hash se usa como índice de la matriz para determinar un directorio entrada, y la dirección en esa entrada determina el depósito en el que se almacenan los registros correspondientes. Sin embargo, no tiene que haber un cubo distinto para cada de la 2d ubicaciones de directorio, varias ubicaciones de directorio con los mismos primeros d ′ bits para sus valores hash pueden contener la misma dirección de depósito si todos los registros que el hash a estas ubicaciones cabe en un solo cubo. Una profundidad local d &#39;, almacenada con cada bucket: especifica el número de bits en los que se basa el contenido del bucket. La figura 16.11 muestra un directorio con profundidad global d = 3.

**Hashing Dinámico.** Un precursor del hashing extensible fue el hashing dinámico propuesto por Larson (1978), en el que las direcciones de los cubos eran las n bits de orden superior o n - 1 bits de orden superior, dependiendo del número total de claves perteneciente al cubo respectivo. El eventual almacenamiento de registros en cubos para el hashing dinámico es algo similar al hashing extensible. La mayor diferencia está en la organización del directorio. Mientras que el hashing extensible usa la noción de profundidad global (d bits de alto orden) para el directorio plano y luego combina adyacentes cubos plegables en un cubo de profundidad local d - 1, el hashing dinámico mantiene un directorio estructurado en árbol con dos tipos de nodos:

**Nodos internos que tienen dos punteros:** el puntero izquierdo correspondiente al 0 bit (en la dirección hash) y un puntero derecho correspondiente al 1 bit.

**Nodos de hoja:** estos sostienen un puntero al cubo real con registros.

**Hashing lineal.** La idea detrás del hashing lineal, propuesta por Litwin (1980), es permitir que un archivo hash se expanda y reduzca su número de cubos dinámicamente sin necesitando un directorio.

## Otras organizaciones de archivos primarios

### Archivos de registros mixtos

Las organizaciones de archivos que hemos estudiado hasta ahora suponen que todos los registros de un determinado son del mismo tipo de registro. Los registros pueden ser de EMPLEADOS, PROYECTOS, ESTUDIANTES o DEPARTAMENTOS, pero cada archivo contiene registros de un solo tipo. En la mayoría de las aplicaciones de bases de datos, encontramos situaciones en las que numerosos tipos de las entidades están interrelacionadas de varias maneras, como vimos en el Capítulo 7. Relaciones entre los registros en varios archivos pueden representarse mediante campos de conexión.

Estas organizaciones de archivos generalmente se asignan un área del disco a mantener registros de más de un tipo para que los registros de diferentes tipos puedan ser agrupados físicamente en el disco. Si se espera que se use una relación particular con frecuencia, implementar la relación físicamente puede aumentar el sistema eficiencia en la recuperación de registros relacionados.

### Árboles B y otras estructuras de datos como organización primaria

Se pueden usar otras estructuras de datos para organizaciones de archivos primarios. Por ejemplo, si tanto el tamaño de registro como la cantidad de registros en un archivo son pequeños, algunos DBMS ofrece la opción de una estructura de datos de árbol B como la organización de archivos principal.

## Paralelizar el acceso al disco usando tecnología RAID

Un avance importante en la tecnología de almacenamiento secundario está representado por el desarrollo de RAID, que originalmente representaba matrices redundantes de discos económicos.
El objetivo principal de RAID es igualar las tasas de rendimiento de discos contra los de memoria y microprocesadores.
La solución natural es una gran variedad de pequeños discos independientes que actúan como un solo disco lógico de mayor rendimiento. La división de datos distribuye los datos de forma transparente en varios discos para que aparezcan como un solo disco grande y rápido.

### Mejora de la confiabilidad con RAID

Para una matriz de n discos, la probabilidad de falla es n veces mayor que la de uno disco.
Mantener una sola copia de datos en una matriz de discos de este tipo provocará una pérdida significativa de fiabilidad. Una solución obvia es emplear redundancia de datos para que las fallas del disco puede ser tolerado Las desventajas son muchas: operaciones de E/S adicionales para escritura,cálculo adicional para mantener la redundancia y para recuperarse de errores, y capacidad de disco adicional para almacenar información redundante. Una técnica para introducir redundancia se llama duplicación o sombreado. Los datos se escriben de forma redundante en dos discos físicos idénticos que se tratan como uno disco lógico, cuando se leen los datos, se pueden recuperar del disco con cola, búsqueda y demoras rotacionales. Si un disco falla, el otro disco se usa hasta que primero se repara.

### Organizaciones y niveles RAID

Se definieron diferentes organizaciones RAID basadas en diferentes combinaciones de dos factores de granularidad de la intercalación de datos (rayas) y el patrón utilizado para calcular la información redundante.

**RAID 0:** utiliza el trazado de datos, no tiene datos redundantes y, por lo tanto, tiene la mejor escritura rendimiento ya que las actualizaciones no tienen que duplicarse. Divide los datos de manera uniforme en dos o más discos.

**RAID 1:** usa discos reflejados. En este último, la mejora del rendimiento es posible medianteprogramar una solicitud de lectura en el disco con la búsqueda y rotación más cortas esperadas
retrasar.

**RAID 2:** utiliza redundancia de estilo de memoria mediante códigos Hamming, que contienen bits de paridad para distintos subconjuntos superpuestos de componentes. Por lo tanto, en una versión particular de este nivel, tres discos redundantes son suficientes para cuatro originales discos, mientras que con la duplicación, como en el nivel 1, se requerirían cuatro. Nivel 2 incluye detección y corrección de errores, aunque la detección generalmente no es requerido porque los discos rotos se identifican a sí mismos.

**RAID 3:** utiliza un disco de paridad único que depende del controlador de disco para determinar qué disco ha fallado. Los niveles 4 y 5 usan bandas de datos a nivel de bloque, con el nivel 5 distribuyendo datos e información de paridad en todos los discos.
La reconstrucción en caso de falla del disco es más fácil para el nivel RAID 1. Otros niveles requieren
La reconstrucción de un disco fallido mediante la lectura de varios discos. El nivel 1 se usa para aplicaciones críticas como el almacenamiento de registros de transacciones. Los niveles 3 y 5 son preferidos para el almacenamiento de gran volumen, y el nivel 3 proporciona velocidades de transferencia más altas. Más El uso popular de la tecnología RAID actualmente utiliza el nivel 0 (con franjas), el nivel 1 (con espejo) y nivel 5 con un impulso adicional para la paridad. Una combinación de múltiples RAIDS.

## Arquitecturas modernas de almacenamiento

En esta sección, describimos algunos desarrollos recientes en sistemas de almacenamiento que son convirtidos en una parte integral de la mayoría de las arquitecturas de sistemas de información de la empresa. La interfaz Fibre Channel (FC) es la opción predominante para el almacenamiento redes en centros de datos. A continuación, revisamos algunas de las arquitecturas de almacenamiento modernas.

### Redes de área de almacenamiento

La mayoría de las organizaciones grandes utilizan un concepto llamado redes de área de almacenamiento (SAN). En una SAN, almacenamiento en línea los periféricos se configuran como nodos en una red de alta velocidad y se pueden conectar y separado de los servidores de una manera muy flexible.
Permiten colocar sistemas de almacenamiento a distancias más largas de los servidores y ofrecen diferentes opciones de rendimiento y conectividad.
Las alternativas arquitectónicas actuales para SAN incluyen lo siguiente: punto a punto conexiones entre servidores y sistemas de almacenamiento a través de Fibre Channel; uso de una fibra.

Conmutador de canal para conectar múltiples sistemas RAID, bibliotecas de cintas, etc. a servidores; y el uso de concentradores y conmutadores Fibre Channel para conectar servidores y almacenamiento de sistemas en diferentes configuraciones. Las principales ventajas reclamadas incluyen:

■ Conectividad flexible de muchos a muchos entre servidores y dispositivos de almacenamiento.

utilizando concentradores e interruptores Fibre Channel

■ Separación de hasta 10 km entre un servidor y un sistema de almacenamiento utilizando cables de fibra óptica adecuados

■ Mejores capacidades de aislamiento que permiten la adición sin interrupciones de nuevos periféricos y servidores.

■ Replicación de datos de alta velocidad en múltiples sistemas de almacenamiento. Las tecnologías típicas utilizan la replicación sincrónica para la replicación local y asíncrona para soluciones de recuperación ante desastres (DR).

Las SAN están creciendo muy rápidamente pero aún enfrentan muchos problemas, como combinar opciones de almacenamiento de múltiples proveedores y lidiar con estándares en evolución.

### Almacenamiento conectado a la red

Los dispositivos (NAS) se encuentran entre los dispositivos de almacenamiento que se utilizan para este propósito. Los dispositivos son, de hecho, servidores que no proporcionan ninguno de los servicios de servidor comunes, pero simplemente permita la adición de almacenamiento para compartir archivos. Los dispositivos NAS permiten gran cantidad cantidades de espacio de almacenamiento en el disco duro que se agregarán a una red y pueden hacer que espacio disponible para múltiples servidores sin apagarlos por mantenimiento y actualizaciones. Los dispositivos NAS pueden residir en cualquier lugar de una red de área local (LAN) y puede combinarse en diferentes configuraciones. Un único dispositivo de hardware, a menudo llamado la caja NAS o la cabeza NAS, actúa como la interfaz entre el sistema NAS y los clientes de la red. Estos dispositivos NAS no requieren monitor, teclado o mouse. Uno o

Se pueden conectar más unidades de disco o cinta a muchos sistemas NAS para aumentar el total capacidad. Los clientes se conectan al cabezal NAS en lugar de al almacenamiento individual dispositivos. Un NAS puede almacenar cualquier información que aparezca en forma de archivos, como el correo electrónico, cuadros, contenido web, copias de seguridad del sistema remoto, etc. En ese sentido, los dispositivos NAS se están implementando como reemplazo de los servidores de archivos tradicionales.

Dichos dispositivos suelen admitir niveles RAID 0, 1 y 5.

Las redes de área de almacenamiento (SAN) tradicionales difieren del NAS en varias formas. Específicamente, las SAN a menudo utilizan Fibre Channel en lugar de Ethernet, y una SAN a menudo incorpora múltiples dispositivos de red o puntos finales de forma independiente o privada

LAN, mientras que NAS se basa en dispositivos individuales conectados directamente a los existentes

LAN pública. Mientras que los servidores de archivos de Windows, UNIX y NetWare exigen cada uno ,soporte de protocolo específico en el lado del cliente, los sistemas NAS afirman un mayor funcionamiento en el sistema de independencia de los clientes. En resumen, NAS proporciona una interfaz de sistema de archivos con soporte para archivos en red utilizando protocolos como el sistema de archivos de Internet común (CIFS) o el sistema de archivos de red (NFS).

### iSCSI y otros protocolos de almacenamiento basados en red

Recientemente se ha propuesto un nuevo protocolo llamado iSCSI (SCSI de Internet). Es un protocolo de almacenamiento en bloque como SAN. Permite a los clientes (llamados iniciadores) enviar SCSI comandos a dispositivos de almacenamiento SCSI en canales remotos. La principal ventaja de iSCSI es que no requiere el cableado especial que necesita Fibre Channel y puede correr sobre distancias más largas utilizando la infraestructura de red existente. Al llevar

Comandos SCSI sobre redes IP, iSCSI facilita la transferencia de datos a través de intranets y gestiona el almacenamiento a largas distancias. Puede transferir datos a través de redes de área local (LAN), redes de área amplia (WAN) o Internet.

El almacenamiento iSCSI ha impactado principalmente a las pequeñas y medianas empresas porque de su combinación de simplicidad, bajo costo y la funcionalidad de los dispositivos iSCSI. iSCSI es uno de los dos enfoques principales para la transmisión de datos de almacenamiento a través de redes IP.

### Almacenamiento en niveles automatizado

Otra tendencia en el almacenamiento es el almacenamiento en niveles automatizado (AST), que mueve automáticamente los datos entre diferentes tipos de almacenamiento, como SATA, SAS y unidades de estado sólido (SSD) según la necesidad.

El administrador de almacenamiento puede configurar una política de niveles en la que los datos de uso menos frecuente se mueven a una velocidad más lenta

Las unidades SATA y los datos de uso más frecuente se trasladan a unidades de estado sólido. Esta organización en niveles automatizada puede mejorar enormemente el rendimiento de la base de datos.

EMC tiene una implementación de esta tecnología llamada FAST (almacenamiento en niveles totalmente automatizado) que realiza un monitoreo continuo de la actividad de datos y toma medidas para mover los datos al nivel apropiado según la política.

### Almacenamiento basado en objetos

Bajo este esquema, los datos se administran en forma de objetos en lugar de archivos hecho de bloques. Los objetos llevan metadatos que contienen propiedades que pueden usarse para manejando esos objetos. Cada objeto lleva un identificador global único que se utiliza para localizarlo. No hay necesidad de realizar operaciones de almacenamiento de nivel inferior en términos de gestión de capacidad o tomar decisiones como qué tipo de arquitectura RAID debe usarse para protección contra fallas.

El almacenamiento de objetos también permite una flexibilidad adicional en términos de interfaces: otorga control a las aplicaciones que pueden controlar los objetos directamente y también permite que los objetos ser direccionados en un amplio espacio de nombres que abarca múltiples dispositivos. La replicación y la distribución de objetos también es compatible. En general, el almacenamiento de objetos es idealmente adecuado para el almacenamiento escalable de grandes cantidades de datos no estructurados como Web páginas, imágenes y clips y archivos de audio /video.
