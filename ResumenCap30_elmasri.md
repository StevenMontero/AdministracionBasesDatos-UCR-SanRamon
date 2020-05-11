# Database Security

## Tipos de seguridad

La seguridad de bases de datos es tema y area muy extensos ya que no se limita a aspectos tecnico solamente.Toca areas como:

  * Cuestiones legales y éticas relacionadas con el derecho de acceso a cierta información.
 
 * Problemas relacionados con el sistema, tales como los niveles del sistema en los que varia la seguridad(Nivel de software,Nivel de HardWare ,Nivel del DBMS).
  
  * Cuestiones de política a nivel gubernamental, institucional o corporativo con respecto qué tipos de información no deberían ponerse a disposición del público.
  
  * Categorizar la data en multiples niveles para restringir el acceso a esta de algunas aplicaciones o personas.
  
### Amenazas a la base de datos

Las amenazas a las bases de datos pueden provocar la pérdida o degradación de algunos o todos los objetivos de seguridad comúnmente aceptados como: integridad, disponibilidad capacidad y confidencialidad.

  * Perdida de Integridad: Las amenazas a las bases de datos pueden provocar la pérdida o degradación de algunos o todos los siguientes objetivos de seguridad comúnmente aceptados: integridad, disponibilidad capacidad y confidencialidad.Lo que proboca en la organizacion que la data no sea confiable y lleve la toma de decisiones erroneas.
  
  * Pérdida de disponibilidad: La disponibilidad de la base de datos se refiere a poder hacer que los objetos estén disponibles en todo momento para un
usuario humano o un programa que tiene un derecho legítimo a esos objetos de datos. La pérdida de disponibilidad ocurre cuando el usuario o el programa no pueden acceder a estos objetos.

  * Pérdida de confidencialidad: La confidencialidad de la base de datos se refiere a la protección de
datos de divulgación no autorizada.El impacto de la divulgación no autorizada
de información confidencial puede variar desde la violación de la Ley de Privacidad de Datos
a la puesta en peligro de la seguridad nacional.

**Es importante recordar que el sistema de gestión de bases de datos
solo no puede ser responsable de mantener la confidencialidad, integridad y
disponibilidad de los datos. Ya que este es solo un eslabón mas en la red de aplicaciones que interactuan con los datos.**

Para proteger las bases de datos contra las amenazas discutidas anteriormente, es común implementar cuatro tipos de medidas de control: **control de acceso, control de inferencia, control de flujo,
y encriptación.**

Un DBMS generalmente incluye una autorización y seguridad de la base de datos es responsable de garantizar la seguridad de partes de una base de datos
contra el acceso no autorizado. Ahora es habitual hacer referencia a dos tipos mecanismos de seguridad de bases de datos:

  * **Mecanismos discrecionales de seguridad:** Estos se utilizan para otorgar privilegios a
usuarios, incluida la capacidad de acceder a archivos de datos específicos, registros o campos
en un modo especificado (como leer, insertar, eliminar o actualizar).

  * **Mecanismos de seguridad obligatorios:** Estos se utilizan para imponer niveles múltiples
seguridad clasificando los datos y usuarios en varias clases de seguridad (o
niveles) y luego implementar la política de seguridad apropiada de la organización


### Medidas de control
Se utilizan cuatro medidas de control principales para proporcionar seguridad de los datos en las bases de datos:

  * Control de acceso
  * Control de inferencia
  * Control de flujo
  * Cifrado de datos
  
Un problema de seguridad común a los sistemas informáticos es el de prevenir
personas con acceso al sistema en sí, ya sea para obtener información o para
realizar cambios maliciosos. El DBMS debe incluir disposiciones para restringir el acceso al sistema de base de datos como todo. Esta función, llamada control de acceso, se maneja creando cuentas de usuario
y contraseñas para controlar el proceso de inicio de sesión mediante el DBMS.

Las bases de **datos estadísticas** se utilizan para proporcionar información estadística o resúmenes de
valores basados en varios criterios. Por ejemplo, una base de datos para estadísticas de población
puede proporcionar estadísticas basadas en grupos de edad, niveles de ingresos, tamaño del hogar, educación
niveles de acción y otros criterios. Este tipo de DB que alamacena data sensible debe contar con una seguidad rigurosa de quien accede a la data.

La encriptación se puede utilizar para proporcionar protección adicional para porches sensibles
también de una base de datos. Los datos se codifican usando algún algoritmo de codificación. Esto es tan importante que es unrequisto por ley hacerlo.

### Seguridad de bases de datos y el DBA

