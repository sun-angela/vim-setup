# vim-setup
Writing fast LaTeX documents using Vim and Snippets.

## Introduction

This repository is mainly a place for me (Angela) to store instructions for my personal VS-Code/Vim setup so that I don't forget if I ever need to rebuild it. Disclaimer: I am not a programmer by trade. None of this work is my own. I am purely and directly using the work of OrangeX4 (https://github.com/OrangeX4), whose code originates from the genius Gilles Castel (https://github.com/gillescastel/).

## Setup
1. Download VS Code
2. From VS Code, download the extensions for VSCodeVim, Tabout, and PDF Viewer by Mathematic Inc. using the Extensions tab on the left (the icon looks like a Windows logo that's a little drunk)
3. Open **Preferences: Open User Settings** from the command palette (command-shift-p). This will open up your settings.json file
4. Copy the contents in the **settings.json** file elsewhere so that you can easily restore the file if you decide you hate this setup
5. Delete all content in the **settings.json** file and copy-paste the raw json code from **settings.json** in this repository
6. Open **Preferences: Open Keyboard Shortcuts** from the command palette. This will open up your **keybindings.json** file
7. Copy the contents in the **keybindings.json** file elsewhere so that you can easily restore the file if you decide you hate this setup
8. Delete all content in the **keybindings.json** file and copy-paste the raw json code from **keybindings.json** in this repository
9. Open the command palette again (command-shift-p) and open **HyperSnips: Open Snippets Directory**. This will open a folder on your computer
10. Download and transfer the **latex.hsnips** file from this repository into the folder. You can always delete this file later if you decide you hate this setup
11. Restart VS Code
12. VIOLA! You can now build LaTeX documents on save or by pressing Space+l+b, tab out of bracket/quote delimeters, open the corresponding PDF of the active LaTeX file using Space+l+v, navigate and manipulate .tex files with Vim, and most importantly, use snippets

## How to Navigate Snippets

The sheer amount of snippets contained within latex.hsnips can be overwhelming at first. Let's break down what each part of the snippets means.

``snippet `(?<!\\)part` "d/dx" iAm``

``\frac{\partial ${1:V}}{\partial ${2:x}}$0``

``endsnippet``

- ``snippet`` delineates the start of a snippet.
- The expression that immediately follows (in this case, `(?<!\\)part`), is a regular expression (regex) for what you must type in order to trigger the snippet. In this case, it dictates that you must type ``part`` _without_ preceding it with a backslash
- The following word in quotes ("d/dx") is just what you decide to name the snippet and has no impact on functionality whatsoever
- ``iAm`` refers to the CONTEXT in which the snippet must be called in order for it to trigger. In this case, it must be called within an equation-type environment. Calling it outside of this environment will not do anything. You can also specify ``wA`` for the snippet to trigger in a text-type environment
- The next line specifies what the snippet expands out to. In this case, it becomes a partial fraction. Immediately after expansion is triggered, your cursor will land on the first ${1:} section. You can change the contents of this section (AKA change V to something else), but you don't have to. Pressing tab will then transport your cursor to the next ${2:} section. Again, you can choose to change the contents if you'd like. Pressing tab again will bring you to the position indicated by $0.
- ``endsnippet`` delineates the end of the snippet

To find an existing snippet, the easiest way I've found to do this is to search the document (command-f) for the LaTeX code you're looking for. If that doesn't work, input the file into an AI model and ask it to find it for you. If the functionality you're looking for is not in the file, you can add your own snippet to the file by following the template above. 

### Here's a short guide to some snippets you may find useful, though this list is in no way close to comprehensive

(In text environment)
- ``lm`` -> ``$ $``
- ``eqs`` -> ``\begin{equation*} \end{equation*}``

(In math/equation environment)
- ``//`` -> ``\frac{}{}``
- ``1/2`` -> ``\frac{1}{2}``, works for any numbers
- ``sr`` -> ``^{2}``
- ``hsq`` -> ``\sqrt{}``
- ``pow`` -> ``^{}``
- ``td`` -> ``_{}``
- ``axx`` -> ``a_x``, works for any letters or numbers
-  ``sum`` -> ``\sum_{i = 1}^{n}``
-  ``dint`` -> ``$\int_{-\infty}^{\infty}  \mathrm{d}x$``
-  ``ali`` -> ``\begin{align} \end{align}``
-  ``ae`` -> ``&=``
-  ``nl`` -> new line, so `` \\``
-  ``RR``, ``NN``, ``ZZ`` -> ``\mathbb{R}``, ``mathbb{N}``, ``mathbb{Z}``
-  ``oo`` -> ``\infty``
-  ``cases`` -> ``\begin{cases} , &  \\ , &  \end{cases}``
-  ``iff`` -> ``\iff``
-  ``=>`` -> ``\implies``
-  ``%)`` -> ``\left(  \right)``, works with any bracket type, like ),],|
-  ``inn`` -> ``\in``
-  ``norm`` -> ``\left\|  \right\|``
-  ``set`` -> ``\{ \}``

There are also some useful "snippets" I use that are vestiges of an old system dependent on **keybindings.json** rather than **latex.hsnips**. Namely, if you type ``template`` and hit enter, you'll get my default homework template. If you type ``problem`` and hit enter, you'll get the template for a new problem solution. You can change the formatting of these templates through **keybindings.json** (not **latex.hsnips**). 

## A Note on Vim:
Vim is a text editing software that makes your life better, but it takes some getting used to. If you look up the user guide and decide you hate it, feel free to toggle it off using Vim: Toggle Vim Mode from the command palette, or, if you want to stop it from triggering on startup, disable or uninstall the extension entirely. All other facets of this build will still work as normal, except for the Space+l+v and Space+l+b stuff. However, if you decide that you would like to learn how to use it, https://www.vim-hero.com/ is a great resource for instruction and practice.
