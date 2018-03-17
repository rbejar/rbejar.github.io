---
author: rbejar
date: 2018-03-17
layout: post
title: "Los workflows de Git (II): ramas de características"
share-img: http://www.rubenbejar.com/img/share-img/GitMerge.png
tags:
- Git
- Gestión
- Aǵil
- Desarrollo
- Devops
- Feature branches
- Integración continua
- Despliegue continuo
---

En el [post anterior]({{base.url}}/2018/03/git-workflows-centralizado/) me centré en analizar las razones para elegir, o no elegir, el *workflow* centralizado cuando se trabaja con Git considerando tanto las circunstancias de cada proyecto —equipo o equipos, producto y objetivos— como tres componentes fundamentales de los proyectos de software sobre los que esta elección tiene impacto: desarrollo, operaciones y gestión.

En este voy a hacer algo parecido sobre las ramas de características. Igual que en el post anterior no voy a explicar lo que son, eso está hecho bien en otros sitios, sino que directamente iré a las circunstancias que hay que considerar para decidir si usarlas o no.

## Ramas de características (*Feature branching*)

Aunque considerar esto como un *workflow* completo puede ser un poco exagerado, las [ramas de características](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow) son como mínimo un componente de otros *workflows* comunes, y una técnica que puede adaptarse a distintas formas de trabajar, así que es interesante plantear cuándo son más útiles, y cuándo menos.

El peligro principal de las ramas de características son las integraciones. Si has estado varios días trabajando en una rama aislada de la principal, quizás con algún *git fetch/merge* o *git pull* ocasional para mantener un mínimo de sincronización con master, y al final de ese proceso integras tu código es probable que no tengas muchos problemas. En el peor de los casos si esos *fetch/merge* o *pull* han sido poco frecuentes, es posible que esa integración tarde una hora en lugar de unos minutos. Si no necesitas integración ni entrega continuos, esto puede funcionarte bien. 

El riesgo es bastante mayor cuando hay varias personas trabajando en ramas de características distintas simultáneamente. Aunque cada una de esas personas haya hecho alguna sincronización ocasional de la rama master con su rama de características, los cambios que van haciendo en estas ramas no son visibles para los demás hasta que completen e integren el trabajo. Y es en ese punto cuando surgen los problemas graves. Estos no serán los conflictos de *merge* o problemas con la sintaxis del código. Costará un poco más hacer esto que si se integra con más frecuencia, pero lo difícil no va a ser tener un *commit* sin conflictos y que se compile. El problema es tener eso, y además mantener un código correcto y mantenible. Cualquier cambio hecho en una rama que afecte a la corrección del código de la otra rama solo va a aparecer en este punto, cuando ya llevamos días, incluso semanas, avanzando en paralelo.

