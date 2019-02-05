---
layout: slides
title: "Commandline"
---

<section markdown="block" class="intro-slide">
# {{ page.title }}


<p><small></small></p>
</section>

<section markdown="block" class="title-slide">
## What's a Command Line Interface (CLI)

It's a way of __interacting with your computer__ (or... errr... another computer?)

* {:.fragment} you give it __instructions by typing a command__ 
* {:.fragment} a __command__ is some sequence of characters
* {:.fragment} after you press &lt;ENTER&gt;, the computer does _stuff_!
* {:.fragment} you usually get some feedback or output
</section>


<section markdown="block">
## Command Line Topics

* command line basics
	* getting around the file system
	* finding and manipulating files
* other command line tools
</section>

<section markdown="block">
## Motivation

__[This is hard! Let's go shopping!](http://snowclones.org/2008/02/19/x-is-hard-let%E2%80%99s-go-shopping/) _Why_ are we learning this? &rarr;__

* {:.fragment} uploading files / working on the server 
* {:.fragment} many tools require use of the command line
* {:.fragment} automation
* {:.fragment} experience different platforms / tools
* {:.fragment} lookin' [1337](http://en.wikipedia.org/wiki/Leet)
</section>

<section markdown="block">
## Terminal

* On MacOS, the command line interface using an application called __Terminal__. 
* __Open it.  It's probably under Applications &rarr; Utilities. &rarr;__
* On windows... ummmm. `cmd.exe` (or use cmder, cygwin, etc. ... or use putty to login to a machine with a different OS)

</section>

<section markdown="block">
## Terminal vs GUI

This is basically an alternative interface to your computer

* {:.fragment} you can do a lot of things in terminal that you can do by clicking through folders, windows, and applications with your trackpad/mouse
* {:.fragment} it's primarily text based input and output
</section>

<section markdown="block">
## __Demo__: A Quick Tour

__In your OS... how do you?__ &rarr;

* create, copy, edit, and list files 
  * {:.fragment} (finder, TextEditor, Windows Explorer, Notepad)
* see processes, stop processes 
  * {:.fragment} (Activity Monitor / Task Manager)
* find files 
  * {:.fragment} (finder, spotlight, _cortana_ 🤦‍)

__Welllllll... you can do all of that through the terminal!__
{:.fragment}
</section>

<section markdown="block">
# Entering Commands
</section>

<section markdown="block">
## Commands

__Commands__ are __verbs__; they tell the computer to do something.
</section>

<section markdown="block">
## Entering a Command 

Once you have Terminal open, you should see a string of characters that ends with a dollar sign.  This is called the __command prompt__.  A __prompt__ looks something like this.

<pre><code data-trim contenteditable> walsh-9:~ joe$
</code></pre>

Whenever you see a line in these slides prefixed with a $, that means that we're typing something in at the __prompt__.
</section>

<section markdown="block">
## Executing a Command

In terminal, type in the name of the command, and press &lt;ENTER&gt;.  __Let's trying using ls, a command to list files and directories__ &rarr; 

* open Terminal (Applications &rarr; Utilities &rarr; Terminal
* type __ls__
* press &lt;ENTER&gt;

<pre><code data-trim contenteditable>
$ ls
</code></pre>
</section>

<section markdown="block">
## Where Are You?

Note that when you're at the prompt, you're always running commands in the context of some location on your computer.  

* This location corresponds to an actual directory.  
* You can change _where you are_ using various commands.  We'll see that later.
</section>

<section markdown="block">
## Let's Repeat That: At the prompt, you're running commands in the context of some location (think folder/directory) on your computer

</section>

<section markdown="block">
## What Was That Again? 

* when you're at the prompt
* and you type in a command
* you're doing so while you're in a particular folder/directory
* you're always _located_ somewhere on your file system

</section>

<section markdown="block">
## Arguments

__Arguments__ are the thing or things that a command acts on; they're like __nouns__ (or more formally, __direct objects__).
</section>

<section markdown="block">
## Commands and Arguments

Some commands can optionally have __arguments__:  

* they go after the command name
* a command may potentially be able to take 0 or more arguments

__Try this (list files in Desktop):__

<pre><code data-trim contenteditable>
$ ls Desktop
</code></pre>
</section>

<section markdown="block">
## Flags

__Flags__ are like __adverbs__.  They specify how a command is run.

(sometimes they're also called _options_)
</section>

<section markdown="block">
## Commands and Flags

__Commands__ can optionally have __flags__.  

* they go after the command name, but usually before arguments
* they are specified with either - or --
* commands may have 0 or more flags.  

__Try this (list all, including hidden, files in Desktop):&rarr;__

<pre><code data-trim contenteditable>
$ ls -a Desktop
</code></pre>
</section>

<section markdown="block">
## &lt;TAB&gt; Completion

You can use the &lt;TAB&gt; key to complete commands or file names.  __Try typing the following:&rarr;__

* ls Desk&lt;TAB&gt;
* __What happens? &rarr;__

The argument, Desktop, is automatically completed for you!  __Go ahead and run the command by pressing &lt;ENTER&gt; &rarr;__
{:.fragment}
</section>

<section markdown="block">
## &lt;TAB&gt;&lt;TAB&gt;

What if there are multiple matches?  __Type the letter l and then &lt;TAB&gt;. What happens? &rarr;__

Nothing.  Now try hitting &lt;TAB&gt; one more time.  __What happens? &rarr;__
{:.fragment}

All of the possible commands that start with the letter l are shown.
{:.fragment}
</section>

<section markdown="block">
## Next and Previous Commands

You can use the &lt;UP&gt; or &lt;DOWN&gt; keys to go through previous and next commands.  __Try pressing &lt;UP&gt; twice, and &lt;DOWN&gt; once.  What command is shown?__

<pre><code data-trim contenteditable>
$ ls Desktop
</code></pre>
</section>

<section markdown="block">
## Errors

Type the letter l and press &lt;ENTER&gt;. 

<pre><code data-trim contenteditable>
$ l
</code></pre>  

__What happens? &rarr;__

<pre><code data-trim contenteditable>
-bash: l: command not found
</code></pre>
{:.fragment}
</section>

<section markdown="block">
## More Errors

Type ls foo and press &lt;ENTER&gt;. 

<pre><code data-trim contenteditable>
$ ls foo
</code></pre>  

__What happens? &rarr;__

<pre><code data-trim contenteditable>
ls: foo: No such file or directory
</code></pre>
{:.fragment}
</section>



<section markdown="block">
## Navigating the File System

<aside>In Three Parts</aside>

* OSX's directory structure
* A little bit about pathnames
* How to get around using the commandline
</section>

<section markdown="block">
## Let's Look at the MacOS Directory Structure
</section>

<section markdown="block">
## First, Some Definitions

What's a __directory__? &rarr;

* {:.fragment} a __directory__ is a cataloging structure on a file system that references other files (and directories)
* {:.fragment} we can think of it as _a thing that contains files_ (it's a little more complex than that, though)
* {:.fragment} they're usually used to organize files
</section>

<section markdown="block">
## More Definitions

What's a __folder__? &rarr;

* {:.fragment} it's essentially the same thing as a directory
* {:.fragment} but it's the graphical representation (like the little folder icons in finder)
</section>

<section markdown="block">
## Even More Definitions

What's a __pathname__? &rarr;

* a __pathname__ is the general form of the name of a file or directory; it specifies a unique location in a file system
* for example, in finder, to locate a file or folder, you follow a particular path - __let's check this out__ &rarr;. 
* __what's the path to the Desktop starting from the _top most_ folder, the hard drive (probably Macintosh HD on the lab computers)?__ &rarr;
{:.fragment}
</section>

<section markdown="block">
## Some Structure

Each operating system organizes their files and directories differently.  OSX's file structure looks like this (it's similar to other UNIX based file systems):

* __/__ - (also called __root__) the top most folder on a disk (the directory that _contains_ all of the other files and directories)
* __/Applications__ - where shared applications are kept
* __/Users__ - all user accounts and their accompanying files are stored here
* __/Volumes__ - all disks that are attached to your computer including USB drives, hard drives, etc.
* __/System__ - _system specific_ files, libraries, preferences that are critical to the operating system

</section>

<section markdown="block">
## More About the User's Directory

It's worth noting the directories nested under Users.  They should seem familiar to you.

* __/Users/username__ - (also called __home__ when you're in your own username's directory) contains files specific to that particular user
* __/Users/username/Desktop__ - represents the user's Desktop
* __/Users/username/Downloads__ - the user's downloads folder
</section>


<section markdown="block">
## And Now... To Pathnames!

<aside>We know a little bit about the file system structure; let's take a closer look at how we locate files</aside>
</section>

<section markdown="block">
## What's a Pathname Again?

A __pathname__ is the general form of the name of a file or directory; __it specifies a unique location in a file system__.
</section>

<section markdown="block">
## Path Separator

A __path separator__ is a character that's used to join together each directory in a pathname that contains nested directories (for example, Desktop was located under Users and username...  there was a character that separated each directory).  

__What character represents the path separator on MacOS (we just saw this)?__ &rarr;

* it's a __forward slash__, __/__
* (sometimes just called __slash__ when referencing directories) 
* it's __not backslash__ (that's the path separator for Windows!)
{:.fragment}
</section>

<section markdown="block">
## Absolute vs Relative Paths

* __absolute paths__ are paths expressed as starting from root
	* example: /Users/username/Desktop
* __relative paths__ are paths expressed as relative from the current working directory
	* example (if you're starting from /Users/username): Desktop

</section>

<section markdown="block">
## Some Special Paths

There are shortcuts to represent specific paths:

* __~ (tilde)__ is _your_ home directory
* __/ (slash)__ is root directory

The following paths are relative to the directory _that you're in_:

* __. (dot)__ is the current directory
* __.. (dot dot)__ is the parent directory
* __../.. (dot dot slash dot dot)__ is the parent of the parent directory

</section>

<section markdown="block">
## Let's See Some Pathnames Through Finder

* Desktop
* Downloads
* root (probably Macintosh HD)
</section>

<section markdown="block">
## Now That We Know About Pathnames, We Can Navigate the File System Using the Commandline! (EXCITED YET!?)

<aside>Let's learn some commands</aside>
</section>

<section markdown="block">
## ls

__List all of the files (and directories) in the current directory. &rarr;__ 

Think: _list_ (we just saw this!).

<pre><code data-trim contenteditable>
$ ls
Applications	Documents   ....
</code></pre>
</section>

<section markdown="block">
## ls pathname

__List all of the files (and directories) in the directory specified by the pathname. &rarr;__ 

<pre><code data-trim contenteditable>
$ ls Desktop
cuny-first.png		fractal mountains
</code></pre>
</section>

<section markdown="block">
## ls -l

__The -l flag gives detailed output about each file in the directory &rarr;__ 

Think: _l for long version_.

<pre><code data-trim contenteditable>
$ ls -l
drwx------   3 joe  staff   102 Nov  1 15:08 Applications
drwx------+  7 joe  staff   238 Jan 28 22:46 Desktop
</code></pre>
</section>

<section markdown="block">
## ls -a

__The -a flag lists all files, including hidden ones &rarr;__ 

Think: _a for all_.

<pre><code data-trim contenteditable>
$ ls -a
.			.config			Dropbox
</code></pre>
</section>

<section markdown="block">
## ls -al

__You can combine flags by placing them one after the other.  This outputs a detailed list of all files. &rarr;__ 

<pre><code data-trim contenteditable>
$ ls -al
drwxr-xr-x+ 67 joe   staff   2278 Jan 30 02:07 .
drwxr-xr-x   5 root  admin    170 Aug 13  2011 ..
-rw-r--r--@  1 joe   staff  24580 Jan 30 02:19 .DS_Store
-rw-r--r--   1 joe   staff   3459 Mar 21  2011 .RData
</code></pre>
<!-- remove_highlight -->
</section>

<section markdown="block">
## ls -t

__The -t flag sorts by time. &rarr;__ 

<pre><code data-trim contenteditable>
$ ls -lt
total 0
drwxr-xr-x   2 joe  staff    68 Jan 30 02:07 mtec1002
drwx------@ 19 joe  staff   646 Jan 29 21:21 Dropbox
drwxr-xr-x   9 joe  staff   306 Jan 29 19:31 projects
</code></pre>
<!-- remove_highlight -->
</section>

<section markdown="block">
## Combining Flags and Arguments

You can use multiple flags... and combine them with an argument as well. __What do you think this does?__ &rarr;

<pre><code data-trim contenteditable>
$ ls -alt Desktop
</code></pre>

It lists all of the files in Desktop (if you're in your _home_ folder), ordered by time, including hidden files and showing extra information.
{:.fragment}

<pre><code data-trim contenteditable>
drwxr-xr-x+ 40 joe  staff    1360 Jan 29 01:12 ..
-rw-r--r--@  1 joe  staff    6148 Jan 25 01:46 .DS_Store
drwx------+  6 joe  staff     204 Jan 24 08:26 .
-rw-r--r--@  1 joe  staff  245447 Jan 23 23:15 cuny-first.png
drwxr-xr-x  16 joe  staff     544 Oct 28 18:46 fractal mountains
-rw-r--r--   1 joe  staff       0 Aug 31 22:41 .localized
</code></pre>
{:.fragment}
<!-- remove_highlight -->

</section>

<section markdown="block">
## pwd

__Shows the directory that you're currently in.__ &rarr;

Think: _print working directory_.

<pre><code data-trim contenteditable>
$ pwd
/Users/joe
</code></pre>
</section>

<section markdown="block">
## hostname

__Prints out the name of your computer &rarr;__

<pre><code data-trim contenteditable>
$ hostname
walsh-9
</code></pre>
</section>

<section markdown="block">
## mkdir

__Creates a directory with the name of the argument supplied. &rarr;__

Think: _make directory_

One argument is _required_: the name of the directory to create.

<pre><code data-trim contenteditable>
$ mkdir my_animated_gifs
</code></pre>
</section>

<section markdown="block">
## mkdir dir1/dir2/dir3

__This attempts to create 3 directories nested within eachother. &rarr;__

Forward slash (/) shows that a directory is within the directory preceding it.  dir1/dir2 means dir2 in dir1.

However, nested directories don't work as an argument for mkdir. (Unless...)
<pre><code data-trim contenteditable>
$ mkdir dir1/dir2
mkdir: dir1: No such file or directory
</code></pre>
</section>

<section markdown="block">
## mkdir -p dir1/dir2

__The -p flag allows you to create multiple directories nested within eachother. &rarr;__

<pre><code data-trim contenteditable>
mkdir -p dir1/dir2
$ ls
dir1
$ ls dir1
dir2
</code></pre>
</section>

<section markdown="block">
## cd

__Changes current directory to the directory specified in the argument. &rarr;__

Think: _change directory_

One argument is _required_: the name of the directory to change to.

<pre><code data-trim contenteditable>
$ cd Desktop
$ pwd
/Users/joe/Desktop
</code></pre>
</section>

<section markdown="block">
## A Reminder About Special Paths

* . (dot) is current directory
* .. (dot dot) is parent directory
* ../.. (dot dot slash dot dot) is parent of parent directory
* / (slash) is root directory
* ~ (tilde) is home directory

</section>

<section markdown="block">
## Using Special Paths 

Let's use special paths with cd &rarr;

<pre><code data-trim contenteditable>
$ pwd
/Users/joe
$ cd ../
$ pwd
/Users
$ ls
Shared	joe
$ cd ~
$ pwd
/Users/joe
$ cd /
$ pwd
/
</code></pre>
</section>

<section markdown="block">
## Back to Directory 

__Pass - (dash) as an argument to cd to go back to the directory you just changed from. &rarr;__

<pre><code data-trim contenteditable>
$ pwd
/Users/joe
$ cd /tmp
$ pwd
/tmp
$ cd -
/Users/joe
</code></pre>
</section>

<section markdown="block">
## rmdir

__Removes a directory with the name of the argument supplied. &rarr;__

Think: _remove directory_

One argument is _required_: the name of the directory to remove.

<pre><code data-trim contenteditable>
$ mkdir foo
$ ls
foo
$ rmdir foo
$ ls

</code></pre>
</section>

<section markdown="block">
## pushd/popd

__Change to directory, but save current one for later. &rarr;__

* pushd requires one argument, the directory to change to.
* you can pushd multiple directories
* popd takes you back to the last saved directory
* you can continue to use popd until there are no more saved directories

</section>

<section markdown="block">
## pushd/popd Continued

<pre><code data-trim contenteditable>
$ pwd
/Volumes
$ pushd ~/Desktop/
~/Desktop /Volumes
$ pushd /Applications/
/Applications ~/Desktop /Volumes
$ popd
~/Desktop /Volumes
$ pwd
/Users/joe/Desktop
$ popd
/Volumes
</code></pre>

</section>

<section markdown="block">
## Permissions

<pre><code data-trim contenteditable>
chmod 755 foo.html
</code></pre>

<pre><code data-trim contenteditable>
chmod u+r foo.html
</code></pre>

</section>