El DBA es el actor principal en el manejo y autoridad sobre la DB por lo que tiene muchas responsabilidades que van desde otorgar privilegios a los usuarios que necesitan usar el sistema , clasificar a los usuarios y
datos de acuerdo con la política de la organización. El DBA tiene una cuenta super usuario para poder hacer todas estas tareas dentro del DBMS esta cuenta tiene comandos de orogar y revocar privilegios.
Los privilegios de las cuentas de los DBA son:

1. **Creación de cuenta** Esta acción crea una nueva cuenta y contraseña para un
usuario o un grupo de usuarios para permitir el acceso al DBMS.
2. **Concesión de privilegios** Esta acción permite que el DBA otorgue ciertos privilegios
a ciertas cuentas.
3. **Revocación de privilegios** Esta acción permite que el DBA revoque (cancele) privilegios que se otorgaron previamente a ciertas cuentas.
4. **Asignación de nivel de seguridad** Esta acción consiste en asignar cuentas de usuario a
el nivel de autorización de seguridad apropiado.

### Control de acceso, cuentas de usuario y auditorías de bases de datos

Cada vez que una persona o un grupo de personas necesita acceder a un sistema de base de datos, el
individuo o grupo primero debe solicitar una cuenta de usuario. El DBA luego creará un
nuevo número de cuenta y contraseña para el usuario si existe una necesidad legítima de
acceder a la base de datos. El usuario debe iniciar sesión en el DBMS ingresando la cuenta
número y contraseña cuando se necesita acceso a la base de datos. El DBMS verifica que
el número de cuenta y la contraseña son válidos; si es así, el usuario puede usar
DBMS y para acceder a la base de datos. Los programas de aplicación también pueden considerarse
usuarios y deben iniciar sesión en la base de datos. El sistema de base de datos también debe realizar un seguimiento de todas las operaciones en la base de datos que están
aplicado por un determinado usuario en cada sesión de inicio de sesión.
Si se sospecha cualquier alteración de la base de datos, se realiza una auditoría de la base de datos, que
consiste en revisar el registro para examinar todos los accesos y operaciones aplicados a
base de datos durante un cierto período de tiempo. Cuando una operación ilegal o no autorizada es
encontrado, el DBA puede determinar el número de cuenta utilizado para realizar la operación.

### Datos confidenciales y tipos de revelaciones
Algunas bases de datos pueden contener solo datos confidenciales, mientras que otras bases de datos pueden no contener datos confidenciales.Tambien pueden que tengan datos publicos y confidenciales en esta situacion se tienen que cubrir con por un control de acceso.
Los factores que pueden hacer que los datos se clasifiquen como sensibles son:

 * **Inherentemente sensible:** El contenido de esta informacion puede llegar a revelar detalles muy privados o sensibles de una persona o empresa. Por ejemplo, el salario de una persona o que
el paciente tiene VIH / SIDA.

* **De una Fuente Sensible:** La fuente de los datos puede indicar la necesidad de secreto: por ejemplo, un informante cuya identidad debe mantenerse en secreto.

* **Declarado Sensible:** El propietario de los datos puedo espesificar que son datos sensibles.

* **Un atributo sensible o registro sensible:** El atributo o registro particular
puede haber sido declarado sensible, por ejemplo, el atributo de salario de un
empleado o el registro del historial salarial en una base de datos de personal.

* **Sensible en relación con los datos divulgados previamente:**  Algunos datos pueden no ser
sensible por sí mismo, pero se volverá sensible en presencia de algún otro datos.

El DBA y el administrador de seguridad tienen la resposabilidad de hacer cumplir las politicas de seguridad.
Se deben considerar varios factores antes de decidir si es seguro revelar el
datos. Los tres factores más importantes son la disponibilidad de datos, la aceptabilidad del acceso,
y garantía de autenticidad.

1.**Disponibilidad de datos:** Si un usuario está actualizando un campo, este campo se vuelve inactivo
Los usuarios que no puedan acceder y otros usuarios no deberían poder ver estos datos. Este bloqueo
es solo temporal y solo para garantizar que ningún usuario vea datos inexactos.

2. **Aceptabilidad de acceso:** Los datos solo deben revelarse a usuarios autorizados.El administrador de la base de datos también puede denegar el acceso a una solicitud de un usuario incluso si el
la solicitud no accede directamente a un elemento de datos confidenciales, porque
los datos solicitados pueden revelar información sobre los datos confidenciales que
no está autorizado a tener.

3.**Garantía de autenticidad:** Antes de otorgar acceso, ciertas características externas
También se pueden considerar las estadísticas sobre el usuario. Por ejemplo, un usuario solo puede
tener acceso permitido durante las horas de trabajo.

Las definiciones de seguridad vs precisión:

 * **Seguridad:** Son los medios para garantizar que los datos se mantengan a salvo de la corrupción y que
