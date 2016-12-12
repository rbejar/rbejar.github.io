---
author: rbejar
comments: true
date: 2016-12-11
layout: post
title: Documentación ágil de decisiones de diseño
subtitle: Architecture Decision Records (ADRs)
share-img: http://www.rubenbejar.com/img/share-img/Arq-Code.png
tags:
- Agile methods
- Software Engineering
- Software Architecture
---

Diseñar software requiere tomar muchas decisiones. La documentación arquitectural y el código fuente reflejarán los resultados de esas decisiones, pero el razonamiento que llevó a ellas se puede perder fácilmente. La exposición de razones (*rationale*) es la parte de la documentación arquitectural donde se recogen estos razonamientos, al menos de las decisiones con más implicaciones. 

¿Qué decisiones hay que documentar? Principalmente las que tienen un efecto importante en el sistema (en su funcionalidad o en su calidad), las que costaron tiempo y largas discusiones, o pruebas, o prototipos, y las que son difíciles de entender, poco usuales o inesperadas. El objetivo de esta documentación es ser una memoria auxiliar para los diseñadores del sistema, un mecanismo para cortar discusiones redundantes, una herramienta de comunicación y formación para las nuevas incorporaciones al equipo de desarrollo.

El libro [Documenting Software Architectures, Views and Beyond (2nd Edition)](https://resources.sei.cmu.edu/library/asset-view.cfm?assetID=30386) propone un modelo con hasta 11 puntos para cada decisión que se quiera documentar (asunto, decisión y estado, etiquetas, asunciones, alternativas etc.). Cada decisión se incluiría en el documento de la arquitectura del sistema en la sección correspondiente (por ejemplo, la exposición de razones sobre una decisión que atañe a una vista de módulos, se incluiría en esa sección). El formato de este documento puede ser el que se decida para el proyecto, desde un documento ofimático a una wiki.

Hoy quiero comentar una alternativa compacta y pragmática, adecuada incluso para proyectos ágiles (recordatorio: las metodologías ágiles no están en contra de la documentación, solo están en contra de la documentación que no aporta valor). Esta alternativa son los [*Architecture Decision Records*](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) (ADR, registros de decisiones arquitecturales). Cada ADR se mantiene en un fichero de texto (por ejemplo en Markdown) que se guarda en el repositorio junto al código fuente (en general es importante mantener la documentación bajo control de versiones, y si es documentación de diseño es buena idea mantenerla bajo control de versiones junto al código). Por ejemplo, se puede guardar en una ruta así `doc/arch/adr-NNN.md` donde los NNN son números correlativos que identifican a los ADR (y que por tanto no reusaremos). Cada ADR tiene 5 secciones (título, contexto, decisión, estado, y consecuencias) y un ADR debería ocupar entre una y dos páginas de texto. Aunque crear y mantener los ADRs es sencillo, hay [alguna herramienta de línea de comandos](https://github.com/npryce/adr-tools) para facilitarlo.

Documentar las razones detrás de las decisiones de diseño más importantes es fundamental en cualquier proyecto de software que vaya a mantenerse durante tiempo, y los ADR son una aproximación directa y práctica que puede ser útil en tu próximo proyecto.
