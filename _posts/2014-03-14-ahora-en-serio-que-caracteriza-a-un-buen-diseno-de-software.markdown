---
author: rbejar
comments: true
date: 2014-03-14 16:06:45+00:00
layout: post
link: http://www.rubenbejar.com/2014/03/ahora-en-serio-que-caracteriza-a-un-buen-diseno-de-software/
slug: ahora-en-serio-que-caracteriza-a-un-buen-diseno-de-software
title: 'Ahora en serio: ¿qué caracteriza a un buen diseño de software?'
wordpress_id: 435
categories:
- Programming
- Software Engineering
tags:
- Diseño de software
- Programación
---

En [la última entrada del blog](http://www.rubenbejar.com/2014/03/que-caracteriza-a-un-buen-diseno-de-software/) hablábamos sobre la importancia de distinguir entre software bien diseñado y software bueno, y señalábamos como a menudo se confunden las dos cosas (que están relacionadas pero son muy diferentes). Sin embargo apenas mencionábamos de pasada algunas de las características que debe tener un diseño de software para que lo consideremos bueno.

Creo que es buena idea que empecemos por un problema que parece más conocido: ¿qué caracteriza a un buen código fuente? Algunas posibles respuestas (ni exhaustivas, ni totalmente independientes unas de otras):



	
  * Legible: el código fuente se lee más veces de las que se escribe. Seguir un estándar de codificación bien pensado y establecido hace mucho por la legibilidad del código.

	
  * Bien documentado: **recalco lo de bien**. Esto incluye comentarios explicando las partes más complicadas del código, las **responsabilidades** de clases, métodos, procedimientos, funciones o variable y la exposición de las **razones** (los porqués) que han llevado a escribir cierto código y no otro.

	
  * Bien organizado: una buena estructura modular dice mucho de un código fuente.

	
  * Hace uso de estructuras de datos y algoritmos establecidos: si todas las estructuras de datos del código son vectores estáticos unidimensionales, mala señal. Si tenemos que solucionar un problema difícil, en lugar de inventarnos un algoritmo de cero (que seguramente tampoco lo resolverá bien) tendríamos que aplicar a nuestro problema un esquema algorítmico adecuado.

	
  * Hace uso de buenos nombres (para variables, funciones, clases etc.): los nombres apropiados son aquellos que hacen referencia a la responsabilidad que tienen estos elementos del código y ayudan a la legibilidad del código (los nombres de variable de 40 caracteres no ayudan).

	
  * Al hilo del punto anterior, los elementos del código deben tener una responsabilidad única.


¿En qué nos ayuda esta lista a caracterizar lo que es un buen diseño? En nuestro contexto (desarrollo de software), un diseño es una especificación de algo que vamos a construir o la documentación de algo que hemos construido. En ambos casos el nivel de detalle es variable. No es lo mismo un borrador inicial de la arquitectura de un nuevo sistema que tenemos que implementar, que la documentación detallada que deberíamos proporcionar a nuestros clientes si vendemos componentes para su integración en otros sistemas. Sin olvidar esto, de un buen diseño de software esperaremos que sea:

	
  * Legible: el diseño se lee más veces de las que se escribe. Seguir un estándar de documentación de diseño bien pensado y establecido hace mucho por la legibilidad del mismo.

	
  * Bien documentado: **recalco lo de bien**. Esto incluye explicaciones de las partes más complicadas del diseño, las **responsabilidades** de módulos, componentes y conectores y la exposición de las **razones** (los porqués) que han llevado a cierto diseño y no a otro.

	
  * Bien organizado: una buena estructura modular y de componentes dice mucho de un diseño de software.

	
  * Hace uso de estilos arquitecturales y patrones de diseño establecidos: si no podemos distinguir fácilmente las vistas de los modelos en la parte que corresponde con nuestra GUI, mala señal. Si tenemos que organizar un sistema complejo, en lugar de inventarnos un estilo arquitectural de cero (que seguramente tampoco lo resolverá bien), tendríamos que aplicar a nuestro problema uno adecuado (cliente-servidor, por niveles, publicador-suscriptor...)

	
  * Hace uso de buenos nombres (para componentes, clases, paquetes etc.): los nombres apropiados son aquellos que hacen referencia a la responsabilidad que tienen estos elementos del diseño y ayudan a la legibilidad del mismo (los nombres de módulos de 40 caracteres no ayudan).

	
  * Al hilo del punto anterior, los elementos del diseño deben tener una responsabilidad única.


Espero que se aprecie el paralelismo.  ;-)

Podríamos añadir más cosas, y es evidente que encontraríamos algunas diferencias, pero **una vez hemos separado las características de un buen diseño de las de un buen software** (lo que hicimos en el post anterior) se aprecia mejor que **lo que caracteriza a un buen diseño es muy similar a lo que caracteriza a un buen código fuente**.

¿Sorprendidos? No deberíais. Como ya hemos visto en otras ocasiones, [programar es diseñar](http://www.rubenbejar.com/2013/10/breve-resena-del-libro-the-pragmatic-programmer/), y [el código fuente es diseño](http://www.rubenbejar.com/2013/04/programar-no-es-poner-ladrillos/). Y como es lógico, si el código fuente es diseño, lo que caracterice a un buen código fuente también caracterizará a un buen diseño.




