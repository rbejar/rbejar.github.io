---
author: rbejar
comments: true
date: 2013-12-02 18:12:00+00:00
layout: post
link: http://www.rubenbejar.com/2013/12/concursos-para-desarrollo-de-software-el-mejor-proveedor-no-es-el-mas-barato/
slug: concursos-para-desarrollo-de-software-el-mejor-proveedor-no-es-el-mas-barato
title: 'Concursos para desarrollo de software: el mejor proveedor no es el más barato'
wordpress_id: 365
categories:
- Project Management
- Software Engineering
tags:
- Calidad
- Concurso
- Precio
---

Cuando una empresa grande o una administración pública necesitan un desarrollo de software que no pueden abordar por sus propios medios, en muchas ocasiones recurren al concurso: escriben un pliego de condiciones, suelen establecer un tope de presupuesto y de plazo y abren un periodo de tiempo para que los proveedores potenciales hagan sus ofertas.

Hay un artículo relativamente reciente que recopila y analiza unos cuantos estudios relacionados con este tipo de licitaciones y extrae algunos datos y recomendaciones interesantes para aquellos licitadores que no busquen solo el menor precio (Jørgensen, 2009):



	
  * Cuantos más proveedores se presentan a un concurso, más agresivas son sus ofertas. Esto es entendible, puesto que presentarse a un concurso lleva un esfuerzo, y los que se presentan quieren ganarlo. El problema es que esto incrementa las probabilidades de que gane el concurso un proveedor que ha hecho una oferta demasiado optimista, sobre todo si el licitador se basa principalmente en el precio para decidir el ganador. El autor del artículo sugiere que si el precio va a ser un criterio de selección importante y se presentan muchas ofertas, que primero se elija un subconjunto de proveedores basándose exclusivamente en sus habilidades y solo después se inicie el proceso de subasta. Un problema es que no hay criterios claros para decidir cuándo son "muchas" ofertas.

	
  * Si los proveedores fueran realistas con su nivel de competencia, una oferta menor reflejaría un equipo de desarrollo más competente. Sin embargo hay estudios que indican exactamente lo contrario: cuanta más experiencia, documentada y relevante, pujas más altas (en algún estudio hasta un 60% más altas de media). También hay estudios que indican que si un proveedor ha estado involucrado en la especificación de requisitos inicial, y por tanto conoce mejor el problema, va a pujar más alto. Para rematar el problema, el licitador normalmente lo tiene muy complicado para evaluar adecuadamente la competencia de los proveedores. Por tanto, los proveedores que serían más adecuados, por su habilidad, para el concurso están en desventaja: porque tenderán a hacer ofertas más caras y porque el licitador seguramente carece de la información y/o experiencia necesarias para comparar la competencia real entre los concursantes (el problema de la [selección adversa](https://es.wikipedia.org/wiki/Selecci%C3%B3n_adversa)). En este caso Jørgensen sugieren que si el licitador cree que no puede evaluar adecuadamente la competencia de los proveedores, que evite seleccionar basándose únicamente en el precio. Puesto que en ese caso el licitador se queda sin muchas opciones (no debe elegir por precio, y no tiene la capacidad de evaluar por la habilidad del proveedor), Jørgensen sugiere que el licitador recurra a asesores externos (*).

	
  * Otro tema interesante es el material que deben tener los proveedores a la hora de presentarse al concurso. Por una parte, cuanta más información tengan sobre la complejidad del proyecto menos tendencia a ser demasiado optimistas. En las descripciones de tamaño o complejidad conviene ser todo lo neutral posible: si algo se describe como una "extensión menor" en lugar de como "nueva funcionalidad", las estimaciones serán más optimistas de lo debido. También conviene evitar hablar de oportunidades futuras (por ejemplo sugerir que el ganador del concurso lo tendrá más fácil a la hora de optar a contratos de mantenimiento) porque esto va a forzar pujas más a la baja, de nuevo demasiado optimistas. Finalmente, Jørgensen recomienda  no incluir información sobre el presupuesto disponible o sobre expectativas sobre el precio, porque van a funcionar como [anclas](https://en.wikipedia.org/wiki/Anchoring) sobre las ofertas. (**)

	
  *  Para terminar, el autor del artículo recomienda evitar fases de negociación tras el concurso. Aunque en otras disciplinas quizás puedan tener sentido, en desarrollo de software tienden a llevar al exceso de optimismo. Por ejemplo, en un estudio se pidió a dos grupos de empresas que pujaran para desarrollar la misma funcionalidad. La diferencia era que a unas compañías les pedían ofertas económicas para esa funcionalidad directamente, y a otras les pedían primero ofertas para más funcionalidad, y luego que rebajaran las ofertas iniciales a cambio de una rebaja de funcionalidad. Las segundas hicieron ofertas un 27% menores.


Creo que este artículo es interesante porque se centra en un tema concreto del que no hay muchos datos: la influencia que tiene el licitador en la estimación de costes de un proyecto de software. **Si el objetivo del licitador es conseguir un precio bajo** (a costa de la calidad, con mayor riesgo de que no se complete, y con la casi certeza de que se retrasará la entrega), invitar a muchos concursantes, focalizarse en el precio para decidir, dar una descripción vaga del sistema, indicar un presupuesto bajo, describir el proyecto como "pequeño" y hacer ver a los concursantes que pueden tener más oportunidades de contratos en el futuro son las técnicas a seguir. **Si el objetivo del licitador es conseguir un producto de calidad**, que esté entregado a tiempo y minimizar las posibilidades de fracaso, tendría que hacer todo lo contrario. Mucho nos queda por andar, me temo, para que los licitadores de un desarrollo de software comprendan los beneficios de no apostar principalmente por el precio más bajo a la hora de elegir a un proveedor.





(*) Esto no es nada sencillo. El autor sugiere que estos asesores pueden dar una visión objetiva a partir de los resultados de proyectos previos similares al pliego de condiciones (y no solo de aquellos proyectos seleccionados por el proveedor). También propone la realización de proyectos piloto y la evaluación de los desarrolladores concretos que participarán. Estas propuestas no me parecen demasiado realistas en el caso general, pero si un licitador se juega mucho en un proyecto tendría que plantearse muy seriamente si está haciendo lo suficiente para elegir al proveedor más adecuado. Supongo que estas propuestas son más factibles si se trata de un proyecto grande y hay pocos concursantes, o si se aplican tras una selección previa de los concursantes iniciales.

(**) Hablando de recomendaciones poco realistas... ;-)

**Referencias**

Magne Jørgensen, ["How to Avoid Selecting Bids Based on Overoptimistic Cost Estimates,"](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=04814964) IEEE Software, vol. 26, no. 3, pp. 79-84, May/June, 2009 (hay una "versión del autor" que se puede descargar de [http://simula.no/research/se/publications/Simula.SE.159/simula_pdf_file](http://simula.no/research/se/publications/Simula.SE.159/simula_pdf_file))
