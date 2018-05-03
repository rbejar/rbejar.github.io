---
author: rbejar
comments: true
date: 2013-03-21 21:53:52+00:00
layout: post
link: https://www.rubenbejar.com/2013/03/gvim-does-not-take-the-full-screen-when-maximized-in-kde/
slug: gvim-does-not-take-the-full-screen-when-maximized-in-kde
title: GVim Does not Take the Full Screen When Maximized in KDE. Solved
wordpress_id: 52
tags:
- Quick tips
- KDE
- Linux
---

**Problem:** you maximize the GVim window but it does not take the full screen as it should: there are gaps in the sides and/or above the title bar.

**Diagnostic (simplistic!):** it seems that some character-based applications would have some restrictions about their sizes because they do not “measure” those sizes in pixels but in characters. It looks like GTK and KWin are not understanding each other in this situation.

**Solution:** tried in Kubuntu 12.04, but it should work in other KDE environments. Click on the title bar of a GVim Window > Advanced > Application specific options > Size and position / Follow geometry restrictions - Force - No. The name of the options in the menus may not be exactly like that in English because I am translating on the fly from the Spanish GUI labels.