el acceso al mismo está adecuadamente controlado. Proporcionar seguridad significa divulgar solo
datos no sensibles y rechazar cualquier consulta que haga referencia a un campo sensible.

 * **Precisión:** Es poder proteger todos los datos confidenciales al divulgar o hacer disponible la mayor cantidad posible de datos no sensibles. 
 
 ### Relación entre seguridad de la información y privacidad de la información
Decidir cómo diseñar las consideraciones de privacidad en tecnología para el futuro incluye
dimensiones filosóficas, legales y prácticas. Hay una superposición considerable
entre cuestiones relacionadas con el acceso a los recursos (seguridad) y cuestiones relacionadas con la aprobación
del uso privado de la información (privacidad).
La seguridad en la tecnología de la información se refiere a muchos aspectos de la protección de un sistema del uso no autorizado, incluida la autenticación de usuarios, el cifrado de información, control de acceso, políticas de firewall y detección de intrusos.
El concepto de privacidad va más allá de la seguridad.Privacidad examina qué tan bien se usa la información personal que el sistema adquiere sobre un usuario y que cumpla con la privadicidad conforme a los supuestos explícitos o implícitos con respecto a ese uso. Desde la perspectiva del usuario final, la privacidad puede considerarse desde
dos perspectivas diferentes: prevenir el almacenamiento de información personal versus asegurar uso apropiado de la información personal.
 
 **Una definición simple pero útil de privacidad es la capacidad de las personas para controlar los términos bajo los cuales se adquiere y utiliza su información personal.**
 
## Control de acceso discrecional basado sobre la concesión y revocación de privilegios 
El método típico de imponer el control de acceso discrecional en un sistema de base de datos.Muchos DBMS relacionales actuales usan alguna variación de esta técnica. La idea principal es incluir declaraciones en el lenguaje de consulta que permitan el DBA y usuarios seleccionados para otorgar y revocar privilegios.

### Tipos de privilegios discrecionales
El identificador de autorización se utiliza para referirse, en términos generales, a una cuenta de usuario (o grupo de cuentas de usuario).El DBMS debe proporcionar acceso selectivo a cada relación en la base de datos en función de cuentas específicas. Las operaciones también pueden ser controladas; por lo tanto, tener una cuenta no necesariamente da derecho al titular de la cuenta a toda la funcionalidad proporcionada por el DBMS. 

Informalmente, hay dos niveles para asignar privilegios para usar el sistema de base de datos:


* El nivel de la cuenta. En este nivel, el DBA especifica los privilegios particulares que cada cuenta posee independientemente de las relaciones en la base de datos.

* El nivel de relación (o tabla). En este nivel, el DBA puede controlar el privilegio de acceder a cada relación o vista individual en la base de datos.

Los privilegios a nivel de cuenta se aplican a las capacidades proporcionadas a la misma cuenta y pueden incluir el privilegio CREATE SCHEMA o CREATE TABLE, para crear un esquema o una relación base; el privilegio CREATE VIEW; el privilegio ALTER, para aplicar cambios de esquema como agregar o eliminar atributos de las relaciones; el privilegio DROP, para eliminar relaciones o vistas; el privilegio MODIFICAR, para insertar, eliminar o actualizar tuplas; y el privilegio SELECT, para recuperar información de la base de datos mediante una consulta SELECT.

El segundo nivel de privilegios se aplica al nivel de relación, que incluye la relación base
relaciones y relaciones virtuales (vista). Los privilegios en el nivel de relación especifican para cada usuario las relaciones individuales en las que se puede aplicar cada tipo de comando. 
Para controlar la concesión y revocación de privilegios de relación, cada relación R en un
a la base de datos se le asigna una cuenta de propietario, que normalmente es la cuenta que se utilizó
cuando la relación se creó en primer lugar.

En SQL, los siguientes tipos de se pueden otorgar privilegios a cada relación individual R:

* **Privilegio SELECT (recuperación o lectura)** le permite a la cuenta a cosultar datos de la DB.
* **Privilegios de modificación en R** Esto le da a la cuenta la capacidad de modificar las tuplas de R. En SQL, esto incluye tres privilegios: ACTUALIZAR, ELIMINAR e INSERTAR.
* **Privilegio de referencias en R** Esto le da a la cuenta la capacidad de referenciar
(o consulte) una relación R al especificar restricciones de integridad.

### Especificación de privilegios mediante el uso de vistas
El mecanismo de puntos de vista es un mecanismo de autorización discrecional importante por derecho propio. Por ejemplo, si el propietario A de una relación R quiere que otra cuenta B pueda recuperar solo algunos campos de R, entonces A puede crear una vista V de R que incluya solo esos atributos y luego otorgar SELECT en V a B.

