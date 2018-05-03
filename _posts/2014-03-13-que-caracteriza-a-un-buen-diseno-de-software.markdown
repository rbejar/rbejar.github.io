---
author: rbejar
comments: true
date: 2014-03-13 13:47:51+00:00
layout: post
link: https://www.rubenbejar.com/2014/03/que-caracteriza-a-un-buen-diseno-de-software/
slug: que-caracteriza-a-un-buen-diseno-de-software
title: ¿Qué caracteriza a un buen diseño de software?
share-img: https://www.rubenbejar.com/img/share-img/SoftwareWellDesigned.png
wordpress_id: 414
tags:
- Programming
- Software Engineering
- Diseño de software
- Programación
---

Es bastante más fácil señalar las características que debe tener un buen diseño de software(1) que explicar como llegar a él. Hay muchos artículos que recogen algunas de estas características, y hoy quiero mostrar como estos incluyen a menudo elementos que tienen poco que ver con lo bueno o lo malo que sea este diseño. Usaré como ejemplos  tres de los resultados que me han salido en la primera página de la búsqueda en Google de _good software design_.

La primera característica de un buen diseño de software que aparece en este breve [artículo](http://www.theserverside.com/news/thread.tss?thread_id=26021), es "que proporciona la funcionalidad necesaria". La primera en la frente. Un diseño malo también puede proporcionar la funcionalidad necesaria. Por ese camino no distinguiremos entre diseño bueno y diseño malo. Ese mismo fallo lo cometen también [en este otro](http://avilay.wordpress.com/2012/09/01/what-is-good-software-design/), que nos indica en el segundo punto que el buen diseño debe ser "robusto". Esto no suena mal, robusto es una palabra con connotaciones positivas, pero cuando concretan lo que es robusto dicen que "el software es resistente a fallos, capaz de reconocer cuando ha habido fallos y capaz de recuperarse de los mismos". **Están describiendo características de un buen software, no de un buen diseño.** **Un software mal diseñado puede exhibir características positivas**: lleno de funcionalidades útiles, eficiente, robusto, estéticamente atractivo, intuitivo, bien integrado con otros programas del entorno, barato etc. Ninguna de estas cosas nos asegura que su diseño sea bueno. Si seguimos leyendo este segundo artículo, encontramos que casi todas las características que describen son las de un buen software y no las de un buen diseño.

[Aquí](http://wiki.answers.com/Q/What_are_characteristics_of_a_good_software_design?) empiezan mejor encaminados: complejidad mínima, fácil de mantener, autoexplicativo etc. pero acaban por cometer el mismo error. Dicen que un buen diseño es reusable (podría ser), pero luego explican que "diseñamos el sistema para que puedan usarse piezas de él en otros sistemas". **Explicada así, la reusabilidad es de los componentes del sistema, no del diseño. Un sistema mal diseñado puede tener partes fácilmente reusables** (aunque sea accidentalmente). Pasa de nuevo cuando hablan de portabilidad: es difícil saber exactamente a qué se podrían referir al decir que un diseño puede ser portable, pero leyendo la explicación está claro que se refieren a la portabilidad del sistema, no del diseño. **Un software mal diseñado puede ser fácilmente portable** (por ejemplo porque lo hemos hecho en Java).

En todos estos artículos también hay  cosas que realmente caracterizan a un buen diseño de software: lo más simple posible, consistente, documentado, sin duplicación innecesaria, expresado en un lenguaje preciso, mantenible, reusable etc. Pero en ninguno distinguen entre un buen software, y un software bien diseñado.

Que un software tenga un buen diseño interesa a sus desarrolladores presentes y futuros. A los usuarios les da igual que las 20000 líneas de código estén en un único módulo, si la aplicación es atractiva, funciona rápido y cubre sus necesidades. **Que sacar la versión 2.0 de esta aplicación nos cueste dos años en lugar de dos meses por culpa de su mal diseño, tampoco tendrá impacto negativo en los usuarios, porque para entonces ya se habrán pasado a la competencia**. El impacto negativo de un mal diseño de software lo sufren directamente los desarrolladores y la empresa que lo vende, e indirectamente (como mucho) sus usuarios.

Un buen diseño de software nos debe ayudar a construir aplicaciones con características positivas que puedan ser percibidas por sus usuarios (un buen software), pero **ni un buen diseño garantiza un buen software, ni un buen software implica siempre un buen diseño.** Lo que caracteriza a un buen diseño de software es muy distinto de lo que caracteriza a una buena aplicación. Ambas cosas se confunden con frecuencia porque están relacionadas, pero tenemos que ser capaces de distinguirlas porque **difícilmente podremos hacer buenos diseños si no sabemos distinguir qué los caracteriza, y difícilmente podremos hacer buen software si pensamos que para ello nos basta con hacer un buen diseño**.

En la [próxima entrada del blog](https://www.rubenbejar.com/2014/03/ahora-en-serio-que-caracteriza-a-un-buen-diseno-de-software/) hablaremos un poco más de las características de un buen diseño de software y llegaremos a una conclusión que a algunos puede que os sorprenda.



(1) Hablo de diseño de software desde el punto de vista de la ingeniería del software: la actividad que consiste en determinar cómo voy a construir una aplicación o sistema de información que cumpla con unos requisitos determinados, bajo ciertas restricciones de plazos y recursos económicos. No estoy hablando por ejemplo del diseño gráfico de las interfaces de usuario.
