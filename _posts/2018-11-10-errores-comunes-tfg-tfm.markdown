---
author: rbejar
date: 2018-11-10
layout: post
title: "Algunos errores comunes en la escritura de trabajos de fin de estudios en ingeniería"
share-img: https://www.rubenbejar.com/img/share-img/typewriter.jpg
tags:
- Escribir
- TFG
- TFM
- Trabajo Fin de Estudios
- Errores
- Consejos
- Memoria
- Informe
- Proyecto
---

Este texto tiene como objetivo recopilar algunas reflexiones totalmente personales sobre errores y omisiones que he visto cometer a estudiantes en sus memorias de trabajos de fin de grado, y de fin de máster, en ingeniería informática en la [Escuela de Ingeniería de Arquitectura de la Universidad de Zaragoza](https://eina.unizar.es). Guías y recomendaciones generales sobre cómo escribir buenos documentos técnicos se pueden encontrar en otros lugares, y este texto no pretende ser eso. Tampoco voy a entrar en problemas muy técnicos o muy específicos ni en aspectos éticos obvios como el de no apropiarse del trabajo de otros. Tan solo voy a señalar algunos problemas que veo de vez en cuando, algunos en los primeros borradores que mandan mis estudiantes y otros en las memorias finales que ves como miembro de un tribunal, y que creo que pueden solucionarse con poco esfuerzo solo con ser consciente de ellos.

## Hay que empezar explicando cuál es el objetivo del trabajo
Es más que habitual tener que recordar a los estudiantes que lo primero que tienen que poner es el objetivo del trabajo que se presenta, y hacerlo de una manera breve y sencilla. Cuando te toca ser miembro de un tribunal de trabajos de fin de estudios, te llegan proyectos muy variados y tienes poco tiempo para mirártelos. A veces no te haces una idea sobre el objetivo del proyecto hasta que te has mirado una memoria entera. Eso suele ser porque la memoria no lo dice claro. 

También suele ser interesante dar una idea de cuál va a ser el resultado final al principio de la memoria. Que sepas hacia dónde va lo que estás leyendo facilita mucho entenderlo. Es una memoria de proyecto, no una novela. No pasa nada por hacer un *spoiler* del final.

## No hay que pasarse con el contexto
La memoria debe centrarse en el trabajo realizado por la estudiante que lo presenta. Comparar lo que has hecho tú con cosas más o menos parecidas que existan es importante. Pero dedicar páginas y páginas a aspectos vagamente relacionados no. Esto es especialmente crítico cuando el trabajo es la mejora o ampliación de algo ya existente, o cuando se ha hecho como parte de un proyecto mayor, por ejemplo en una empresa. Dedicar mucho espacio a la parte que no has hecho tú, sugiere que la parte que has hecho tú no es muy interesante.

## Hay que explicar las fases de exploración de los problemas
Los problemas complicados nunca se resuelven por hipnosis; aunque los mires fijamente durante mucho tiempo, la solución completa y correcta no se va a materializar automáticamente en tu mente. En un trabajo final de estudios de ingeniería es normal que para algunos aspectos del mismo haya que haber probado distintas aproximaciones hasta dar con una solución aceptable. A los estudiantes en general les cuesta explicar estos aspectos más explorativos de su trabajo en las memorias, como si se avergonzasen de no haber adivinado a la primera cuál era la mejor solución de su problema. Siempre que esa exploración haya sido racional y suficientemente sistemática, solo los más ingenuos e inexpertos lectores pensarán que eso es un fallo. Y además esas suelen ser las partes más interesantes del trabajo, porque han sido las más complicadas de solucionar.

## Los trabajos de fin de estudios son, salvo algunas pocas excepciones, trabajos individuales
Pero es bastante habitual, por ejemplo, que los estudiantes te indiquen que han seguido una metodología como Scrum (que es una metodología de trabajo **en equipo**). También es frecuente que excusen alguna mala práctica (no usar control de configuraciones de código, nombrado de ficheros aleatorio, planificación absolutamente improvisada...) porque "es un proyecto de una sola persona". 

Se presenta un trabajo de ingeniería. Individual, de corta duración, de complejidad normalmente moderada, pero es un trabajo de ingeniería, y debería reflejar las mejores prácticas aprendidas, aunque algunas de estas solo sean realmente útiles cuando se trabaja en equipo y en proyectos más grandes.

## Algunas cosas no se pueden poner a medias
Por ejemplo, si tu trabajo consiste en el análisis, diseño e implementación de una aplicación móvil, no bastan con que pongas unos cuantos de los requisitos "a modo de ejemplo", los tienes que poner todos o parecerá que ese análisis no lo has hecho completo. Aunque parezca obvio, de vez en cuando tengo que recordar esto para casos de uso, casos y guiones de pruebas etc.

Las figuras sueltas no suelen ser muy útiles. Casi todas las figuras requieren un contexto y unas explicaciones. También es más habitual de lo que parece encontrarte figuras que nunca se mencionan en el texto, y hasta secciones de la memoria cuyo único contenido es una figura (sin contexto ni explicaciones). 

Si dices que algunos de tus, por ejemplo, requisitos, son básicos o fundamentales, y luego no pones otra clase de requisitos (opcionales, avanzados, o lo que sea), estás pidiendo a gritos que alguien te pregunte que dónde están. 

## Y algunas cosas es mejor no ponerlas en absoluto
Frases como "lo he probado **a ojo**" o "**por suerte** se probó en un entorno de pruebas y no en el de producción" las he visto en borradores de memorias. Yo entiendo que si se ha hecho el proyecto en una empresa, es posible que la calidad no haya sido la primera consideración. Y entiendo que bajo presión de tiempo o falta de recursos, uno puede tener que dejar de lado ciertas prácticas más o menos importantes. Pero la pruebas son esenciales, y deberían ser deliberadas, sistemáticas y, en lo posible, automáticas. Y hacerse en entornos de pruebas adecuados. Si no se han hecho así, el estudiante seguramente tendrá que explicarlo si se le pregunta durante la defensa del trabajo. Pero poner así de claro en la memoria estas cosas señala que el estudiante no solo ha hecho estas cosas "mal", sino que las ha hecho mal sin ser consciente de lo mal hechas que están, lo que es más difícl de justificar.

Esta frase estaba casi literalmente en un borrador de una memoria: "...y un archivo XML que no será utilizado en este proyecto...". Si no será usado, ¿por qué está ahí? ¿Y por qué me lo cuentas? Este es otro de esos casos: o cuentas algo más, o no cuentes nada en absoluto.

## Abusar del relleno queda fatal
Los esfuerzos por engordar las memorias a base de páginas semivacías, quizás con una captura de pantalla y dos líneas de texto, de imágenes repetitivas (diez ejemplos de algo que ya se ve claro con los dos primeros), márgenes excesivos etc. son extremadamente cantosos y tremendamente inefectivos. Y más hoy en día, que las memorias ya no se imprimen en papel, con lo que se pierde hasta el efecto de ese sesgo que nos hace valorar más las cosas más pesadas (<https://www.telegraph.co.uk/news/science/science-news/9543903/Heavier-wine-bottles-appear-more-expensive.html>, <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3005631/>). 

Tampoco es interesante llenar la memoria de anexos con manuales de procedimiento, estándares o cualquier otra cosa que no es parte del trabajo realizado, algo que también se ve de vez en cuando. Si son tan interesantes, una brevísima explicación de lo que son junto con una cita bibliográfica será más que suficiente. 

