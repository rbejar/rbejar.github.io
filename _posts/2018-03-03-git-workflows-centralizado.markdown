---
author: rbejar
date: 2018-03-03
layout: post
title: "Los workflows de Git (I): el injustamente menospreciado workflow centralizado"
share-img: http://www.rubenbejar.com/img/share-img/GitMerge.png
tags:
- Git
- Gestión
- Desarrollo
- Devops
- Workflow centralizado
- Integración continua
- Despliegue continuo
---

Git es un sistema de control de versiones distribuido de uso muy extendido en proyectos de software, aunque se usa también para otras cosas. Una de sus características es que no establece demasiadas restricciones sobre cómo sus usuarios deben organizarse para trabajar, así que cada equipo, organización o proyecto tienen que decidir una forma de trabajar con el.

Con el tiempo, y la experiencia, se han ido estableciendo ciertos *workflows* habituales, que no son más que formas de organizarse para trabajar con Git. Elegir uno de estos *workflows* sin considerar las características del equipo o equipos involucrados, el producto en el que se trabaja y los objetivos —p.ej. de calidad— que se quieren alcanzar es más habitual de lo que parece. Las decisiones que tienen impacto en el transcurso y los resultados de un proyecto de software habría que tomarlas eligiendo razonadamente entre alternativas razonables. No siguiendo una moda, por vagas referencias a "buen estilo" o "buenas prácticas", porque es lo último que has visto en una conferencia de desarrolladores, porque te "suena bien" o porque "en no sé qué sitio lo hacen así y les va muy bien".

Git, como todos los sistemas de control de versiones, es una herramienta que se sitúa en un punto entre el desarrollo de software, las operaciones —despliegue y monitorización del sistema, respuesta a incidencias en producción etc.— y la gestión de proyectos:

- Los equipos de desarrollo escriben el código, lo comparten y lo combinan usando Git. Cada integrante tiene sus repositorios locales, y se tienen que organizar entre sí para compartir y combinar el código entre los diferentes repositorios.
- Los equipos de operaciones descargan el código correspondiente a una versión que quieren desplegar, la información de configuración del entorno de despliegue —que debería estar también en Git— y despliegan —idealmente con un proceso automatizado y buscando la entrega continua—. También tienen que coordinar con desarrollo el arreglo de errores o problemas detectados durante la monitorización de las versiones que están en producción.
- Gerencia tiene que asegurarse de que un proyecto se divide en partes que puedan desarrollar en paralelo personas, o equipos, que luego coordinarán sus resultados, tiene que priorizar una funcionalidad u otra, decidir los niveles de calidad que son aceptables para el proyecto o establecer una cadencia, o compromisos temporales, para las entregas a los clientes. Una buena división del trabajo minimizará conflictos de *merge* entre desarrolladores. Un uso juicioso de ramas mantendrá el *work in progress* (WIP) bajo control reduciendo así los tiempos de ciclo. Tener ciertos objetivos de cadencia en las entregas exige implementer pipelines de despliegue automatizados, que dependen fuertemente de cómo se haya organizado el uso de Git. La calidad del código depende en parte de cuántos ojos lo han revisado, y según se organice el trabajo con Git se puede exigir que algunas contribuciones, o todas, sean revisadas por una persona antes de ser aceptadas.

Elegir de manera razonada un *workflow* de Git debería pues tener en cuenta, no solo las circunstancias particulares mencionadas antes —equipo o equipos, producto y objetivos—, sino estos tres puntos de vista —desarrollo, operaciones y gestión—, algo que en general no se hace.

