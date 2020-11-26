# Documento de requerimientos

## Introducción

### Propósito

El proyecto consiste en desarrollar un sistema que permita a los alumnos del Instituto Tecnológico Autónomo de México (ITAM) comunicarse con sus profesores y los demás 
alumnos del ITAM. Para este proyecto lo más importante es estabilidad, entonces la aplicación debe de estar corriendo en el servidor 24/7.

### Convenciones del documento

En el presente trabajo para hacerlo atractivamente visual se presentan párrafos en forma de listas con viñetas, para enumerar y dejar en claro los requerimientos, 
objetivos y características de cada sección respectivamente. 

### Audiencia

Todos los miembros de la comunidad ITAM: alumnos, profesores y  personal administrativo.

### Scope

* El sistema permitirá la comunicación interna entre los miembros de la comunidad asegurando un ambiente seguro y adecuado para el desarrollo de actividades 
universitarias.  
* Impulsar a que el lenguaje que se use para comunicarse sea apropiado.
* Evitar que se manden mensajes no adecuados.
* Posibilitar la organización de tipos de chats en directorios: directorio de chats con alumnos, profesores, grupos de la materia, grupos estudiantiles, personal 
administrativo, rectoría.
* Habilitar servicios que el Instituto da por Whatsapp tales cómo la línea origen. 
### Referencias
 * Material de clase de Ingeniería de software en el ITAM.
 * Material de clase de Análisis y diseño de sistemas de información en el ITAM.
 
## Descripción General

  ### Perspectiva del producto
  
  El Instituto Tecnológico Autónomo de México necesita un sistema que permita una comunicación eficiente y adecuada entre los miembros de la comunidad. 
La necesidad existía pero la prioridad del desarrollo de tal plataforma aumentó al pasar a un formato remoto a causa de una pandemia global imprevista.
El presente documento analiza los requerimientos funcionales del proyecto.
Se desarrollará un web-app con una buena adaptación a formato móvil permitiendo que la plataforma de chats sea lo más accesible, buscaremos que el UX sea parecido a lo 
que todos están acostumbrados al usar plataformas del estilo de whatsapp, telegram. 

### Funcionalidades

 * Los miembros de la comunidad podrán iniciar sesión con sus credenciales usadas para Comunidad ITAM.
* Los chats tendrán habilitado un intérprete de LaTex. 
* Los usuarios podrán enviar mensajes a miembros de la comunidad.
* Los chats se organizan predeterminadamente en 4 carpetas: alumnos, profesores, administradores y grupos de materias en curso. 
* Se podrán crear nuevos directorios para organizar chats.
* Los mensajes serán preprocesados para asegurar que el lenguaje sea adecuado y los horarios de comunicación se apeguen lo más posible al horario laboral. 
* Los usuarios tendrán un perfil básico en el que podrán añadir una foto de perfil y una breve descripción.
* Los usuarios podrán crear grupos nuevos.


### Tipos de usuario y características
  
 * Estudiantes
    * Se refiere a los estudiantes del ITAM, pueden mandar mensajes a cualquier miembro de la comunidad. Tendrá candados en envíos de mensajes a profesores y personal 
    administrativo. La creación de grupos está habilitada.

* Profesores
  * Profesores del ITAM, son administradores de los grupos de las materias que imparten y pueden crear grupos.

* Personal Administrativo
  * Es el personal administrativo del ITAM en todos los departamentos i.e: servicios escolares, servicios financieros, rectoría, vinculación internacional, admisiones, 
  servicio social
  
### Entorno operativo
  
  Este sistema debe de existir en los servidores de datos y servidores web del ITAM. La base de datos con la que debe de interactuar es una BD relacional de Oracle 
  montada en servidores físicos dentro del ITAM. Este sistema debe de interactuar con los otros sistemas del ITAM, como Canvas, Microsoft Teams y Comunidad ITAM.
  
### Restricciones de Diseño e implementación
  
  * Este sistema debe de correr en paralelo con los otros sistemas del ITAM, lo que puede limitar el espacio que puede ocupar. 
  * Se debe de poder comunicar con otros sistemas que no están actualizados, los que requieren protocolos específicos. 
  * Se deben usar los sistemas y hardware ya existentes dentro del ITAM, lo que incluye una base de datos de Oracle montada en servidores físicos. 
  * El personal técnico del ITAM se debe de hacer responsable de manejar y mantener el sistema.
  