### Revocación de privilegios
En algunos casos, es conveniente otorgar un privilegio a un usuario temporalmente.Por lo tanto, se necesita un mecanismo para revocar privilegios. En SQL, se incluye un comando REVOKE con el propósito de cancelar privilegios. 

### Propagación de privilegios utilizando la opción GRANT
Siempre que el propietario A de una relación R otorgue un privilegio sobre R a otra cuenta B,el privilegio se puede otorgar a B con o sin la OPCIÓN DE CONCESIÓN. GRANT OPTION significa que B también puede otorgar ese privilegio sobre R a otro
cuentas 

### Especificación de límites en la propagación de privilegios
Se han desarrollado técnicas para limitar la propagación de privilegios, aunque aún no se han implementado en la mayoría de los DBMS y no forman parte de SQL.

Limitar la propagación **horizontal** a un número entero i significa que una cuenta B dada la OPCIÓN DE OTORGAMIENTO puede otorgar el privilegio a como máximo i cuentas.

La propagación **vertical** es más complicada; limita la profundidad de la concesión de privilegios. Otorgar un privilegio con una propagación vertical de cero es equivalente a otorgar el privilegio sin OPCIÓN DE CONCESIÓN. Si la cuenta A otorga un privilegio a la cuenta B con la propagación vertical establecida en un número entero j> 0, esto significa que la cuenta B tiene la OPCIÓN DE CONCESIÓN en ese privilegio, pero B puede otorgar el
privilegio a otras cuentas solo con una propagación vertical menor que j. 

## Control de acceso obligatorio y basado en roles de control de acceso para seguridad multinivel
Las clases de seguridad típicas son secreto superior (TS), secreto (S), confidencial (C) y no clasificado (U), donde TS es el nivel más alto y U el más bajo. El modelo usado comúnmente para seguridad multinivel, conocido como el modelo Bell-LaPadula.

Se aplican dos restricciones al acceso a los datos en función de las clasificaciones de sujeto / objeto:

1. Un sujeto S no tiene acceso de lectura a un objeto O a menos que la clase (S) ≥ clase (O). Esto se conoce como la propiedad de seguridad simple.
2. Un sujeto S no puede escribir un objeto O a menos que clase (S) ≤ clase (O). Esto se conoce como la propiedad estrella (o propiedad *).

### Comparing Discretionary Access Control and Mandatory Access Control
Las políticas obligatorias aseguran un alto grado de protección de una manera, evitan cualquier flujo ilegal de información. Por lo tanto, son adecuados para tipos de aplicaciones militares y de alta seguridad, que requieren un mayor grado de protección. Sin embargo, las políticas obligatorias tienen el inconveniente de ser demasiado rígidas, ya que requieren una clasificación estricta de sujetos y objetos en niveles de seguridad y, por lo tanto, son aplicables a pocos entornos y colocan una carga adicional.
La jerarquía de roles se puede implementar de la siguiente manera:

<code>GRANT ROLE full_time TO employee_type1</code>
 
<code>GRANT ROLE intern TO employee_type2</code>

### Control de acceso basado en roles
El control de acceso basado en roles (RBAC) surgió rápidamente en la década de 1990 como una tecnología comprobada para administrar y hacer cumplir la seguridad en sistemas empresariales a gran escala.
Los roles se pueden crear utilizando CREATE ROLE y DESTROY ROLE.Los comandos GRANT y REVOKE se puede utilizar para asignar y revocar privilegios de roles.RBAC puede usarse con controles de acceso discrecionales y obligatorios tradicionales.
La jerarquía de roles en RBAC es una forma natural de organizar roles para reflejar la organización.
En otras palabras, si un usuario tiene un rol, el usuario automáticamente tiene roles más bajos en la jerarquía. La definición de una jerarquía de roles implica elegir el tipo de jerarquía y los roles, y luego implementar la jerarquía otorgando roles a otros roles.



**Seguridad basada en etiquetas y control de acceso a nivel de fila**

En el control de acceso a nivel de fila, cada fila de datos recibe una etiqueta, que se usa para almacenar información sobre la sensibilidad de los datos. El control de acceso a nivel de fila proporciona mayor granularidad de seguridad de datos al permitir que se establezcan los permisos para cada fila y no solo para la tabla o columna. Cada usuario tiene una identidad en seguridad basada en etiquetas. La identidad de este usuario se compara con la etiqueta asignada a cada fila para determinar si el usuario tiene acceso para ver el contenido de esa fila. Se pueden recibir privilegios de dos cuentas diferentes.


