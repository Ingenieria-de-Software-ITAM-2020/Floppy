# Plan de Calidad
## Identificador del plan de prueba
Prueba 1.0 del prototipo para la aplicación de Espacio Itamita.

## Referencias
Las pruebas de este prototipo se harán en la plataforma [Proto IO](https://proto.io/), una vez que se termine el código y esté en producción las pruebas se implementarán utilizando difernete un software de pruebas como Test IO. No será posible utilizar herramientas web para hacer las pruebas del código antes de ponerlo en producción ya que Espacio Itamita será una aplicación mobil para iOS y Android, entonces se deben de hacer pruebas para ambas plataformas. Es posible utilizar lenguajes de programación como Flutter o Dart para que el mismo código funcione para iOS y Android, pero de igual manera se debe de probar en ambas plataformas.

## Introducción
El objetivo que tiene este proyecto es crear un sistema en el que los estudiantes del Instituto Tecnológico Autónomo de México (ITAM) se puedan comunicar de una mejor forma entre ellos y con sus profesores. Este sistema debe de cumplir con los requerimientos de UX para las funcionalidades más importantes que necesitan sus usuarios y tener una buena documentación, metodología y arquitectura, con la meta de que el desarrollo de la aplicación sea lo más eficiente y económico posible.

## Elementos de prueba
 - La validación del usuario y contraseña se deben de poder hacer con las mismas credenciales utilizadas en Comunidad ITAM.
 - Las pantallas se deben de desplegar correctamente.
 - El interprete de Latex funcione correctamente.
 - Los botones redireccionan a las pantallas correctas.
 - Se pueden enviar y recibir mensajes con los demás usuarios.
 - Se pueden crear nuevos grupos para tener chats.
 - No puede haber perdida de información.
 - Se pueden poder enviar fotos y documentos en los mensajes.
 - Los profesores, alumnos y personal administrativo estan organizados en su carpeta correspondiente.
 - Habrá un chatbot para ayudar a los usuarios y responder posibles dudas que tengan.

## Problemas de riezgo de software
 - Los servidores del ITAM pueden tener problemas y se cae la conexión.
 - En fechas de exámenes o fechas en las que hay muchos proyectos el tráfico de datos puede aumentar y tirar los servidores.
 - Pueden haber problemas en el interprete de Latex y que no se puedan enviar ecuaciones.
 - Puede haber perdida de información y que no se envien o se reciban mensajes.

## Funcionalidades a probar
- Inicio de sesión del usuario.
- Que el usuario pueda chatear con otros usuarios.
- Que el usuario pueda buscar en sus contactos.
- Que el usuario crear nuevos grupos.
- Que el sistema permita enviar mensajes con código de Latex y lo interprete para enseñar la ecuación correspondiente.
- Que el usuario pueda enviar imágenes y documentos a otros usuarios.
- Que el chatbot del sistema pueda responder las dudas que tenga el usuario sobre cosas del ITAM.
- Que el sistema pueda enviar notificaciones al celular del usuario.

## Funcionalidades que no se deben probar
La cuenta con la que va a ingresar el usuario debe de ser la misma que su cuenta del ITAM entonces la validez de esta cuenta no se debe de probar.

## Acercamiento
Para comenzar las pruebas, se utilizará un prototipo en Proto IO que se le enseñará a los diferentes usuarios que tendrá la aplicación (estudiantes, profesores y personal administrativo). Se utilizará la información recolectada con el prototipo para hacer cambios en el UI para que los usuarios de la aplicación la acepten lo más rápido posible. La métrica que se utilizará en esta prueba será el tiempo que toma el usuario en enviar un mensaje a una persona específica, en crear un nuevo grupo y en escribir un mensaje en ese grupo. Para hacer esto, se deben de hacer diferentes prototipos para poder comparar entre ellos e implementar el mejor en codigo. Además de esto, se debe de utilizará la métrica *Mean Time Between Failures* para ver cuales son las funcionalidades que se deben de modificar para que hayan menos errores.

En la primera prueba se deberán verificar las funcionalidades que están en el apartado de las [funcionalidades a probar](#funcionalidades-a-probar) y las que están en los [elementos de prueba](#elementos-de-prueba), sin embargo, algunas funcionalidades, como el interprete de Latex o la conexión al servidor, no se pueden probar en el prototipo. Se desarrollará el código únicamente cuando esten terminadas las pruebas con el prototipo, y después se implementarán todas las pruebas usando ya el código.

## Criterios de aprobación / Falla del elemento
Por el momento solamente se está probando el front-end utilizando un prototipo entonces el criterio de aprobación sería que un usuario pueda encontrar las pantallas que se requieren para mandar un mensaje, buscar un usuario que se le quiera mandar un mensaje y crear un nuevo grupo en menos de un minuto.
En un futuro, se espera que se puedan enviar mensajes, fotos, documentos y ecuaciones utilizando Latex sin fallas.

## Criterios de suspención y requisitos de reanudación
- Las pruebas que no necesitan al servidor del ITAM y se puedan hacer localmente se harán constantemente.
- Ls pruebas que necesiten los servidores del ITAM se suspenderán si estos no están disponibles o si hay alguna falla de seguridad en la aplicación. En el momento en el que el problema se arregle las pruebas se reanudarán.

## Entregables de prueba
El entregable de las pruebas será un documento detallado con las funcionalidades que se probaron, el modo en el que se implementaron las pruebas y los resultados de las métricas que se obtuvieron. En el caso de que sea una prueba del diseño de la aplicación se incluirá también la opinión de los usuarios en las diferentes funcionalidades que se probaron.

## Tareas de prueba restantes
Todas las pruebas de seguridad se espera que esten implementadas con los demás servicios que da el ITAM, entonces no se van a probar la encripción de los mensajes. Todas las otras funcionalidades de la aplicación sí se van a probar.

## Necesidades ambientales
Para pruebas generales de la aplicación se requieren:
 - Un dispositivo iPhone y Android.
 - Acceso a internet.
 - Un usuario para los servicios del ITAM.

## Necesidades de personal y capacitación
Para llevar a cabo las primeras pruebas del prototipo el personal que haga las pruebas no necesita ninguna capacitación ademas de entender completamente la funcionalidad que está probando y las métricas que se estarán usando para probar dicha funcionalidad.

## Responsabilidades
El equipo de pruebas está formado con las cuatro personas que estan desarrollando la aplicación (Francisco Aramburu, Fernanda Martinez, Dan Jinich y Eyal Schuller). Cada persona será respobsable de probar dos funcionalidades diferentes:
- Francisco Aramburu:
  - Inicio de sesión del usuario.
  - Que el usuario pueda chatear con otros usuarios.
- Fernanda Martinez
  - Que el usuario pueda buscar en sus contactos.
  - Que el usuario crear nuevos grupos.
- Dan Jinich
  - Que el sistema permita enviar mensajes con código de Latex y lo interprete para enseñar la ecuación correspondiente.
  - Que el usuario pueda enviar imágenes y documentos a otros usuarios.
- Eyal Schuller
  - Los profesores, alumnos y personal administrativo estan organizados en su carpeta correspondiente.
  - Habrá un chatbot para ayudar a los usuarios y responder posibles dudas que tengan.
