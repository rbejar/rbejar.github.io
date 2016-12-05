---
author: rbejar
comments: true
date: 2013-04-03 18:30:42+00:00
layout: post
link: http://www.rubenbejar.com/2013/04/goodbye-evernote-hello-synchronized-markdown-plain-text-notes/
slug: goodbye-evernote-hello-synchronized-markdown-plain-text-notes
title: Goodbye Evernote. Hello Plain Text Notes
wordpress_id: 194
tags:
- Tips
- Desktop
- Online Service
---

I have quite a lot of information in text notes, and most of it is just plain text. In the last years I've tried several approaches to:



	
  * Write simple notes easily. Mostly plain text notes, but with some internal organization and style (headers, bullet points, emphasized words...).

	
  * Have those notes categorized or tagged.

	
  * Be able to make full text searches on my notes (on all of them, or only on a subset).

	
  * Have those notes accessible from almost any device with an Internet connection.

	
  * Support offline access (read and write) to my notes from my devices, specially my Linux laptops and, more occasionally, my Android smartphone. Offline updates should be synchronized easily when connected again.


For some time I used [Tomboy](http://projects.gnome.org/tomboy/) and synchronized the notes using [Dropbox](https://www.dropbox.com/). Synchronization was a problem sometimes but overall it worked for me. Until I got my smartphone, and discovered that accessing Tomboy notes in Dropbox from an Android smartphone was a problem (I don't remember the details, but I remember that I got convinced that I needed a better solution).

Then, I went for [Evernote](https://www.evernote.com/). It had everything I wanted: free for the basic functionality (all that I need), web client, Android client, [unofficial Linux desktop client](http://sourceforge.net/projects/nevernote/), searches, notebooks for categories, styled text, and it offers some extra stuff that sometimes comes handy (e.g. attaching a PDF or an image to a note). I moved my notes there and it worked. After some time, however, I discovered that the unofficial desktop client did not synchronize well locally edited styled text notes. I was able to keep offline copies of my notes with the desktop client, but I was not able to reliably update them (neither offline nor online). I don't know if this is a problem with the other desktop clients, but I have been using just the web and Android clients for several months, and this has finally been a deal breaker.

So now I have a new approach: I use plain text notes with [Markdown syntax](http://daringfireball.net/projects/markdown/syntax).



	
  * I have a notes folder in Dropbox, and inside I have other folders for categories. I can access my notes from any computer with a web browser and an Internet connection if necessary.

	
  * I can open the notes with any plain text editor. If the editor "understands" Markdown, it will style (or highlight) the text, but that is more than enough for me). If not, it is not a big issue because, after all, Markdown is just **legible** plain text.

	
  * Dropbox synchronizes the directory among my computers pretty well, even with my Android smartphone (you have to mark as favorites all your notes in the official Dropbox app, but it is just once).

	
  * I use [920 Text Editor](https://play.google.com/store/apps/details?id=com.jecelyin.editor&hl=es) to open the notes in the smartphone, and [Kate](http://kate-editor.org/) in my Linux computers (I use KDE). Both editors support text searches in directories, so I can search my notes easily. Kate "knows" the Markdown syntax, and highlights the text files (920 Text Editor doesn't, but for the smartphone that is not a big issue as the plain text is legible enough).

	
  * To have a quick access to the notes, I have a Kate session that opens in the notes directory, and a keyboard shortcut that opens Kate with that session if it is not already opened. In my smartphone I have a link to the notes directory in Dropbox in my home screen, and the .markdown extension linked to 920 Text Editor, so accessing my notes or writing new ones is convenient and fast.


If I ever have synchronization problems, it is just plain text, so I expect to be able to solve them easily. In the worst case I can use diff. Dropbox is my current choice, but I could be using [Ubuntu One](https://one.ubuntu.com/), or other similar services. I could even use Subversion or Git (although the support in Android could be a problem in this case).

I use Kate, but as long as your text editor supports sessions (or similar), Markdown syntax highlighting and directory searches, you have what you need. One advantage of this approach to notes is that you don't need to use a different application just for them. I use Kate and Markdown all the time, and I am already comfortable with them. Of course, this approach works with any OS and smartphone platform.

I have been using this solution for a while, and it seems to work as expected. Of course it is not a substitute for Evernote (or similar services) if you are a "power user", bur for my plain vanilla text notes it works well, and doesn't require a new application. Notes are just plain text files, with some organization and style courtesy of Markdown, and I can use any synchronization service. Mostly open source, and pretty simple, as I like it.