Estas *big bad integrations* tienen otros efectos secundarios. Por ejemplo, cada desarolladora tratará de minimizar los cambios que hace en su rama por miedo a que cualquiera de esos cambios suponga luego más trabajo al integrar. Pero eso implica que vamos a minimizar las refactorizaciones del código, lo que implica acumulación de [deuda técnica](https://www.martinfowler.com/bliki/TechnicalDebt.html) y, por tanto, problemas en el futuro.

La práctica de la integración continua nace esencialmente para evitar este tipo de problemas. **Las ramas de características y la integración continua**, y por tanto la entrega o desplegue continuos, **son incompatibles**.  


### Integración promiscua

Si se trabaja con ramas de características, una forma de simplificar las integraciones de estas con la rama master es que los que trabajan en ramas de características en paralelo se integren entre sí con cierta frecuencia —Martin Fowler ha llamado a esto "integración promiscua"—. Así, al integrar con master ya habrán tenido la oportunidad de descubrir y solucionar bastantes problemas. Aunque esto sigue sin permitir hacer integración continua, al menos se reducen el esfuerzo y los problemas causados por las *big bad integrations*.

El mayor riesgo de esta práctica es que el diseño del software pasa a verse muy influenciado por la comunicación, o falta de ella, entre los desarrolladores(*). Con integración continua se está constantemente chequeando que el código de todo el mundo se integra bien con el de los demás, y cualquier problema es obvio y surge inmediatamente. Con integración promiscua, se integra solo aquello que dos o más desarolladores han decidido integrar, y cuando deciden hacerlo. Si alguien tiene dudas sobre si lo que está haciendo va a afectar negativamente al código de otras ramas de características, va a tener que empezar a preguntar e indagar. Cada nueva integración de una rama de características hará más difícil mantener la coherencia del diseño.

(*) En lo que es una encarnación más de la [ley de Conway](https://en.wikipedia.org/wiki/Conway%27s_law).

### Relación con la gestión del proyecto y el trabajo en equipo

Cada rama de características que aún no ha sido integrada con la rama máster es WIP (*work in progress*). El exceso de WIP aumenta el tiempo de ciclo, esencialmente el tiempo que transcurre entre que decidimos hacer algo y que lo hemos completado y entregado, y normalmente querremos reducirlo para tener una buena cadencia de entrega de resultados. Un proyecto que normalmente tenga muchas ramas de características vivas al mismo tiempo puede que no esté gestionando bien esto.

Si una desarrolladora del equipo termina lo que estaba haciendo y en lugar de ayudar a terminar algo en marcha decide empezar con una característica nueva —o se le asigna como trabajo que empiece con una característica nueva—, es posible que estemos ante un problema relacionado con la gestión del proyecto. Algunos ejemplos:

- Puede ser que no hay priorización clara de las tareas a realizar, y por tanto pensemos que podemos permitirnos empezar cosas nuevas sin haber terminado otras que realmente son más prioritarias.
- Puede ser que haya una mala división del trabajo que no permita asignar fácilmente tareas más pequeñas que la de implementar una característica completa a los miembros del equipo.
- Puede que no tengamos un equipo lo bastante multidisciplinar y que habiendo tareas por hacer y gente disponible para hacerlas, normalmente no podamos asignarlas porque las personas están demasiado especializadas.

### Trabajo en características largas o complicadas

A veces se defiende el uso de ramas de características cuando algunas características van a tardar bastante tiempo en ser desarrolladas, y mientras tanto tenemos que seguir manteniendo —corrigiendo y actualizando— el producto. **Lo malo** de usar ramas de características para esto **es tratar de delegar en el sistema de control de versiones un problema que realmente es de diseño y operaciones del software**. Alternativas:

- Divide la característica grande en varias más pequeñas que tengan sentido por sí mismas.
- Integra todo el código de la característica continuamente, excepto la parte de GUI. De esa manera los usuarios pueden recibir actualizaciones sin verse afectados, y lo único que te faltará es integrar la parte de GUI en el momento en que hayas terminado lo demás, algo que deberías poder hacer en un único sprint/iteración/ciclo de lanzamiento.
- Y solo si las dos anteriores, que son más sencillas, no te sirven, puedes utilizar [Feature Toggles o Feature Flags](https://martinfowler.com/articles/feature-toggles.html). La idea esencial de esta técnica es tener ficheros de configuraciones con "interruptores" para ciertas características que están en desarrollo. La aplicación en ejecución lee el valor de estos interruptores y te muestra, o no, la nueva característica.

Si lo que tienes que hacer es una actualización importante del código y está relativamente bien localizada, p.ej. sustituir un framework o un componente grande por otro, mientras lo mantienes actualizado en sus versiones actuales, entonces puedes utilizar ramas por abstracción [Branch by Abstraction](https://paulhammant.com/blog/branch_by_abstraction.html). La idea esencial es crear una capa que abstraiga al resto del código del framework o componente que vas a cambiar, luego desarrollar una nueva implementación de esta capa abstracta y finalmente sustituir una implementación por otra. Lo bueno de trabajar así es que puedes hacerlo mientras haces integración continua, porque la nueva implementación de esa capa abstracta no tiene por qué estar completa hasta que decidas hacer la migración desde la antigua a la nueva. Si esta abstracción está bien diseñada, y has probado adecuadamente el código nuevo, esa migración será muy sencilla.

### Conclusión

Con cosas que he mencionado solo de pasada en este post se podrían escribir unos cuantos capítulos de un libro, así que además de los enlaces que he puesto debajo algunas cosas más para leer.

Lo más importante que dice este post es que **apoyarnos solo en el sistema de control de versiones para resolver problemas que son de diseño y de operaciones del software y de gestión del proyecto es mala idea**. Las ramas de características tienen su utilidad, especialmente cuando no necesitas hacer integración continua, cuando tienen una vida no muy larga y cuando no tienes muchas al mismo tiempo. Si te encuentras usándolas para más que esto, es posible que en realidad tengas un problema de arquitectura, de operaciones o de gestión del proyecto del que no eres consciente. 



**Para más información**

- ["Feature Branch" by Martin Fowler](https://martinfowler.com/bliki/FeatureBranch.html).
- ["Paying Down Your Technical Debt" by Jeff Atwood](https://blog.codinghorror.com/paying-down-your-technical-debt/).
- ["Feature Toggle" by Pete Hodgson](https://martinfowler.com/articles/feature-toggles.html).
- ["Branch by Abstraction" by Martin Fowler](https://martinfowler.com/bliki/BranchByAbstraction.html).
- ["Scrum. Principios Ágiles". Transparencias de Rubén Béjar](https://github.com/UNIZAR-30248-GeProSoft/scrum-slides/blob/master/PDF/7i_GPS-S02-Scrum-Principios%C3%81giles.pdf).