### Documentación de usuario

  * Manual de estudiantes: es un instructivo para el uso del sistema por parte de los alumnos.
  * Manual administrativo: es un manual para el uso del sistema por parte de los directores de departamento y el personal administrativo técnico.
  * Documentación: es la información necesaria para entender las partes del sistema y su funcionalidad, para poder reparar errores y agregar funcionalidad.
  
### Supuestos y dependencias
  * Se asume que los usuarios estarán de acuerdo con las del sistema que apuntan a grear un ambiente seguro y saludable.
  * Se asume que todo miembro de la comunidad tiene acceso a una dispositivo con conexión a internet. 
  * Se asume que únicamente podrán usar el sistema los alumnos, profesores y administradores activos durante el semestre en cuestión.
  * Se asume que existe suficiente espacio en los servidores físicos para el manejo correcto de este sistema.
  * Se asume que se puede hacer un sistema que se comunique de manera automática con Canvas y Microsoft Teams.
  
## Requerimientos de interfaces externas
  ### Interfaces de Usuario. 
  * Interfaz de log-in:
    * Es la misma para todos los usuarios.
    * Debe de recibir nombre de usuario y contraseña, verificar y dar el acceso correspondiente.
  * Interfaces de usuarios
    * Inicio de sesión.
    * Cambio de contraseña (te redirige a comunidad).
    * Ventana de chats.
    * Vista de cada chat.
    * Vista de creación de grupos.
    * Vista de perfil del usuario.
  ### Interfaces de Hardware
  Se usarán los servidores de IBM ubicados en el ITAM. El cuarto de servidores está ubicado en el primer piso del edificio de ingenierías. Los protocolos e interfaces. 
  Para poder levantar los servicios únicamente se necesita una computadora, preferentemente con sistema operativo debian. Se necesitarán discos duros, procesadores y 
  conexiones al centro de datos del alumno. Todo lo anterior está disponible en el cuarto de servidores del ITAM manejado por el departamento académico de sistemas.
  ### Interfaces de Software
  El usuario necesitará un navegador moderno o un smartphone.  

  Del lado del servidor se necesitará acceso a:

  * Base de datos del Instituto.
    * Se necesita acceso a los grupos y a información básica de toda la comunidad. Se debe crear una nueva BD para almacenar una parte de las conversaciones entre los 
    usuarios. (Nota: Se almacenarán las conversaciones que se tengan entre miembros de la comunidad durante 1 semestre escolar. Es necesario para que los usuarios 
    accedan a los chats desde dispositivos distintos únicamente usando su usuario y contraseña de comunidad.) La nueva base será no relacional y se usará MongoDB. 
  * Claves de acceso ssh al cuarto de servidores.
  * Sistema operativo debian, preferentemente Ubuntu 20.x
  
  ### Interfaces de Comunicación
  La comunicación de los usuarios con la plataforma será por medio de HTTPS. Los usuarios necesitarán un navegador moderno. El sistema recibirá solicitudes GET y POST.
  
  Web Forms
  
  * Inicio de sesión
    * Un form con dos campos, nombre de usuario y contraseña. Verificará a los usuarios y dará acceso a la plataforma.
  * Cambio de contraseña (te redirige a comunidad).
    * Un form con 2 campos para guardar y confirmar la nueva constraseña
  * Ventana de chats.
    * Form para buscar miembros de la comunidad por nombre o correo
    * From para Cambiar de directorio de chats.
    * Form para ingresar a uno de los chats existentes.
    * Botón para entrar a perfil del usuario en la sesión  
  * Vista de cada chat.
    * Form para enviar mensaje. 
    * Botón de regreso a chats generales
  * Vista de creación de grupos.
    * Form para agregar miembros a un grupo. Habilidad de poner una breve descripción del grupo.
  * Vista de perfil del usuario.
    * Form para entrar a los espacios dedicados a cada uno de los cursos inscritos/impartidos por el usuario.
## Features del sistema

### Login y cambio de contraseña
#### Descripción y prioridad

Prioridad 2
Permitirá a los usuarios iniciar sesión y gestionar su contraseña. Es muy importante pues la comunicación entre los miembros de la comunidad debe de ser 
privada, la seguridad es vital. 

#### Secuencias de Respuesta
El usuario entrará a la página y verá un inicio de sesión normal y un botón de cambios de contraseña. 
    
