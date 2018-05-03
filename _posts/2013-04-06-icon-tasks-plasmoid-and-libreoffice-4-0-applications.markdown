---
author: rbejar
comments: true
date: 2013-04-06 16:30:59+00:00
layout: post
link: https://www.rubenbejar.com/2013/04/icon-tasks-plasmoid-and-libreoffice-4-0-applications/
slug: icon-tasks-plasmoid-and-libreoffice-4-0-applications
title: KDE Icon-Only Task Manager and LibreOffice 4.0 Applications
wordpress_id: 236
tags:
- Quick tips
- KDE
- Linux
---



If you have added LibreOffice 4.0 applications to the icon-only task manager in a KDE desktop panel, but when you open a LibreOffice document a new icon appears on the panel instead of  a marker on the one you have anchored there, like in the next image, there is a simple solution.

![Icon-Tasks Problem](/img/posts/IconTasksProblem-300x226.png)

I have tried this in Kubuntu 12.04 with LibreOffice 4.0, but it should work in other KDE environments. First, you have to drag and drop the launchers for the LibreOffice applications you want in your icon-only task manager from the KDE Application Launcher. Then right click on that task manager, choose "Icon-Only Task Manager Settings", then "Launcher Matching Rules", and add one rule per each LibreOffice application you have: the Window classes will be libreoffice-writer, libreoffice-impress, libreoffice-calc, etc. and you can select the launcher by clicking on the icon right to the "Launcher:" text box. See the next image:

![Launcher Properties Libre Office 4.0](/img/posts/LauncherPropertiesLibreOffice-300x245.png)

Window class and window name can be automatically filled when you click on the the "Detect Window Properties" button and then on an application window for that launcher. That would be the general solution to this problem, however in this case that didn't work, at least for me, until I left the window name box empty as the previous image shows. You can see the problem solved in the last image.

![Icon-Tasks Solution](/img/posts/IconTasksSolution-300x208.png)
