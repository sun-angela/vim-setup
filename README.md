# vim-setup
Writing fast LaTeX documents using Vim and Snippets.

## Introduction

This repository is mainly a place for me (Angela) to store instructions for my personal VS-Code/Vim setup so that I don't forget if I ever need to rebuild it. Disclaimer: I am not a programmer by trade. None of this work is my own. I am purely and directly using the work of OrangeX4 (https://github.com/OrangeX4), whose code originates from the genius Gilles Castel (https://github.com/gillescastel/).

## Setup
1. Download VS Code
2. From VS Code, download the extensions for VSCodeVim and PDF Viewer by Mathematic Inc.
3. Open Preferences: Open User Settings from the command palette (command-shift-p). This will open up your settings.json file
4. Delete all content in the settings.json file and copy-paste the raw json code from settings.json in this repository
5. Open the command palette again (command-shift-p) and open HyperSnips: Open Snippets Directory. This will open a folder on your computer
6. Download and transfer the latex.hsnips file from this repository into the folder
7. Restart VS Code
8. VIOLA! You can now build LaTeX documents on save or by pressing Space+l+b, open the corresponding PDF of the active LaTeX file using Space+l+v, navigate and manipulate .tex files with Vim, and most importantly, use snippets

# A Note on Vim:
Vim is a text editing software that makes your life better, but it takes some getting used to. If you look up the user guide and decide you hate it, feel free to toggle it off using Vim: Toggle Vim Mode from the command palette. All other facets of this build will still work as normal. However, if you decide that you would like to learn how to use it, https://www.vim-hero.com/ is a great resource for instruction and practice.