* Para el inicio de sesión normal, si el usuario tiene las credenciales correctas se dará acceso a la plataforma. Nota: en caso de tener 2FA activado, el usuario verá 
una segunda página en la que deberá ingresar el código de verificación.
* Para el cambio de contraseña, el usuario recibirá un correo electrónico con una key con autorización para efectuar el cambio

#### Requerimientos Funcionales 
* **REQ-1:** La contraseña deberá cumplir los requisitos de tener más de 8 caracteres y utilizar mayúsculas, minúsculas y algún número o símbolo. Esto se hace para asegurar que las contraseñas sean seguras.
* **REQ-2:** El sistema deberá utilizar hashing (sha-256) para guardar las contraseñas en la base de datos. De esta forma, nadie tiene acceso a la contraseña excepto el usuario.



### Colmi-Bot

#### Descripción y prioridad
Prioridad 3
Los usuarios tendrán acceso a un chatbot que los guiará en trámites administrativos dentro del ITAM (i.e: Cómo dar una baja, qué hacer si tengo una falta en el 
reglamento, cómo iniciar mi servicio social, qué debo hacer si estoy por comenzar mi tesis.) Los usuarios podrán preguntar al bot qué tareas hay en un grupo y quién está 
en ese grupo.

#### Secuencias de Respuesta
Los usuarios entrarán al chatbot desde su menú de chats y podrán iniciar una conversación.
* Si el usuario es alumno, para poder iniciar una conversación con algún administrativo deberá ser guiado por el bot hacia la persona o el departamento correcto. Lo 
anterior para evitar que los administrativos tengan que redirigir a alumnos a otras áreas. 
* Para que el bot pueda contestar acerca de las tareas dejadas en un grupo, el administrador de la materia (profesor) deberá habilitar la sincronización del bot con el 
material. 


#### Requerimientos Funcionales 
* **REQ-1:**  Contestar a preguntas de índole académica, en caso de no saber la respuesta que el bot caiga en un intent default y pregunte al usuario si quiere que se 
emita un ticket con su pregunta para que se le haga seguimiento de manera particular por algún funcionario del ITAM. 

* **REQ-2:** Dirigir correctamente a los alumnos y crear conversaciones administrador-alumno para la mayoría de los trámites. En caso de que sea únicamente una duda 
sobre el trámite, el bot deberá reconocer el intent y abstenerse de crear conversaciones innecesarias. Las conversaciones creadas de índole administrador-alumno 
únicamente podrán enviar mensajes en días hábiles durante el horario laboral.  

* **REQ-3:** Dirigir correctamente a los alumnos y crear conversaciones administrador-alumno para la mayoría de los trámites. En caso de que sea únicamente una duda 
sobre el trámite, el bot deberá reconocer el intent y abstenerse de crear conversaciones innecesarias.




### Chats

#### Descripción y prioridad
Prioridad 1
Los miembros de la comunidad podrán comunicarse vía mensaje dentro de un ambiente sano y puramente académico. 

#### Secuencias de Respuesta
En la página de chats los alumnos verán los directorios de chats por default y se mostrarán en pantalla los chats del directorio seleccionado. 
* Es la página default después del inicio de sesión.
* Al cambiar de directorio de chats deben cambiarse los chats que se muestran. 
* Al seleccionar un chat cambiará la pantalla y se renderiza la conversación del chat elegido.
* Dentro de cada chat se podrán enviar mensajes de texto y archivos.
* Para salir de un char habrá un botón en la esquina superior izquierda. 


#### Requerimientos Funcionales 
* **REQ1:** Los chats alumno-administrativo y alumno-profesor serán bloqueados durante horarios no escolares pero se podrán activar si el profesor o administrativo lo 
desea. 

* **REQ2:** Dentro de los chats se podrán enviar archivos pdf e imágenes en formato jpg y jpeg. También podrás mandar mensajes que se renderizan a LaTeX. 

* **REQ3:** Se podrán reportar mensajes que vayan en contra de los principios establecidos por el instituto, esto para promover una convivencia sana y puramente 
académica. 
* **REQ4:** En los chats alumno-alumno, antes de poder mandar un mensaje se deberá enviar una solicitud de mensaje a la segunda parte involucrada. 


### Grupos

#### Descripción y prioridad
Prioridad 3
Se podrán crear grupos entre los miembros de la comunidad.


#### Secuencias de Respuesta
Estando en la pantalla de chats habrá una opción de crear grupos y directorios nuevos.
* Al intentar crear un grupo, el usuario entrará a una pantalla que permitirá agregar a los miembros y describir brevemente el grupo.
* Al crear el grupo, este se colocará en un nuevo directorio de chats. Los usuarios podrán cambiar al grupo de directorio según les convenga. 


