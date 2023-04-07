# TP-TACS-2023-C1

# **Introduccion**

El objetivo del TP es desarrollar una aplicación que sirva para organizar reuniones entre varias personas.

![imagen-ultima-cena](https://lh6.googleusercontent.com/bxd_rsqi0RZi4MD1zFbTGs56uEVWW8t7axVrfjlhetuGQZH6u8z5-PoRonNSQNEbvUZQfnROYG2-D51I5Pa1MDgFI3Xfsng0ORCZXZxL46Gzhyk-LCS3JfZMwahltCkO_5CBtPAEeodh3d2BGVO6dP0)

La aplicación funcionará de modo stand alone, y estará publicada en la nube para ser accedida.

El TP consta de diversas entregas en las cuales de forma iterativa e incremental se irán agregando funcionalidades a la aplicación.

Recomendaciones Generales



1. Enfocarse en los requerimientos de cada entrega. (Se puede hacer de más pero no de menos)
2. Utilizar al ayudante para validar decisiones de diseño y consultar arquitectura, frameworks, etc.
3. Dividir en forma clara en el equipo las historias de cada entrega para atacarlas en paralelo donde sea posible.
4. Utilizar alguna herramienta para la gestión de tareas (Scrummy, Trello, Issues de Github)
5. Para bajar el riesgo de las futuras entregas aprovechar el tiempo de entregas anteriores para investigar las tecnologías.
6. De ser necesario utilizar al ayudante como facilitador, en cuestiones técnicas y de organización → El rol del ayudante NO es simplemente el de corregir, sino dar soporte al equipo durante todo el proceso en cuestiones técnicas y metodológicas.


# **Objetivo de la aplicación**

La aplicación tiene como objetivo poder organizar eventos entre varias personas, acordando día y horario.


# **User Stories**



1. Como usuario quiero crear un evento, estableciendo una serie de opciones.
1. Cada opción consta de un día y un horario
1. Como usuario quiero anotarme a un evento ya creado, pudiendo votar todos los días y horarios que me quedan bien.
2. Como usuario quiero poder ver los datos de un evento, y los días y horarios con su cantidad de votos asociados.
3. Como usuario quiero poder cerrar la votación de un evento. Siempre y cuando haya sido creado por mi.
4. A fines de monitoreo (y marketing) se solicita ver un contador con la cantidad de eventos creados y horarios votados anotados en las últimas 2 horas. Este dato debe ser tan preciso como sea posible.
5. Req no funcional: dada la alta carga que puede llevar la API se pide que se implemente un[ rate limiter](https://towardsdatascience.com/designing-a-rate-limiter-6351bd8762c6) / throttling. A fines pedagógicos se pide que se implemente sin utilizar 3rd party libraries o soluciones ya fabricadas.
1. En una segunda etapa se debe considerar que el rate limiter debe funcionar de forma distribuída en un cluster que está balanceado.


# **Requerimientos no funcionales**

Los requerimientos no funcionales no solo son importantes para aprobar el TP sino que están directamente relacionados con la filosofía y objetivos de la materia. La calidad no se negocia.

Técnicos



* Se debe utilizar Github/GitLab como SCM.
* Los tests son parte del código. Un caso de uso que no está debidamente testeado, tampoco está completo.
* Todos los métodos no triviales deben tener su correspondiente doc (ej: javadoc) explicando su función, forma de uso y cualquier otra información relevante.
* Se debe incluir en el README.me/Wiki como levantar la aplicación y cualquier decisión respecto del código o las soluciones utilizadas.
* La aplicación debe ser capaz de correrse desde Maven/Gradle/SBT/Node, el comando a correr debe iniciar la aplicación dentro de un Docker container.
* Se debe usar docker-compose para definir el conjunto de aplicacion + db + network de modo tal que se pueda correr todo con un solo comando. Esto es obligatorio para modo local, si en la nube se va a utilizar alguna SaaS DB, entonces para el deploy solo es necesario el Docker container de la main app.
* La APP tiene que cumplir con requerimientos mínimos de seguridad (manejo de contraseñas, recursos externos, etc.)
1. Las claves deben ser guardadas de forma[ correcta](https://es.wikipedia.org/wiki/Sal_(criptograf%C3%ADa)).
2. En caso de existir, las API keys NUNCA debe ser expuestas al usuario
* La aplicación debe soportar un load test, se utilizara alguna tool como[ Vegeta](https://github.com/tsenart/vegeta),[ Wrk](https://github.com/wg/wrk), etc
* La aplicación debe ser portable, requiriendo solamente de Gradle/Maven/SBT/Node + Docker para su prueba y evaluación.
* La aplicación debe tener una interfaz de usuario fácil de utilizar, a elegir entre frontend o integración por telegram

UI



* Si bien se espera algo sencillo, la aplicación debe tener un frontend amigable. Recomendamos seguir los lineamientos de[ https://material.io/](https://material.io/)
* Utilizar algun framework CSS (Bootstrap, etc)


# **Condiciones para promoción**



1. Entregas en fecha
2. Realizar frontend e integración con telegram.


# **Entregas**



* Las entregas deberán realizarse el día pactado antes de las 19 Hs. con un tag llamado Entrega_XX correspondiente al número de entrega.
* Las entregas se realizarán indicando el link al repositorio y el tag para la entrega.
* Todo retraso en una entrega que no haya sido correctamente comunicado y justificado tendrá como penalización el agregado de nuevos requisitos para la aprobación final del TP.


## **Entrega 1 - Esqueleto aplicación**

Esqueleto de la aplicación WEB.

Se debe definir un primer approach hacia los recursos y URLs REST que se utilizarán para cumplir con las historias propuestas. Para esta entrega no es necesario implementar la persistencia, es suficiente con que el estado quede reflejado en memoria.

Para esta entrega si es necesario que la app corra dentro de Docker.


## **Entrega 2 - UI**

Se debe poder interactuar con la app mediante la interfaz elegida.


## **Entrega 3 - Persistencia con DB**

Persistencia utilizando una base de datos. Se debe modificar la aplicación para que en vez de almacenar los datos en memoria, la misma lo haga utilizando alguna base a definir por el equipo.

Nota: A fines pedagógicos se solicita que la base de datos sea NoSQL.


## **Entrega 4 - Cloud**

Para esta entrega la aplicación debe estar deployada en la nube, el deploy en la nube debe ser utilizando Docker containers.


## **Entrega Final**

Entrega final con detalles pulidos de funcionalidades faltantes y correcciones finales
