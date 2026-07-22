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

The sheer amount of snippets contained within latex.hsnips can be overwhelming at first. Let's break down what each part of the snippets mean.

``snippet `(?<!\\)part` "d/dx" iAm
\frac{\partial ${1:V}}{\partial ${2:x}}$0
endsnippet``

- ``snippet`` delineates the start of a snippet.
- The word that immediately follows (in this case, `(?<!\\)part`), is a regular expression (regex) for what you must type in order to trigger the snippet. In this case, it dictates that you must type ``part`` _without_ preceding it with a backslash.
- The following word in quotes ("d/dx") is just what you decide to name the snippet and has no impact on functionality whatsoever.
- ``iAm`` refers to the CONTEXT in which the snippet must be called in order for it to trigger. In this case, it must be called within an equation-type environment. Calling it outside of this environment will not do anything. You can also specify ``wA`` for the snippet to trigger in a text-type environment.
- The next line specifies what the snippet expands out to. In this case, it becomes a partial fraction. Immediately after expansion is triggered, your cursor will land on the first ${} section. You can change the contents of this section but you don't have to. Pressing tab will then transport your cursor to the next ${} section. Again, you can choose to change the contents if you'd like. Pressing tab again will bring you to the position indicated by $0. 

## A Note on Vim:
Vim is a text editing software that makes your life better, but it takes some getting used to. If you look up the user guide and decide you hate it, feel free to toggle it off using Vim: Toggle Vim Mode from the command palette. All other facets of this build will still work as normal. However, if you decide that you would like to learn how to use it, https://www.vim-hero.com/ is a great resource for instruction and practice.