#### Requerimientos Funcionales 

* **REQ1:** Al crear un grupo, cada uno de los miembros añadidos recibirán un mensaje preguntando si desean formar parte de el grupo de mensajes.

* **REQ2:** Todos los requerimientos de chats aplican a los grupos. 

* **REQ3:** Si hay un profesor o administrativo en el grupo las reglas de horario laboral y días hábiles aplican, también podrán ser desactivadas si el 
profesor/administrador lo desea.



### Directorios de Chats

#### Descripción y prioridad
Prioridad 2
Dentro de la pantalla principal habrá directorios/carpetas en las que cad usuario podrá
organizar los chats o grupos que tenga. 

#### Secuencias de Respuesta
Estando en la pantalla de chats habrá una opción para crear directorios nuevos. Se podrán cambiar chats de carpeta y poner chats on dos o hasta tres carpetas distintas.  
* Al intentar crear un grupo, el usuario entrará a una pantalla que permitirá agregar a los miembros y describir brevemente el grupo.
* Al crear el grupo, este se colocará en un nuevo directorio de chats. Los usuarios podrán cambiar al grupo de directorio según les convenga.

#### Requerimientos Funcionales 
* **REQ1:** Al crear un grupo, cada uno de los miembros añadidos recibirán un mensaje preguntando si desean formar parte de el grupo de mensajes.

* **REQ2:** Todos los requerimientos de chats aplican a los grupos. 

* **REQ3:** Si hay un profesor o administrativo en el grupo las reglas de horario laboral y días hábiles aplican, también podrán ser desactivadas si el 
profesor/administrador lo desea.

## Otros requerimientos No Funcionales 
### Requisitos de desempeño
Este sistema se debe de poder adaptar para que en períodos determinados pueda recibir más de cinco mil usuarios concurrentes que van a enviar y recibir mensajes usando 
el sistema, aún cuando en promedio va a tener menos de mil usuarios concurrentes, esto es solo para tener un buen margen de error 
     
### Requisitos de confiabilidad 
El aumento de la complejidad de autenticación del software garantiza la seguridad del sistema. Se pueden utilizar enfoques de verificación formales para probar el 
software; sin embargo, incluso el software probado y estresado puede tener problemas. Se usarán logs en el sistema para avisar a los administradores en caso de encontrar 
algún intento de robo de datos. 

### Requisitos de seguridad
Si vamos a manejar y almacenar datos y conversaciones privadas de cada miembro de la comunidad. La seguridad física y la seguridad a nivel informático es importante, es 
decir, si pensamos usar los servidores del ITAM, es necesario contemplar una restricción de acceso al personal e implementar un plan de backup para los datos en caso de 
cualquier falla. Así como el mantenimiento de los servidores:
* Control de humedad y temperatura
* Aire acondicionado 

Mientras que la seguridad a nivel informático consistirá en aplicar barreras de seguridad que resguarden la información, de tal manera que se pueda evitar el robo, 
copia, alteración y/o difusión de los datos sin autorización , para ello es importante tener barreras de acceso a cada módulo.

En conclusión en cuanto a seguridad es importante proteger la información, como todo sistema informático:
* Confidencialidad
  * Acceso solo a usuarios autorizados
* Integridad
  * Permisos para modificar la BD sólo para usuarios autorizados. (envío de mensajes)
* Disponibilidad 
  * Los recursos estarán disponibles solo para usuarios autorizados.
### Atributos de callidad del Software 
Para garantizar la calidad de nuestro servicio, es necesario tener en cuenta la disponibilidad de la plataforma en las fechas que son necesarias, durante un semestre en 
curso, para ello se realizarán pruebas funcionales. 
### Reglas de negocio 
* Solo los miembros de la comunidad podrán entrar a mandar mensajes.
* Los contactos de miembros de la comunidad solo estarán a la vista de otros miembros de la comunidad.
* Las conversaciones serán privadas pero estarán almacenadas durante 6 meses en una BD, esto para facilitar el acceso a las conversaciones desde múltiples dispositivos.

## Otros requerimientos 
La base de datos de miembros debe ser la misma que la base de datos actual del ITAM, esto es para que toda la información y registros que se creen puedan ser vistos 
rápidamente en los otros sistemas del ITAM.

    


  

  
  
  
  
  
  
  
  
  
  
  
  
  
