# text-metta-sutta

## Overview

This is a typesetting project I made to learn LaTeX and to provide a small single-section text block for a bookbinding project.

The text contains the 10 verses of the Karaṇīyamettā Sutta written in both
its original Pāli (using Devanagari script) and English.

![metta-sutta](https://user-images.githubusercontent.com/110567463/222981433-c8f9e6d1-b1cb-4951-a8b7-76287756869c.png)

## What's Included

- `metta-sutta.tex`: The LaTeX code that contains the book's text, layout,
   and formatting
- `metta-sutta.pdf`: The rendered, non-imposed content of the book
- `book.tex`: The LaTeX code that imposes the pages of `metta-sutta.pdf` into a 3 sheet signature
- `book.pdf`: The rendered, imposed content of the book. It is laid out for US Letter paper and is intended to be printed double-sided.

## Build Requirements

The completed PDF (`book.pdf`) is included in this repository, but if you would like to rebuild it you will need to configure a LaTeX environment on your computer. Instructions can be found online for your particular operating system.

This project requires the XeLaTeX engine. Additionally, you may (or may not)
need to install these additional packages using `tlmgr`:
- [latexmk](https://ctan.org/pkg/latexmk)
- [relsize](https://ctan.org/pkg/relsize)
- [changepage](https://ctan.org/pkg/changepage)


On my system, I was able to setup the build requirements with the following commands:
```
brew install basictex
sudo tlmgr install latexmk
sudo tlmgr install relsize
sudo tlmgr install changepage
```

You will also need to install the following two fonts on your system:
- [EB Garamond](https://fonts.google.com/specimen/EB+Garamond)
- [Noto Sans Devanagari](https://fontmeme.com/fonts/noto-sans-devanagari-font/)

## Building

First, generate the content:
```
latexmk -xelatex metta-sutta.tex
```

Next, generate the signature:
```
latexmk -xelatex book.tex
```

Finally, clean up temporary files:
```
latexmk -c
```