Los requisitos de seguridad de la etiqueta se aplican sobre los requisitos de acceso de control discrecional para cada usuario, Por lo tanto, el usuario debe cumplir los requisitos de acceso de control discrecional y luego la etiqueta requisitos de seguridad para acceder a una fila. i la cuenta de propietario A ahora revoca el privilegio otorgado a B, todos los privilegios que B propagó en función de ese privilegio deberían revocarse automáticamente por el sistema.



**Control de acceso XML**

Con el uso mundial de XML en aplicaciones comerciales, y científicas, es indispensable pensar en métodos de autenticación para el acceso de aplicaciones que se conectan a través de la red por medio de archivos XML al almacenamiento en bases de datos, para que esto se puede llevar a cabo se necesita cumplir con cierta especificaciones como sintaxis para asociar firmas criptográficas, ya que un método a implementar seria firmas digitales o encriptación, también otras especificaciones para el uso de estos archivos con las bases de datos es, pensar en transformaciones de contraseñas, para asegurar que dos instancias produzcan el mismo resumen y puedan coincidir estas contraseñas inclusive con cambios ligeros como espacios, por ultimo otro aspecto importante es pensar en el procesamiento de la información y que esta no sea vea comprometida y siga siendo de carácter confiable y disponible.

**Políticas de acceso de control por la web y aplicaciones móviles**

En la actualidad, un gran porcentaje del comercio es a través de la web, e-comerce, donde por supuesto el uso de las bases de datos es indispensable, pero tiene una gran desventaja y es que las amenazas aumenta, esto hace que sea un desafío mayor controlar el acceso a los datos, ya que juegan un papel muy importante no solo los datos sino los procesos y el conocimiento, hay más elementos incorporados en la red que deben de protegerse y por otro lado el e-comerce aumenta el número de datos sensibles como tarjetas de crédito, datos que deben de protegerse por ley y no permitirse el acceso no autorizado, recordemos que existe una cantidad mayor de aplicaciones que se pueden conectar y extraer esa información, por eso se deben establecer políticas de seguridad muy claras de quien puede o no acceder a esa información.

Se espera que XML desempeñe un papel clave en el control de acceso para aplicaciones de comercio electrónico porque se está convirtiendo en el lenguaje de representación común para documentos de intercambio a través de la Web, y también se está convirtiendo en el idioma para el comercio electrónico. Por lo tanto, existe la necesidad de asegurar las representaciones XML mediante mecanismos de control de acceso específicamente diseñados para la protección de documentos XML. Y, por otro lado, la información de control de acceso (es decir, acceso políticas de control y credenciales de usuario) pueden expresarse utilizando el propio XML.

**Inyección SQL**

Es el ataque o amenaza más común al base de datos. Consiste en introducir líneas de texto que se envían a través de la web, cuando se realiza una consulta a una base de datos, por medio de los comandos se pueden inyectar otras consultas que afectan la integridad, intentan acceso no autorizado o incluso deniega el servicio a otros usuarios.

Otros ataques: **Escalada de privilegios no autorizada**. Este ataque se caracteriza por un individuo intentando elevar su privilegio atacando a vulnerables puntos en los sistemas de bases de datos. **Abuso de privilegios**. Este ataque es realizado por un usuario privilegiado. Por ejemplo, un administrador al que se le permite cambiar la información del estudiante puede usar este privilegio de actualizar las calificaciones de los estudiantes sin el permiso del instructor. **Denegación de servicio**. Es un intento de hacer recursos no disponibles para sus usuarios previstos. Es una categoría de ataque de acceso a las aplicaciones o datos de la red denegando a los usuarios previstos por desbordando del búfer o consumiendo recursos. **Autenticación débil.** Si el esquema de autenticación del usuario es débil, un atacante puede hacerse pasar por la identidad de un usuario legítimo al obtener sus credenciales de inicio de sesión.

Tipos de ataques de inyección: **Manipulación SQL** cambian la consulta SQL reemplazando por otras clausulas la consulta. **Inyección de código:** añade más código a la consulta, para hacer que aparezcan bugs en el sistema y generar una caída de la aplicación. **Inyección de llamada de una función:** este ataque manipula una sentencia SQL haciendo una llamada de una función del sistema de la base de datos, alterando los resultados de la consulta.

**Riesgos asociados con la inyección de SQL **

