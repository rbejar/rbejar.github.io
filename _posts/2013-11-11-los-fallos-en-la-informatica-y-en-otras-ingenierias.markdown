---
author: rbejar
comments: true
date: 2013-11-11 21:36:44+00:00
layout: post
link: https://www.rubenbejar.com/2013/11/los-fallos-en-la-informatica-y-en-otras-ingenierias/
slug: los-fallos-en-la-informatica-y-en-otras-ingenierias
title: Los fallos en la informática y en otras ingenierías
wordpress_id: 285
tags:
- Software Engineering
- Diseño
- Informática
- Ingeniería
---

Si has estudiado informática, seguro que en algún momento de la carrera te han contado la historia de algunos de los fallos más sonados, como [los fallos de especificación y diseño en el sistema de referencia inercial del cohete Ariane 501](http://www.ima.umn.edu/~arnold/disasters/ariane5rep.html) que provocaron que explotara unos 40 segundos después de ser lanzado, [una condición de carrera en el Therac-25](https://en.wikipedia.org/wiki/Therac-25), un acelerador lineal usado para radioterapia, que causó que se dieran dosis de radiación unas 100 veces superiores a las programadas para algunos pacientes, o el de la sonda [Mars Climate Orbiter](https://en.wikipedia.org/wiki/Mars_Climate_Orbiter) que se desintegró durante la inserción orbital por un software que produjo un dato en libras por segundo en lugar de en Newtons por segundo como se había especificado (1).

Los sistemas informáticos están hoy en día en todas partes. Es difícil encontrar algo mínimamente complejo que no tenga al menos un microprocesador por algún sitio. Eso implica que con un porcentaje pequeño de sistemas que funcionen mal, el número total de fallos puede ser grande. Algunos llaman la atención, como [estos cajeros automáticos de Sydney que daban dinero](http://www.bbc.co.uk/news/world-asia-pacific-12606735), otros cuestan mucho dinero público, como [este sistema de gestión de casos que le costó al FBI 100 millones de dólares y nunca se usará](http://spectrum.ieee.org/computing/software/who-killed-the-virtual-case-file), o como el recientemente puesto en marcha [HealthCare.gov, plagado de problemas](http://www.pcworld.com/article/2061940/healthcaregovs-problems-what-we-know-so-far.html).

Sin embargo, en general los sistemas informáticos funcionan: los cajeros automáticos te dan el dinero que tienes en la cuenta, no más, las policías gestionan sus archivos informáticamente y las webs de las administraciones públicas, aunque normalmente lejos de ser un ejemplo de diseño y funcionalidad, suelen estar ahí cuando te conectas. Y los aviones vuelan, los inversores en bolsa especulan, y los mensajes electrónicos llegan a sus destinatarios. Es decir, que la mayoría de los sistemas informáticos funcionan bien. A pesar de esto, ejemplos de fallos como los anteriores, se suelen usar para hablar de una "crisis del software" y para justificar la necesidad de aplicar [ponga usted aquí su herramienta, método o proceso] al desarrollo de software.

En términos generales, hoy en día no es posible **diseñar** un  sistema moderadamente complejo que no tenga errores, y tampoco es posible estimar con precisión su coste y su plazo de finalización. Distinto es el caso de la **fabricación**, que busca repetir una y otra vez el mismo proceso para crear productos idénticos, o con pequeñas variaciones entre ellos. Ese es el ámbito donde los procesos, técnicas y herramientas pueden aportar fiabilidad, repetibilidad y estimaciones precisas.

El desarrollo de software es diseño, no es fabricación, y a pesar de su relativa juventud no creo que la informática esté mucho peor equipada que otras ingenierías para abordar el diseño de sistemas novedosos y complejos. Unos ejemplos ayudarán a entender por qué no creo que tenga que fijarse en ellas como "ejemplo a seguir".

[La construcción del avión Airbus A380 se retrasó varias veces](https://en.wikipedia.org/wiki/Airbus_A380#Production_and_delivery_delays): en 2005 se anunció un retraso de seis meses, lo que reducía el número de aviones a entregar en 2009 de 120 a 90-100. En 2006 se anunció un segundo retraso de seis-siete meses (esto serían 70-80 aviones entregados para 2009).  A finales de 2006 hubo un tercer retraso (lo que reduciría el número de aviones entregados para 2009 a 25). En 2008 se anunciaron entregas retrasadas para 2008 y 2009 (se quedaban en 21 aviones). Después de algunos problemas adicionales, se quedó en 14 aviones para el 2009. Finalmente se entregaron 10 Airbus A380 en 2009. Es decir menos de una décima parte de los planes iniciales.

[El Boeing 787 Dreamliner no puede presumir de mejores datos](https://en.wikipedia.org/wiki/Boeing_787_Dreamliner#Production_and_delivery_delays). En 2006 Boeing se da cuenta de que los primeros 787 tienen sobrepeso: apenas 2.3 toneladas más de lo especificado. En Septiembre de 2007 anuncian un retraso de tres meses. En Octubre, anuncian otro retraso de tres meses para el primer vuelo y uno de seis para las primeras entregas. En Enero de 2008 se anuncia otro retraso de tres meses para el primer vuelo. En Abril de 2008 se anuncia el cuarto retraso, que dejaría las entregas iniciales 15 meses más tarde de lo planificado inicialmente. En Noviembre de 2008 anuncian un quinto retraso. En Diciembre de 2008 confirmaron que el primer vuelo se retrasaría aún más. Incluso con los retrasos, en Noviembre de 2010 un Boeing 787 tuvo que hacer un aterrizaje de emergencia durante un vuelo de pruebas porque se detectó un incendio a bordo.

Hablando de incendios, [en 2012 Toyota llamó a revisión a varios millones de coches](https://autos.aol.com/article/toyota-recalls-7-5-million-cars-for-door-fires/) por riesgo de incendio causado por un interruptor defectuoso en una puerta.

La ingeniería naval tampoco se salva: [el nuevo submarino S80 de la armada española tiene sobrepeso](https://es.wikipedia.org/wiki/Submarinos_Clase_S-80#Problemas_durante_la_construcci.C3.B3n) (entre 75 y 100 toneladas), lo que puede comprometer su flotabilidad. Corregirlo supondrá unos 200 millones de euros y un retraso de entre uno y dos años en la entrega.

Ni la ingeniería civil, que podríamos considerar que tiene varios miles de años de experiencia acumulada ;-), se libra de problemas: aquí hay una lista de puentes que se han caído en los últimos 15 años: [https://en.wikipedia.org/wiki/List_of_bridge_failures#2000-Present](https://en.wikipedia.org/wiki/List_of_bridge_failures#2000-Present). Aunque hay accidentes y ataques, muchos de ellos son achacables a fallos de planificación e ingeniería como el Hoan Bridge, en Milwaukee, Wisconsin, que se colapsó parcialmente debido al frío, la nieve y a una importante cantidad de tráfico, tres factores que no parecen precisamente impredecibles cuando pones un puente en un sitio frío de un país con casi un vehículo de motor por habitante.

Estoy bastante seguro de que las empresas detrás de estos proyectos cuentan con personal altamente cualificado formado en las mejores universidades, asesoramiento de expertos de todos los ámbitos, amplia experiencia, las mejores herramientas, millones de certificados de calidad, elaborados procesos de gestión, sesudas metodologías de análisis y diseño, complejos modelos matemáticos, larguísimos protocolos de pruebas, y que generaron toneladas de documentación mientras llevaban a cabo todos estos proyectos. Es decir, que lo hicieron bien, o tan bien como se sabe hacer un proyecto complejo y de largo plazo.

También estoy bastante seguro de que si crees que la forma de trabajar de esas empresas, las cosas que he nombrado en el párrafo anterior, son adecuadas, vas a convencerte muy rápido (2) de que es que no se aplicaron bien, o no se aplicaron lo suficiente, y que por eso fallaron. Y si por el contrario piensas que deberían hacer algo que no hicieron, vas a ver una prueba evidente de que fallaron por no hacerlo (3). En cualquier caso, seguiremos sin saber si los fallos son evitables o si son inherentes al diseño de sistemas complejos.

Me ha quedado un post más largo de lo que quería, pero espero que al menos sea entretenido. Hoy día los sistemas informáticos son casi ubicuos, y un buen porcentaje de ellos se encuentran en el [ámbito complejo](https://en.wikipedia.org/wiki/Cynefin). Puesto que el diseño de sistemas complejos es complejo, capitán obvio _dixit_, es de esperar que un buen número de sistemas informáticos presenten fallos, algunos de ellos graves, aunque el porcentaje sea pequeño con respecto del total. Espero que unos cuantos ejemplos de fallos en otras ingenierías nos ayuden a los informáticos a levantar la vista de nuestros teclados y a sospechar que, después de todo, la informática como disciplina no está tan mal como algunos nos han dicho.



(1) Una explicación precisa y concreta del fallo que sin embargo no explica lo importante para que algo parecido no vuelva a pasar: ¿cómo pudo pasarse por alto algo que es tan obvio y sencillo de comprobar? Si en tu cabeza se está formando una explicación del tipo "Pues porque no usaron el método/técnica/herramienta X...", espera, no me lo cuentes a mi; creo que en la NASA y en Lockheed te agradecerán que vayas a iluminarles, si es posible con palabras sencillas.

(2) Sospechosamente rápido; piénsalo un momento si queda algo de escéptico en ti.

(3) Lo que es evidentemente un razonamiento falaz, pero las falacias que te dan la razón hablan con palabras muy dulces... x)
