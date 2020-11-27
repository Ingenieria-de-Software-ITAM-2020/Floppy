# Arquitectura
Espacio Itamita utiliza una arquitectura de microservicios. Entre las principales razones para esto estan la escalabilidad, la facilidad de desarrollo y de escalabilidad, la agilidad, y lo bien que se adapta para resolver problemas especificos de este sistema.

El usuario tiene una coneccion web a la entrada de APIs. Se tienen 4 componentes principalmente:
- El primer servicio es el servicio de autenticacion que el ITAM ya posee. Este permite verificar la entrada de usuarios, separar por clases y por puestos, etc.
- El segundo servicio es el servicio de comunicacion. Los mensajes se mandan como requests de HTTPS, llegan a una base de datos donde son procesados y enviados al usuario.
- El tercer servicio es Colmillo el chatbot. Por medio de inteligencia artificial y acceso a la informacion del ITAM puede contestar automaticamente dudas de los usuarios.
- Finalmente hay Kubernetes que estan constantemente verificando que los servicios esten funcionando. Si esto no estaria, podrian haber varios momentos con servicios muertos.