-   **Huella digital de base de datos.** El atacante puede determinar el tipo de base de datos. utilizado en el backend para que pueda usar ataques específicos de la base de datos que corresponden a debilidades en un DBMS particular.
-   **Denegación de servicio.** El atacante puede inundar el servidor con solicitudes, por lo tanto, negar el servicio a usuarios válidos, o el atacante puede eliminar algunos datos.
-   **Saltarse la autenticación.** Este es uno de los riesgos más comunes, en el que el atacante puede obtener acceso a la base de datos como usuario autorizado y realizar todas las tareas deseadas.
-   **Identificación de parámetros inyectables**. En este tipo de ataque, el atacante reúne información importante sobre el tipo y la estructura de la base de datos de fondo de una aplicación web. Este ataque es posible por el hecho de que el valor predeterminado de la página de error devuelta por los servidores de aplicaciones a menudo es demasiado descriptivo.
-   **Ejecución de comandos remotos.** Esto proporciona a los atacantes una herramienta para ejecutar comandos arbitrarios en la base de datos. Por ejemplo, un usuario remoto puede ejecutar procedimientos y funciones de bases de datos almacenadas desde un SQL remoto interactivo
-   **Realización de escalada de privilegios.** Este tipo de ataque aprovecha las fallas lógicas dentro de la base de datos para actualizar el nivel de acceso.

**Técnicas de protección contra inyección de SQL**

Estas técnicas se logran programando ciertas reglas a los métodos de acceso en la web procedimientos y funciones.

**Enlazar variables (sentencias con parámetros).** Esta técnica consiste en armar las sentencias SQL con parámetros, estos parámetros son establecidos por el usuario.

 Ejemplo:

PreparedStatement stmt = conn.prepareStatement( “SELECT \* FROM EMPLOYEE WHERE EMPLOYEE\_ID=? AND PASSWORD=?”);
 
stmt.setString(1, employee\_id);
 
stmt.setString(2, password);


**Filtro de entrada (validación de entrada):** Esta técnica se puede utilizar para eliminar el escape de cadenas de caracteres de entrada utilizando la función Reemplazar SQL. Por ejemplo, la comilla simple delimitador (‘) se puede reemplazar por dos comillas simples (‘ ’). Los ataques de manipulación se pueden evitar utilizando esta técnica, ya que los personajes de escape se pueden usar para inyectar ataques de manipulación.

**Función de seguridad.** Las funciones de la base de datos, tanto estándar como personalizadas, deben ser restringido, ya que pueden ser explotados en los ataques de inyección de función SQL.

**Introducción a la estadística de seguridad de las bases de datos.**

Las estadísticas de bases de datos se utilizan principalmente para producir estadísticas de poblaciones, pero las bases de datos contienen información confidencial de cada individuo que debe ser protegida, sin embargo, se está permitido obtener esta información para estadísticas de promedios, sumas, desviación estándar, máximos y mínimos.

Una consulta donde se proteja la información confidencial seria estableciendo parámetros de búsqueda, por ejemplo, sexo = ‘M’, se refiere a todos los individuos masculinos, o city = ‘Houston’, los individuos de esa ciudad, con estos datos se pueden crear estadísticas sin obtener datos confidenciales, lo que si se debe restringir es cuando la consulta pide información de un individuo en particular.

Las consultas permitas son las que contienen funciones como sum () count (), min (), max() average(), estándar\_deviation(), estas son llamadas consultas de estadísticas.

Es posible inferir con algunas estadísticas, datos más específicos por eso, se deben aplicar técnicas, como si la consulta devuelve un numero muy pequeño de tuplas, o si la consulta se repite mucho con los mismos datos, se debería denegar, otra técnica es particionar los datos en la base de datos.

**Introducción al flujo de control**

 Este mecanismo de control regula la distribución o flujo de información dentro de la base de datos, los usuario tienen una clasificación o nivel que les permite ya sea hacer lecturas, escrituras o ambas al mismo tiempo, el control de flujo regula quienes pueden solo escribir o leer, por ejemplo, una base de datos militar, un usuario consulta información, pero no se le permite escribir esa información a otra tabla donde tal vez otro usuario sin estos permisos tenga acceso a información confidencial.

Se pueden distinguir dos tipos de flujo: flujos explícitos, que ocurren como consecuencia de instrucciones de asignación, como Y: = f (X1, Xn,); y flujos implícitos, que se generan por instrucciones condicionales, como si f (Xm + 1,…, Xn) entonces Y: = f (X1, Xm).

Los mecanismos de control de flujo deben verificar que solo los flujos autorizados, tanto explícitos como implícito, se ejecutan. Se debe cumplir un conjunto de reglas para garantizar una información segura fluye. Un flujo de información de A a B ocurre cuando la información asociada con A afecta el valor de la información asociado con B. El flujo resulta de operaciones que causan información (transferir de un objeto a otro.) Se deben verificar las relaciones entre dos clases para permitir que la información fluya desde uno al otro.

**Canales encubiertos.**

