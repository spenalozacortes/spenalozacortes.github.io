+++
title = 'Conectarse al host con SSH'
date = 2025-01-08T20:11:13-06:00
draft = true
+++

Hace algunos días desarrollando unos tests, leí en los requerimientos que tenía que tomar en cuenta unas palabras en la lista negra. No sabía cuáles eran esas palabras, así que me puse a buscarlas (siempre busco antes de preguntar). Creí encontrarlas dando clicks en los menús en uno de los ambientes de pruebas.

Probé algunas palabras y funcionaban para lo que necesitaba. En mi test puse una de las palabras en codificación rígida (*hard coded*), pero luego pensé que sería bueno tener todas las palabras en otro archivo y elegir una al azar cada que se ejecutara el test.

Como se trataba de un ambiente de pruebas, pensé que tal vez no estaría actualizado, así que le pedí a mi Product Owner una lista de las palabras en lista negra. Me dijo que podía obtenerla del ambiente de desarrollo (justo en la página donde yo ya la había encontrado), pero que en ese momento había un bug que impedía obtenerla.

Como hace poco tiempo obtuve acceso al repositorio de la aplicación, pensé que tal vez podía encontrar la lista verdadera en medio de la gigantesca base de código escrita en PHP. Estuve buscando y al fin encontré unas líneas donde se mencionaba una tabla que parecía contener mi tan anhelada lista de palabras.

El problema ahora era que no sabía entrar a la base de datos.

Finalmente se arregló el bug, pude obtener la lista de palabras usando la interfaz de usuario y la agregué a mi test para elegir una palabra al azar a la vez.

Pero me quedó esa duda sobre la base de datos.

Olvidé un poco todo esto y seguí con mi vida, pero los últimos días desarrollando otros tests me encontré con una situación similar. Haciendo una petición a la API tengo que enviar ciertos IDs que están relacionados con ciertos nombres. Mi petición es exitosa con uno de los IDs, pero al enviar los ~50 IDs que necesito para mi test, la petición falla. 

La lista de los IDs con los nombres la escribió en un JSON otra de las ingenieras QA. Pude haberle preguntado que si la lista era correcta, pero tal vez ella no tenía más información que yo y no quería molestarla. Tampoco sabía qué desarrollador era el encargado de esto. Mi Product Owner sabe mucho, pero no se mete en cosas más técnicas como los IDs.

Pude haberle dado click en la interfaz de usuario a cada uno de los nombres, revisar la petición con Chrome DevTools y ver qué ID se enviaba, pero eso me pareció demasiado trabajo. Dicen que los buenos programadores son unos flojonazos y siempre buscan la solución más rápida y sencilla?

En nuestra Retrospective de fin de año me quejé un poco porque nadie me ha guíado verdaderamente en este proyecto. Todo lo he tenido que descubrir prácticamente sola. Dije que hay muchas cosas técnicas que aún no entiendo y que ni siquiera sé qué es lo que no sé. Afortunadamente uno de los desarrolladores en mi equipo se ofreció a explicarme esos detalles que no conozco o que no me quedan claros.

Hasta ahora no había aprovechado esa oportunidad porque no había surgido la oportunidad


