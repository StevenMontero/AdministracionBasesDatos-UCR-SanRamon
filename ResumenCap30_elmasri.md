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