## El *workflow* centralizado
Está explicado en detalle en muchos sitios, por ejemplo en [este tutorial de Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows#centralized-workflow), así que no voy a repetirlo aquí.

Adecuado para equipos pequeños —p.ej. entre 8 y 10 personas como máximo— y que trabajan en el mismo sitio. Es el más adecuado si algunos integrantes todavía están aprendiendo Git —solo necesitas los comandos básicos—, pero no impide sacar partido a un buen dominio de esta herramienta a los que sean más expertos. Dado que hay una rama compartida por todo el mundo —casi siempre `origin/master` en el repositorio central— si hubiera mucha gente podría acabar habiendo demasiados conflictos. El hecho de que trabajen en el mismo sitio también agiliza mucho la resolución de conflictos. Por ejemplo, cuando surge uno cuya solución no es obvia, te vuelves hacia tu compañera que está sentada a tu lado y lo resolvéis inmediatamente. Además en un equipo localizado es más fácil que el proyecto esté organizado de manera que el reparto de tareas minimice colisiones innecesarias. Una metodología ágil con breves reuniones diarias de coordinación y un tablero de tareas bien visible para todo el mundo, reducirá mucho el número de conflictos debidos a un mal reparto del trabajo.

Hay que recordar, en algunas explicaciones sobre este *workflow* esto se olvida, que la rama master local de cada integrante del equipo es privada, es decir que no tienes que compartir todos tus *commits* con los demás, lo haces solo cuando los has dejado en un estado "compartible". También es importante notar que en los repositorios de cada persona se pueden crear **tantas ramas como cada cuál quiera o necesite**. Incluso dos o más personas del equipo podrían colaborar en implementar una característica particular compartiendo una rama específica directamente entre ellos, sin llegar a subirla nunca al repositorio central, o subiendo los cambios una vez hubieran terminado y combinado con la rama master. Eso sí, si esto fuera algo frecuente, seguramente tendrían que plantearse que quizás necesitan un *workflow* distinto.

Está bien para proyectos pequeños, cuyo desarrollo no vaya a durar mucho tiempo y que no van a tener varias versiones en producción simultáneamente. Con Git y un mínimo de cuidado al usar por ejemplo `git reset` siempre será posible volver al *commit* de una versión anterior y crear a partir de ahí una rama para arreglar un fallo en producción en esa versión. Sin embargo, hay alternativas más organizadas para esto que el *workflow* centralizado si esto hay que hacerlo con cierta frecuencia.

Tener una única rama central, p.ej. la rama master del repositorio central, a la que se envían cambios con frecuencia **es un requisito para hacer integración continua**. Todo el trabajo que se haga fuera de la rama master del repositorio central por definición no está integrado con todo lo demás. La integración continua consiste en que todo tu código está integrado con el de todos los demás todo el tiempo (siendo todo el tiempo al menos una o dos veces al día). Cualquier otra cosa puede ir desde "integración casi continua" a "integración ocasional", pero no será integración continua. **El flujo de trabajo centralizado es el que mejor se adapta a la integración continua**. Además la integración continua es un requisito para la entrega continua —y para el despliegue continuo—, así que **el flujo de trabajo centralizado es el que mejor se adapta a la entrega continua**.

No caigáis en la trampa de consider que este workflow es inadecuado porque "es el que más se parece al trabajo con Subversion" que es un argumento que he leído demasiadas veces. Este workflow es más potente que lo que solía ser el trabajo con Subversion: tienes un repositorio centralizado, pero además cada integrante del equipo tiene su propio repositorio, su rama master local, distinta de la compartida, puede crear las ramas locales que quiera e incluso pueden compartirlas entre ellos directamente sin pasar por el repositorio central. Además de que Git hace los *merges* mucho menos dolorosos de lo que solían ser (parece que ha ido mejorando) con Subversion, y es en general más rápido.

Tampoco caigáis en evitarlo por "no aprovechar bien que Git sea distribuido". Que Git es distribuido es una característica muy potente, pero no significa que haya que explotarla al máximo en cada proyecto. El *workflow* en espagueti, donde todos los desarrolladores crean las ramas que les apetece crear y las comparten directamente con quien quieren y cuando quieren se aprovecha muy bien de que Git es un sistema distribuido, pero es lo último que querrías para tu proyecto.

Evitadlo, o al menos consideradlo solo después de descartar otras opciones, para proyectos grandes, con equipos distribuidos, con mmuchos contribuidores que solo son ocasionales, o cuando no necesitéis la integración continua ni la entrega continua. Hay *workflows* más adecuadas para esas circunstancias.

## Conclusión

Este post ya me ha quedado muy largo (muchos bloggers ya lo habrían dividido en dos o tres para "maximizar el impacto" o como sea que lo llamen x) así que voy a tener que dejar un breve análisis de otros workflows habituales para más adelante. De momento espero haber dejado claras al menos dos ideas:

- O tomáis las decisiones técnicas razonando entre alternativas razonables, o las decisiones técnicas os tomarán a vosotros. Y no queréis esto último.
- El workflow centralizado, quizás con pequeñas variantes, es el mejor para determinados equipos en determinados proyectos. No lo menospreciéis solo por ser el más sencillo. La sencillez es una enorme virtud en los proyectos de ingeniería.

Enhorabuena si has llegado hasta aquí. Estos posts tan largos y densos no son para cualquiera. Si todavía te quedan ganas de más, te recomiendo algunas cosas **para leer**:

- ["Continuous Integration" by Jez Humble](https://continuousdelivery.com/foundations/continuous-integration/)
- ["On DVCS, continuous integration, and feature branches" by Jez Humble](https://continuousdelivery.com/2011/07/on-dvcs-continuous-integration-and-feature-branches/)
- ["FeatureBranch" by Martin Fowler](https://martinfowler.com/bliki/FeatureBranch.html)
- ["Enabling Trunk Based Development with Deployment Pipelines" by Vishail Naik](https://www.thoughtworks.com/insights/blog/enabling-trunk-based-development-deployment-pipelines)
- ["How Chromium Works" by Aaron Boodman](https://medium.com/@aboodman/in-march-2011-i-drafted-an-article-explaining-how-the-team-responsible-for-google-chrome-ships-c479ba623a1b) describe como en Chromium  —cientos de desarrolladores y 800 cambios por semana— usan lo que es esencialmente un flujo de trabajo centralizado con tan solo algunas ramas de corta duración porque es lo que se adapta a su ritmo de trabajo y a su estrategia de entrega continua.
