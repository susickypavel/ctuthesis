# ctuthesis

This repository is a fork of https://github.com/tohecz/ctuthesis. Most of the original files are present, but the folder structure is cleaner to work with. It's designed to work well with Visual Studio Code and a LaTeX workshop extension.

# 1. Installation

## 1.1 Prerequisites

- [**Visual Studio Code**](https://code.visualstudio.com)
- [**VSCode LaTeX workshop extension**](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- [**TexLive**](https://tug.org/texlive)

> [!NOTE]
> MacOS users: Make sure you have `latexindent` installed on your machine. Otherwise, LaTeX workshop may have trouble formatting your sources.

### 1.1.1 Required LaTeX packages

Most of the required packages are included in the full distribution of TexLive. If you're an advanced user with custom Tex distribution (such as TinyTex), below are some of the packages that you might be missing. You can copy the command to install all of them with the `tlmgr` package manager below.

- [**biblatex**](https://bibtex.eu/cs/biblatex/)
- [**csquotes**](https://ctan.org/pkg/csquotes)
- [**environ**](https://www.ctan.org/pkg/environ)
- [**microtype**](https://www.ctan.org/pkg/microtype)
- [**pdfpages**](https://www.ctan.org/pkg/pdfpages)
- [**titlesec**](https://www.ctan.org/pkg/titlesec)
- [**fancyhdr**](https://www.ctan.org/pkg/fancyhdr)
- [**caption**](https://www.ctan.org/pkg/caption)
- [**pdflscape**](https://www.ctan.org/pkg/pdfscape)
- [**biber**](https://www.ctan.org/pkg/biber)
- [**makeindex**](https://www.ctan.org/pkg/makeindex)
- [**babel-czech**](https://www.ctan.org/pkg/babel-czech)
- [**babel-english**](https://www.ctan.org/pkg/babel-english)
- hyphen-czech

```sh
tlmgr install biblatex csquotes environ microtype pdfpages titlesec fancyhdr caption pdflscape biber makeindex babel-czech babel-english hyphen-czech
```

### 1.1.2 Optional LaTeX packages

These packages aren't needed for the compilation of the project to work. However, they can enhance your experience with linting and formatting your LaTeX code.

- [chktex](https://www.ctan.org/pkg/chktex)
- [latexindent](https://www.ctan.org/pkg/latexindent)

```sh
tlmgr install chktex latexindent
```

## 1.2 Usage

1. Make sure you have all the [**prerequisites**](#11-prerequisites)
2. Open the [**workspace file**](./.vscode/thesis.code-workspace) using Visual Studio Code
3. Open `thesis.tex` (your root file, this should include all the other `*.tex` files)
4. Make your changes and hit save
5. `.build` folder should be generated in the root of the workspace with bunch of intermediate files and a final [**pdf**](./.build/thesis.pdf).
6. Check out the original [**manual**](./manual.pdf) if you want to customize the thesis to your liking
7. Have fun writing your awesome thesis!

### 1.2.1 TODOs

To make your life a little bit easier, there are several `TODO` comments placed across the `*.tex` files to let you know that you should change their content before submitting your work.

# 2. Structure

```ini
✨ ctuthesis/ # Workspace root
├─ .build/ # Build directory (not in VCS)
│  ├─ thesis.pdf
├─ src/ # Source directory
│  ├─ assets/ # Asset directory, mainly CTU logo and font
│  │  ├─ ctu_logo_black.pdf
│  ├─ common/ # (almost) original ctuthesis *.tex files
│  │  ├─ ctuth-core.tex
│  │  ├─ ctuth-names.tex
│  │  ├─ ctuth-templates.tex
│  │  ├─ ctuth-pkg.tex
│  ├─ documents/ # Directory for all sorts of documents
│  │  ├─ zadani.pdf # Specification of your thesis
│  ├─ ctuthesis.cls # LaTeX class file that makes all the magic, don't worry about it too much.
│  ├─ thesis.ist # Formatting configuration for Index of the document
│  ├─ thesis.bib # Bibliography references
│  ├─ thesis.tex # Entry tex file for your thesis
├─ manual.pdf # Original ctuthesis manual
```