Un canal encubierto permite que la información pase de un nivel de clasificación superior a un nivel de clasificación inferior por medios inadecuados. Los canales encubiertos se pueden clasificar en dos grandes categorías: **canales de temporización** **y almacenamiento**. La característica distintiva entre los dos es que en un canal de tiempo la información se transmite por la sincronización de eventos o procesos, mientras que los canales de almacenamiento no requieren ninguna sincronización temporal, ya que la información es transmitida por acceder a la información del sistema o lo que de otro modo sería inaccesible para el usuario. Controlar una escritura concurrente de un usuario de nivel superior a uno de nivel inferior, puede evitar que se creen canales encubiertos.

**Cifrado e infraestructura de llaves publicas**

El cifrado es una técnica para aumentar la seguridad de la información, en caso de que alguna de las técnicas anteriores sea burlada y la información llegue a manos de personas equivocadas, el cifrado transforma la información de tal modo que no sea entendible sin descifrar, y para que volvamos a tener los datos originales se necesita aplicar una llave de encriptación única por cada contenido cifrado, que solo la base de datos conoce, para esto se ejecuta una serie de algoritmos que son los que realizan el cifrado y descifrado.

**Cifrado de datos y estándares avanzados de cifrado**

El Estándar de cifrado de datos (DES) puede proporcionar de extremo a extremo cifrado en el canal entre el emisor A y el receptor B. El algoritmo DES se compone de dos de los componentes básicos de encriptación: sustitución y permutación (transposición). deriva su fuerza de la aplicación repetida de estas dos técnicas para un total de 16 ciclos.

El Advanced Estándar de cifrado (AES). Es un algoritmo que tiene un tamaño de bloque de 128 bits, en comparación con el tamaño de 56 bloques de DES, y puede usar claves de 128, 192 o 256 bits, AES presenta más claves posibles, en comparación con DES, y por lo tanto, toma mucho más tiempo para agrietarse.

**Algoritmos de clave simétrica**

Una clave simétrica es una clave que se utiliza tanto para el cifrado como para el descifrado. Usando una clave simétrica, es posible un cifrado y descifrado rápido para la rutina utilizada con datos confidenciales en la base de datos. Un mensaje cifrado con una clave secreta puede ser descifrado solo con la misma clave secreta. El cifrado de claves se llama algoritmos de claves secretas, los algoritmos de clave secreta se usan principalmente para encriptar el contenido de un mensaje, también se les llama algoritmos de cifrado de contenido.

**Cifrado de clave publica (asimétrica)**

Los algoritmos de clave pública se basan en funciones matemáticas en lugar de operaciones en patrones de bits. Abordan un inconveniente de cifrado de clave simétrica, es decir, que tanto el remitente como el destinatario deben intercambiar la clave común de forma segura. En los sistemas de clave pública, se utilizan dos claves para cifrado / descifrado. La clave pública se puede transmitir de forma no segura, mientras que la clave privada no se transmite en absoluto. Estos algoritmos, que usan dos claves relacionadas, una clave pública y una clave privada, para realizar operaciones complementarias (cifrado y descifrado): se conocen como cifrado de clave asimétrica algoritmos.

**Un esquema de cifrado de clave pública, o infraestructura, tiene seis ingredientes:**

**1. Texto sin formato.** Estos son los datos o mensajes legibles que se introducen en el algoritmo como entrada.

**2. Algoritmo de cifrado.** Este algoritmo realiza varias transformaciones en el texto sin formato.

**3. y 4. Claves públicas y privadas.** Estas son un par de claves que han sido seleccionadas de modo que, si uno se usa para cifrar, el otro se usa para descifrar.

**5. Texto cifrado.** Este es el mensaje codificado producido como salida.

**6. Algoritmo de descifrado**. Este algoritmo acepta el texto cifrado y el clave coincidente y produce el texto de formato original.

**Firma digital**

Una firma digital es un ejemplo del uso de técnicas de cifrado para proporcionar autenticación de servicios en aplicaciones de comercio electrónico. Como una firma manuscrita, una firma digital es un medio para asociar una marca exclusiva de un individuo con un cuerpo del texto. La marca debe ser inolvidable, lo que significa que otros deberían poder verificar que la firma proviene del creador. Las firmas digitales deben ser diferentes por cada uso.

**Certificados digitales**

Un certificado digital se utiliza para combinar el valor de una clave pública con la identidad de la persona o servicio que posee la clave privada correspondiente en un documento firmado digitalmente.

La siguiente lista describe toda la información incluida en el certificado:

1. La información del propietario del certificado que está representada por un identificador único conocido como el nombre distinguido (DN) del propietario.

2. El certificado también incluye la **clave pública del propietario.**

3. También se incluye **la fecha de emisión del certificado**.

4. El **período de validez** se especifica mediante las fechas "Válido desde" y "Válido hasta", que están incluidos en cada certificado.

5. La **información del identificador** del emisor se incluye en el certificado.

6. Finalmente, se incluye **la firma digital de la CA** emisora del certificado.

