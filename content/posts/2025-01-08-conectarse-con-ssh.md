+++
title = 'Conectarse al host con SSH'
date = 2025-01-08T20:11:13-06:00
draft = true
+++

## El contexto[^1]

Hace algunos días desarrollando unos tests, leí en los requerimientos que tenía que tomar en cuenta unas palabras en una lista negra. No sabía cuáles eran esas palabras, así que me puse a buscarlas (siempre busco antes de preguntar). Creí encontrarlas dando clicks en los menús en uno de los ambientes de pruebas.

Probé algunas palabras y funcionaban para lo que necesitaba. En mi test puse una de las palabras en codificación rígida (*hard coded*), pero luego pensé que sería bueno tener todas las palabras en otro archivo y elegir una al azar cada que se ejecutara el test.

Como se trataba de un ambiente de pruebas, pensé que tal vez no estaría actualizado, así que le pedí a mi Product Owner una lista de las palabras en lista negra. Me dijo que podía obtenerla del ambiente de desarrollo (justo en la página donde yo ya la había encontrado), pero que en ese momento había un bug que impedía obtenerla.

Como hace poco tiempo obtuve acceso al repositorio de la aplicación, pensé que tal vez podía encontrar la lista verdadera en medio del gigantesco código fuente escrito en PHP. Estuve buscando y al fin encontré unas líneas donde se mencionaba una tabla que parecía contener mi tan anhelada lista de palabras.

Ahora el problema era que no sabía entrar a la base de datos.

Finalmente se arregló el bug, pude obtener la lista de palabras usando la interfaz de usuario y la agregué a mi test para elegir una palabra al azar cada vez.

Pero me quedó esa duda sobre la base de datos.

Olvidé un poco todo esto y seguí con mi vida, pero los últimos días desarrollando otros tests me encontré con una situación similar. Al hacer una petición a la API tenía que enviar ciertos IDs que están relacionados con ciertos nombres. Mi petición era exitosa con uno de los IDs, pero la petición fallaba al enviar los ~50 IDs que necesitaba para mi test.

El JSON con los IDs y los nombres lo escribió otra de las ingenieras QA. Pude haberle preguntado que si los IDs eran los correctos, pero tal vez ella no tenía más información que yo y francamente no quería molestarla. Tampoco sabía qué desarrollador estaba implementando esto, pero definitivamente no era un desarrollador de mi equipo. Mi Product Owner sabe mucho, pero no se mete en cosas más técnicas como los IDs.

Pude haberle dado click en la interfaz de usuario a cada uno de los nombres, revisar la petición con Chrome DevTools y ver qué ID se enviaba con cada nombre, pero hacer eso 50 veces me pareció demasiado trabajo. Dicen que los buenos ingenieros son unos flojonazos y siempre buscan la solución más rápida y sencilla?

En nuestra Retrospective de fin de año me quejé un poco porque nadie me ha guiado verdaderamente en este proyecto. Casi todo lo he tenido que descubrir prácticamente sola. Dije que hay muchas cosas técnicas que aún no entiendo y que ni siquiera sé qué es lo que no sé. Afortunadamente uno de los desarrolladores en mi equipo se ofreció a explicarme esos detalles que no conozco o que no me quedan claros.

Hasta ahora no había aprovechado esa oportunidad, en primera porque no se me había ocurrido qué preguntar, en segunda porque no había surgido nada que pudiera preguntarle solo a un desarrollador, y en tercera porque la verdad me daba un poco de vergüenza. La situación de los IDs era perfecta.

Le expliqué mi problema al desarrollador y le dije que yo creía que alguno o varios de mis IDs estaban mal. Le pregunté que dónde podía obtener los IDs correctos. Su respuesta fue una consulta SQL y un comando de MySQL para la línea de comandos, para que yo eligiera el de mi preferencia. Le dije que no sabía cómo conectarme a la base de datos y así comenzó mi aventura con SSH.

## La solución

[^1]: Al momento de escribir esto tengo 7 meses de experiencia profesional como desarrolladora de pruebas.