**Problemas de privacidad y preservación**

Para preservar la privacidad de los datos, deberíamos limitar el rendimiento en minería y análisis de datos a gran escala. Las técnicas más utilizadas para abordar esta preocupación es evitar construir almacenes centrales gigantescos como repositorio único de información vital. Otra posible medida es modificar o perturbar intencionalmente los datos. Si todos los datos estuvieran disponibles en un solo almacén, violando solo un único repositorio la seguridad podría exponer todos los datos. Al modificar, perturbar y anonimizar datos, también podemos mitigar riesgos de privacidad asociados con la minería de datos.

**Desafíos para mantener la seguridad de las bases de datos**

El libro menciona tres áreas importantes que los investigadores tratan de abordar en el mantenimiento de la seguridad de los datos ante las amenazas que existen.

**Calidad de datos:** se necesitan técnicas que proporcionen una verificación semántica de integridad más efectiva y herramientas para la evaluación de calidad de datos, basado en técnicas como la vinculación de registros. Recuperación a nivel de aplicación, también se necesitan técnicas para reparar automáticamente datos incorrectos.

**Derechos de propiedad intelectual:** Se han propuesto técnicas de marca de agua para datos relacionales. El objetivo principal de la marca de agua digital es proteger el contenido de personas no autorizadas, duplicación y distribución al permitir la propiedad comprobable del contenido digital.

**Supervivencia de la base de datos:** a pesar de los ataques y amenazas que surgen contra las bases de datos, estas deben continuar con su labor y es trabajo del DBA procurar que esto suceda: por eso hay una serie de esfuerzos que deben seguir.

**Confinamiento.** Tomar medidas inmediatas para eliminar el acceso del atacante a el sistema y aislar o contener el problema para evitar una mayor propagación.

**Evaluación de daños.** Determinar el alcance del problema, incluido el error, funciones y datos corruptos.

**Reconfiguración.** Reconfigurar para permitir que la operación continúe en un entorno de modo degradado mientras continúa la recuperación.

**Reparación.** Recupere datos dañados o perdidos y repare o reinstale el sistema fallido, funciones para restablecer un nivel normal de operación.

**Tratamiento de fallas.** En la medida de lo posible, identifique las debilidades explotadas en el ataque y tome medidas para evitar una recurrencia.

**Seguridad basada en etiquetas de Oracle **

Restringir el acceso a tablas completas o aislar datos confidenciales en bases de datos separadas es una operación costosa de administrar. Oracle Label Security supera la necesidad de tales medidas habilitando el control de acceso a nivel de fila. Cada tabla de base de datos o vista tiene asociada una política de seguridad. Esta política se ejecuta cada vez que la tabla o vista es consultada o alterada. Los desarrolladores pueden agregar fácilmente acceso basado en etiquetas de control para sus aplicaciones.

**Tecnología de bases de datos virtual privada (VPD)**

 El concepto VPD permite que el servidor sea forzado y refinado al control de acceso para una aplicación segura. VPD proporciona control de acceso basado en políticas. Estas políticas de VPD imponen el nivel del objeto para el control de acceso o seguridad a nivel de fila. VPD proporciona una programación de aplicaciones de interfaz (API) que permite adjuntar políticas de seguridad a las tablas de la base de datos o vistas. Usando PL / SQL, un lenguaje de programación host usado en aplicaciones Oracle, los desarrolladores y administradores de seguridad pueden implementar políticas de seguridad con el ayuda de procedimientos almacenados.

**Arquitectura de seguridad de etiquetas**

El DBMS verifica los privilegios DAC del usuario, asegurándose de que él o ella tenga SELECT privilegios sobre la tabla. Luego verifica si la tabla tiene una base de datos privada virtual (VPD) con una política asociada a ella para determinar si la tabla está protegida usando Oracle etiqueta de seguridad. Si es así, la modificación de VPD SQL (cláusula WHERE) se agrega a la instrucción SQL original para encontrar el conjunto de filas accesibles para que el usuario las vea.

**Como las etiquetas de datos y las etiquetas de usuarios trabajan juntos**

La etiqueta de un usuario indica la información a la que se le permite acceder. También determina el tipo de acceso (lectura o escritura) que el usuario tiene sobre esa información. la etiqueta de la fila muestra la sensibilidad de la información que contiene la fila, así como la propiedad de la información. Cuando una tabla en la base de datos tiene una etiqueta basada en acceso asociado a él, solo se puede acceder a una fila si la etiqueta del usuario cumple con ciertos criterios definidos en las definiciones de políticas. El acceso se otorga o deniega en función del resultado de comparar la etiqueta de datos y la etiqueta de sesión del usuario.

 
 
 
 
