# *TeX et al.*

A (mainly paraphrased and extensive but not necessarily comprehensive) guide for and an overview of TeX, LaTeX, and the extended TeX family.

## What is TeX?

**TeX** (derived from the Ancient Greek word τέχνη or technē ("skill", "art", "technique"); pronounced `/tɛx/` or `/tɛk/`) is a typesetting system and computer program, designed and written by [Donald E. Knuth](https://en.wikipedia.org/wiki/Donald_Knuth), that is primarily used for creating beautifully typeset mathematical content and producing high-quality documents. TeX, which is free and open-source, was first released in 1978 and uses the Turing-complete TeX markup language with primitive commands that are processed and compiled using the original TeX engine (compiler). All TeX files have the filename extension `.tex` and outputs a DVI ("DeVice Independent") file with the filename extension `.dvi`.

## What are TeX macros?

A **TeX macro** is command defined using the low-level primitive commands (the "building blocks") of the TeX markup language and/or other macros, and TeX macros are essentially shorthands that can make the source code of TeX documents both easier to read and write. Users can define their own macros which makes TeX a highly customizable typesetting system. TeX macro names are conventionally built from a `\` (backslash) followed by a sequence of letters, which may be upper or lower case but they may also be `<any-single-special-character>`, which allows all sorts of oddities.

## What is LaTeX?

**LaTeX** ([possibly derived from **La**mport + **TeX**](https://tex.stackexchange.com/a/64146); pronounced `/ˈlɑːtɛx/` or `/ˈleɪtɛx/`) is a document preparation system, originally written and developed by [Leslie Lamport](https://en.wikipedia.org/wiki/Leslie_Lamport) in 1984, which consists of a collection of TeX macros and is a program built on top of TeX to process documents which include complex mathematical expressions and multilingual typesetting. The idea behind LaTeX is to shift the focus from the format to the content of your document ([separation of content and presentation](https://en.wikipedia.org/wiki/Separation_of_content_and_presentation)). LaTeX is widely used in academia because it includes features designed for the production of technical and scientific documentation, and is the de facto standard for the communication and publication of scientific documents. LaTeX is a free and open-source software licensed under [the LaTeX Project Public License (LPPL)](https://en.wikipedia.org/wiki/LaTeX_Project_Public_License).

## What are TeX engines?

A **TeX engine** is the actual program that is used to run TeX to typeset and compile documents. TeX engines are the executable binaries which implement different TeX variants. [There are currently **seven [TeX] engines** (binaries) in common use which can process TeX input, although not all are used to the same extent](https://tex.stackexchange.com/a/13601):

1. Knuth's original **`TeX`**, which is the definitive TeX but is rarely used as the standard engine in modern TeX distributions (see [the TeX distribution section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-are-tex-distributions)).
2. **`e-TeX`** (also written as **`ε-tex`**), which adds a number of additional primitives to `TeX` and bidirectional typesetting extension called `TeX--XeT`.
3. **`pdfTeX`**, which implements direct PDF output (but can produce DVI) and adds a number of (mainly) PDF-related primitives.
4. **`XeTeX`**, which does the above and supports UTF-8 encoded Unicode natively, OpenType and TrueType fonts, and access to system fonts.
5. **`LuaTeX`**, which does all the above and provides access to many internals via the embedded Lua programming language.
6. **`pTeX`**, which adds a number of primitives to support vertical typesetting using "traditional" Japanese encodings.
7. **`upTeX`**, which is similar to `pTeX` but allows for Unicode input (with a number of provisos) and also adds some additional primitives.

To clear up a common confusion, LaTeX is ***not*** a TeX engine but a collection of TeX macros, and different versions of LaTeX correspond to different *LaTeX TeX formats*.
 
 ## What are TeX Formats/TeX Macro Packages?
 
A **TeX format** (or **TeX macro package**) is a collection of macros that make the TeX primitives usable for typesetting purposes by humans. TeX formats are the TeX-based languages in which one actually writes documents. Examples of TeX formats:

### Non-LaTeX TeX Formats
  1. **`Plain TeX`**, a set of macros created by Donald Knuth to typeset his books, including the TeXbook.

  2. **`AMS-TeX`**, a now-obsolete TeX format originally written by Michael Spivak for the American Mathematical Society (AMS) during 1983–1985.

  3. **`ConTeXt`** (see [the `ConTeXt` section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-context))

### LaTeX TeX Formats

  1. **`LaTeX2.09`**, Leslie Lamport's last version of LaTeX which was last updated in 1992. 

  2. **`LaTeX2e`** (also written as **`LaTeX2ε`**), the most commonly used TeX format and the current version of LaTeX, replacing `LaTeX2.09` in 1994, which is actively being maintained and developed by [The LaTeX Project team](https://www.latex-project.org/about/team).

  3. **`LaTeX3`**, a LaTeX version in development since the early 1990s which was initially planned to replace `LaTeX2e` the same way `LaTeX2e` replaced `LaTeX2.09` but whose features are instead currently being gradually incorporated in newer versions of `LaTeX2e` since 2020.

## What does it mean when someone says they're using `LaTeX` or `pdfLaTeX` or `XeLaTeX` or `LuaLaTeX`?

- **"Using `LaTeX`"** is a phrase often used as a shorthand for contexts where one uses a version of LaTeX (presumably `LaTeX2e`) as the TeX format to write TeX files (with the `.tex` filename extension) whose (PDF or DVI) outputs are compiled using any TeX engine (with the caveat that the original `TeX` engine only supports DVI outputs).

- **"Using `pdfLaTeX`"** is a phrase often used as a shorthand for contexts where one uses a version of LaTeX (presumably `LaTeX2e`) as the TeX format to write TeX files (with the `.tex` filename extension) whose (PDF or DVI) outputs are compiled using `pdfTeX` as the TeX engine.

- **"Using `XeLaTeX`"** is a phrase often used as a shorthand for contexts where one uses a version of LaTeX (presumably `LaTeX2e`) as the TeX format to write TeX files (with the `.tex` filename extension) whose (PDF or DVI) outputs are compiled using `XeTeX` as the TeX engine.

- **"Using `LuaLaTeX`"** is a phrase often used a shorthand for contexts where one uses a version of LaTeX (presumably `LaTeX2e`) as the TeX format to write TeX files (with the `.tex` filename extension) files whose (PDF or DVI) outputs are compiled using `LuaTeX` as the TeX engine.

Also, see [this answer to TeX.SX's "Questions regarding the distinction between XeTeX and XeLaTeX and how they relate to TeX and LaTeX?"](https://tex.stackexchange.com/a/296623)

## What is ConTeXt?

[**`ConTeXt`**](https://wiki.contextgarden.net/) is a TeX-derived document processor, created by Hans Hagen and Ton Otten around 1991, which intends for users to provide users with typographic control more easily and more directly and this makes `ConTeXt` differ from LaTeX whose original aim is for users to focus more on the content rather than the presentation although the current LaTeX Project has evolved from this vision (see `ltx3info.pdf` linked in the [resources section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#2-the-latex-project)).  `ConTeXt` is a TeX format distinct from other formats because it uses a separate program (`context`) which then runs a TeX engine. This makes it possible to support a wide array of advanced features, such as integrated graphics and XML input, since the control program can determine the flow of processing. For more information, read [Berend de Boer's *LaTeX in proper ConTeXt* (2003)](https://www.berenddeboer.net/tex/LaTeX2ConTeXt.pdf).

## What is LyX?

[**`LyX`**](https://www.lyx.org/) is a LaTeX-derived GUI document processor that encourages an approach to writing based on the structure of documents ([WYSIWYM](https://en.wikipedia.org/wiki/WYSIWYM)) and not simply their appearance ([WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG)). LyX uses LaTeX as its backend typesetting mechanism but presents the user with the familiar face of a WYSIWYG word processor. For more information, read the [Lyx Wiki](https://wiki.lyx.org/).

## What are LaTeX macro packages?

A **LaTeX macro package** (or simply LaTeX package) is a collection of macros (based on TeX macros defined in a particular LaTeX TeX format, presumably `LaTeX2e`) that are loaded (imported as addons) to add functionality and help users write or improve the typesetting of their LaTeX documents for specific contexts and use-cases. All LaTeX packages have the filename extension `.sty` (as they were referred to as *styles* in LaTeX versions prior to `LaTeX2e`). The standard and proper way to install TeX engines, TeX formats, and LaTeX packages is by installing what's called a *TeX distribution*.

## What are TeX distributions?

A **TeX Distribution** provides a structured collection of TeX-related software, files, and macros, including the previously mentioned *packages* for LaTeX and what are called *modules* for ConTeXt, and uses a package manager to handle package dependencies. Some TeX distributions install everything you'll ever need right away (e.g., **TeX Live**) including fonts and documentations while others allows for more minimal installations which support installing packages on-the-go (e.g., **MikTeX**, see [*Just enough TeX*](https://miktex.org/kb/just-enough-tex)). For ConTeXt specifically, it is recommended to install a ConTeXt distribution from [their official website](https://wiki.contextgarden.net/Installation) instead because it is more up-to-date.

There are three mainly used TeX distributions:

### 1. TeX Live (cross-platform)
   - [Installation on Windows](https://tug.org/texlive/windows.html)
   - [Installation on Unix/GNU/Linux](https://tug.org/texlive/quickinstall.html)
   - [Installation on macOS](https://tug.org/mactex/mactex-unix-download.html)

### 2. MikTeX (available on Windows, macOS, and certain Linux distributions)
   - [Installation](https://miktex.org/download)

### 3. MacTeX (cross-platform redistribution of TeX Live which includes Mac-specific utilities and front-ends)
   - [Installation](https://tug.org/mactex)

After installing a TeX distribution, it is recommended for you to install a *TeX editor* to help you write TeX and LaTeX documents.

## What are TeX editors?

A **TeX editor** is a text editor or IDE that is suitable for writing TeX documents. You can simply write the source code of your TeX documents in something like `notepad` if you so wish of course, but specialized editors simply offer additional features such as syntax highlighting, spell checking, etc. Please do note that an editor alone can not convert a TeX file into a PDF, DVI, or any other output format, but requires programs, mainly a TeX engine, that are included in any TeX distribution.

### Local TeX Editors (Requires installing a TeX distribution)
  - [Visual Studio Code](https://code.visualstudio.com/Download) + [LaTeX Workshop extension](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install) (free, cross-platform)
  - [Emacs](https://www.gnu.org/software/emacs/download.html) + [AucTeX](https://www.gnu.org/software/auctex) (free, cross-platform)
  - [Vim](https://www.vim.org/download.php) or [Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim) + [`latex-suite`/`vim-latex`](https://vim-latex.sourceforge.net/index.php?subject=download&title=Download) (free, cross-platform)
  - [TeXstudio](https://www.texstudio.org/#download) (free, cross-platform)
  - [Texifier (formerly Texpad)](https://texpadapp.com/) (paid with a free trial version, only available on macOS, iOS, and iPadOS with a future release for Windows)
  - For more local TeX editor recommendations, see [TeX.SX's "LaTeX Editors/IDEs"](https://tex.stackexchange.com/q/339)

### Cloud-based TeX Editors (Works without installing a TeX distribution)
  - [Overleaf](https://www.overleaf.com/) (paid, free version allows unlimited documents with only one collaborator, requires registration, uses up-to-date TeX Live)
  - [Cocalc](https://cocalc.com/) (paid, free version allows unlimited documents with unlimited collaborators, requires registration)
  - [Papeeria](https://papeeria.com/) (paid, free version allows unlimited documents with unlimited collaborators, requires registration except for [demo](https://papeeria.com/auth/demo), uses TeX Live 2019)
  - [ConTeXt Live](https://live.contextgarden.net/) (free, no registration required)
  - [TeX Viewer](https://texviewer.herokuapp.com/) (free, no registration required, limited features)
  - [Authorea](https://www.authorea.com/) (paid, free version allows only 10 documents with limited sharing, requires registration)

## Why should I use LaTeX?

If you've read this far, I would assume you're at least somewhat interested in using LaTeX. For more details about the advantages and disadvantages of LaTeX over other alternatives, read the following:

1. [*The Beauty of LaTeX* - Dario Taraborelli](https://nitens.org/w/latex)
2. [TeX.SX's "What is TeX used for?"](https://tex.stackexchange.com/q/5893)
3. [TeX.SX's "What professions use TeX/LaTeX besides CS?"](https://tex.stackexchange.com/q/940)
4. [TeX.SX's "Why should I use LaTeX?"](https://tex.stackexchange.com/q/1756)
5. [TeX.SX's "LaTeX vs Word; improvements of LaTeX over the years"](https://tex.stackexchange.com/q/218567)
6. [TeX.SX's "Showcase of beautiful typography done in TeX & friends"](https://tex.stackexchange.com/q/1319)
7. [TeX.SX's "Showcase TeX Typography for TUG's Calendar"](https://tex.stackexchange.com/q/134638)
8. [TeX.SX's "Examples of simple beautiful PhD theses"](https://tex.stackexchange.com/q/164331)
9. [TeX.SX's "Nice scientific pictures show off"](https://tex.stackexchange.com/q/158668)
10. [TeX.SX's "How can I convert my TeX-illiterate coworkers to LaTeX?"](https://tex.stackexchange.com/q/102878)
11. [TeX.SX's "What are the benefits of writing resumes in TeX/LaTeX?"](https://tex.stackexchange.com/q/11955)
12. [TeX.SX's "Why is LaTeX so complicated?"](https://tex.stackexchange.com/q/222500)

If you're not interested in using LaTeX or if you're simply looking for alternatives, see [the alternatives section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-are-some-alternatives-to-tex-latex-etc).

## How do I install LaTeX on Windows and use Visual Studio Code with the LaTeX Workshop extension as my TeX editor?

See [`LaTeX-VS-Code-Installation-Guide`](https://github.com/amanuensisfrances/LaTeX-VS-Code-Installation-Guide).

## What is the structure of a LaTeX document?
A LaTeX document (with the `.tex` filename extension) generally has the following structure (assuming it is the main file, typically named `main.tex`, and not the sub-files).

```
%!TEX program = <pdflatex/xelatex/pdflatex>
% the comment above is a "magic comment"
% for more information about magic comments, read TeX.SX questions tagged with [magic-comment]: https://tex.stackexchange.com/questions/tagged/magic-comment?tab=Votes

\documentclass[<options>]{<document-class>}

% <preamble>
% the preamble is every piece of LaTeX code written after "\documentclass{<document-class>}" and before "\begin{document}"
% the preamble normally contains commands that affect the entire document
% LaTeX packages are loaded with the macro "\usepackage{<package-name>}" and can only be loaded in the preamble

\begin{document}
    % <text>
    % any pair of macros "\begin{<name>}" and "\end{<name>}" is called "LaTeX environment"
    % every text inside a document environment (written after "\begin{document}" and before "\end{document}") will be typeset
\end{document}
```
Note that we can write comments in any (La)TeX document using `%` (a percent sign). For more information, see [the LaTeX/Document Structure article on Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Document_Structure).

## What are LaTeX document classes?

A **LaTeX document class** (or simply "LaTeX class") is a file (with the `.cls` filename extension) containing the general layout of a LaTeX document. As seen from the previous section about the structure of LaTeX documents, document classes are loaded with the `\documentclass{<document-class>}` macro. Examples of LaTeX document classes:

### Standard Document Classes
  1. **`book`** (has `\chapter`, has `\frontmatter`, `\mainmatter`, and `\backmatter`, *doesn't* have the `abstract` environment, starts a new page for `\part`'s heading) 
  2. **`report`** (has `\chapter`, *doesn't* have `\frontmatter`, `\mainmatter`, `\backmatter`, has the `abstract` environment, starts a new page for `\part`'s heading)
  3. **`article`** (*doesn't* have `\chapter`, *doesn't* have `\frontmatter`, `\mainmatter`, `\backmatter`, has the `abstract` environment, *doesn't* start a new page for `\part`'s heading)
  4. **`letter`** (for writing letters)

### `KOMA-Script` Document Classes (see the [`KOMA-Script` section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-koma-script))

### AMS Document Classes (see [`amscls-doc`](https://ctan.org/pkg/amscls-doc) for the user documentation)
  1. **`amsbook`** (for books)
  2. **`amsart`** (for writing articles for the AMS)
  3. **`amsproc`** (for proceedings)

### Miscellaneous Document Classes
  1. **`memoir`** (see [the `memoir` section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-the-memoir-class))
  2. **`beamer`** (see [the `beamer` section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-the-beamer-class))
  3. **`standalone`** (see [the `standalone` section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-the-standalone-class-and-package))

For more information, see [TeX.SX's "What are the available 'documentclass' types and their uses?"](https://tex.stackexchange.com/q/782).

## What is `KOMA-Script`?

[**`KOMA-Script`**](https://ctan.org/pkg/koma-script) ([possibly derived from Ko(hm) + Ma(rkus) + `script`](https://tex.stackexchange.com/a/229071)) is a bundle of many versatile LaTeX document classes and packages, originally written and currently developed and maintained by Markus Kohm, released in 1994 as a successor to the [`script`](https://ctan.org/pkg/script) document *style* (a term used before `LaTeX2e` when there was no distinction between classes and packages), written by Frank Neukam. Initially primarily intended to provide good LaTeX classes for German-language authors, `KOMA-Script` currently aims to provide more-flexible alternatives to the standard classes. The capabilities of `KOMA-Script` can surpass those of the standard classes and some of them should be considered extensions to the basic capabilities of the LaTeX kernel. 

### `KOMA-Script` Document Classes

  1. **`scrbook`** (`KOMA-Script` analogue to the standard `book` class) [[`KOMA-Script` Documentation, Chapter 3]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.3)
  2. **`scrreprt`** (`KOMA-Script` analogue to the standard `report` class) [[`KOMA-Script` Documentation, Chapter 3]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.3)
  3. **`scrartcl`** (`KOMA-Script` analogue to the standard `article` class) [[`KOMA-Script` Documentation, Chapter 3]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.3)
  4. **`scrlttr2`** (`KOMA-Script` analogue to the standard `letter` class) [[`KOMA-Script` Documentation, Chapter 4]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.4) [[`KOMA-Script` Documentation, Chapter 22]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.22) [[`KOMA-Script` Documentation, Appendix A]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#appendix.A)

### `KOMA-Script` Packages

`KOMA-Script`'s packages (which are integrated in any `KOMA-Script` class, but are also usable in other classes) include: 

1. [**`typearea`**](https://ctan.org/pkg/typearea) (for providing type area calculation and should *not* be directly loaded in a `KOMA-Script` class) [(`KOMA-Script` Documentation, Chapter 2)](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.2) [[`KOMA-Script` Documentation, Chapter 20]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.20)

2. [**`scrletter`**](https://ctan.org/pkg/scrletter) (for providing letter-based functionality of `scrlttr2` to other classes) [[`KOMA-Script` Documentation, Chapter 4]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.4) [[`KOMA-Script` Documentation, Chapter 22]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.22) [[`KOMA-Script` Documentation, Appendix A]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#appendix.A)

3. [**`scrlayer-scrpage`**](https://ctan.org/pkg/scrlayer-scrpage) (for page styles and is *not* loaded by default in a `KOMA-Script` class, replaces the now-obsolete [`scrpage2`](https://ctan.org/pkg/scrpage2)) [[`KOMA-Script` Documentation, Chapter 5]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.5) [[`KOMA-Script` Documentation, Chapter 18]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.18)

4. [**`scrdate`**](https://ctan.org/pkg/scrdate) (for providing calendar date operations) [[`KOMA-Script` Documentation, Chapter 6]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.6)

5. [**`scrtime`**](https://ctan.org/pkg/scrtime) (for providing time information of the current LaTeX run) [[`KOMA-Script` Documentation, Chapter 7]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.7)

6. [**`scraddr`**](https://ctan.org/pkg/scraddr) (for providing data from `scrlttr2`'s address files) [[`KOMA-Script` Documentation, Chapter 8]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.8)

7. [**`scrextend`**](https://ctan.org/pkg/scrextend) (for providing basic features of `KOMA-Script` classes in other classes and should *not* be used in a `KOMA-Script` class) [[`KOMA-Script` Documentation, Chapter 9]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.9) [[`KOMA-Script` Documentation, Chapter 21]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.21)

8. [**`scrjura`**](https://ctan.org/pkg/scrjura) (for providing environments suitable for writing contracts, laws, acts or other legal purposes) [[`KOMA-Script` Documentation, Chapter 10]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.10)

9. **`scrlogo`** (for providing the `\KOMAScript` macro which outputs the word mark `KOMA-Script` in a sans serif font and with slight letter spacing of the part set in uppercase) [[`KOMA-Script` Documentation, Chapter 11]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.11)

10. [**`scrbase`**](https://ctan.org/pkg/scrbase) (for providing basic features of `KOMA-Script`) [[`KOMA-Script` Documentation, Chapter 12]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.12)

11. [**`scrlfile`**](https://ctan.org/pkg/scrlfile) (for providing control of package dependencies) [[`KOMA-Script` Documentation, Chapter 13]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.13)

12. [**`scrwfile`**](https://ctan.org/pkg/scrwfile) (for providing a means of sending all LaTeX `\newrite`, table of contents, and other miscellaneous output via the LaTeX `.aux` file) [[`KOMA-Script` Documentation, Chapter 14]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.14)

13. [**`tocbasic`**](https://ctan.org/pkg/tocbasic) (for providing management of tables/lists of contents, replaces the now-obsolete [`tocstyle`](https://ctan.org/pkg/tocstyle)) [[`KOMA-Script` Documentation, Chapter 15]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.15)

14. **`scrhack`** (for improving third-party packages) [[`KOMA-Script` Documentation, Chapter 16]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.16)

15. [**`scrlayer`**](https://ctan.org/pkg/scrlayer) [[`KOMA-Script` Documentation, Chapter 17]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.17)

16. [**`scrlayer-notecolumn`**](https://ctan.org/pkg/scrlayer-notecolumn) [[`KOMA-Script` Documentation, Chapter 19]](https://mirrors.ctan.org/macros/latex/contrib/koma-script/doc/scrguide-en.pdf#chapter.19)

For more information, see [TeX.SX's "Most useful additions in KOMA-Script?"](https://tex.stackexchange.com/q/1351), [TeX.SX's "Why should I \*not\* use the KOMA-Script classes?"](https://tex.stackexchange.com/q/73141), and [TeX.SX's "Using KOMA-Script packages with other classes"](https://tex.stackexchange.com/q/165230).

## What is the `memoir` class?

[**`memoir`**](https://ctan.org/pkg/memoir) is a LaTeX document class, originally written by Peter Wilson and currently developed and maintained by Lars Madsen, suitable as an alternative to the standard `book` and `report` classes. The built-in package functions of `memoir` are mainly related to document design and layout; `memoir` does not touch upon areas like those that are covered by the `babel` (for multilingual typesetting) or `hyperref` (for hyperlinks and cross-references) packages or any package related to mathematical typesetting. Compared to `KOMA-Script` classes (e.g., `scrbook` or `scrreprt`) which only incorporate a handful of features but execute them well, `memoir` has many built-in features based on multiple different LaTeX packages, mainly rewritten, but some of the aspects of those features may be implemented better by smaller, individual packages (e.g., `enumitem` for lists).

For more information, see [Peter Wilson's *The memoir class*](https://www.tug.org/pracjourn/2006-3/wilson/wilson.pdf) and [TeX.SX's "What are the strengths and weaknesses of KOMA-Script and memoir?"](https://tex.stackexchange.com/q/7742).

## What is the `beamer` class?

[**`beamer`**](https://ctan.org/pkg/beamer) is a LaTeX document class used for producing presentations and slides. The class works in both PostScript and direct PDF output modes, using the `pgf` graphics system for visual effects. 

For more information, see [TeX.SX Questions Tagged With `[beamer]`](https://tex.stackexchange.com/questions/tagged/beamer).

## What is the `standalone` class and package?

[**`standalone`**](https://ctan.org/pkg/standalone) is a LaTeX document class and LaTeX package used for producing standalone LaTeX documents which allows users to easily place picture environments or other material in their source files and compile these on their own or as part of a main document. The `standalone` class handles such files, which by default crops the resulting output file to
the content.

For more information, see [TeX.SX Questions Tagged With `[standalone]`](https://tex.stackexchange.com/questions/tagged/standalone).

## What are math modes in LaTeX?

LaTeX provides two writing modes for typesetting mathematics:

### LaTeX Inline Math Mode

**Inline math mode** is used for writing mathematical expressions that are part of a paragraph. The TeX syntax for inline math mode is `$<inline-math-expression>$` while the LaTeX syntax is `\(<inline-math-expression>\)` (or the longer `\begin{math} <inline-math-expression> \end{math}`).

### LaTeX Display Math Mode

**Display math mode** is used for writing mathematical expressions that are not part of a text or paragraph and are typeset on separate lines. The TeX syntax for unnumbered single-equation display math mode is `$$<display-math-expression>$$` while the LaTeX syntax is `\[<display-math-expression>\]` (or the longer `\begin{displaymath} <display-math-expression> \end{displaymath}` or `\begin{equation*} <display-math-expression> \end{equation*}` with the `amsmath` package).

For more information, see [TeX.SX Questions Tagged With `[math-mode]`](https://tex.stackexchange.com/questions/tagged/math-mode).

## How can I type LaTeX macros faster?

I would personally recommend using local TeX editors that support customizable user snippets that may increase your speed in typing LaTeX macros (especially paired with helpful keybindings for code navigation).  I personally use VS Code + LaTeX Workshop (+ [Emacs Friendly Keymap](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) for a limited selection of Emacs keybindings) as my local TeX editor and VS Code has customizable user snippets (see [*Snippets in Visual Studio Code*](https://code.visualstudio.com/docs/editor/userdefinedsnippets) and [`snippet generator`](https://snippet-generator.app)). For TeX and LaTeX, you can edit the `tex.json` and `latex.json` files respectively to create your own snippets. For example, here is a LaTeX snippet for writing a general LaTeX document structure in VS Code:

```
// in file "C:\Users\<USERPROFILE>\AppData\Roaming\Code\User\snippets\latex.json"
{
	// Document Class
	"Document Class": {
		"prefix": "\\cls",
		"body": [
			"%!TEX program = lualatex\n\n% DOCUMENT CLASS\n\\documentclass${1:[${2:<options>}]}{${3:<class>}}${4:\n\n${5:% <preamble>}}\n\n% START OF DOCUMENT\n\\begin{document}\n\t${6:<document>}\n\\end{document}\n% END OF DOCUMENT"
		],
		"description": "\\documentclass[<options>]{<class>} <preamble> \\begin{document} <document> \\end{document}"
	}
}
```

## What are some recommended packages for LaTeX?

### LaTeX Packages for General Typesetting
  1. [**`babel`**](https://ctan.org/pkg/babel) ***or*** [**`polyglossia`**](https://ctan.org/pkg/polyglossia) (only for `XeLaTeX` and `LuaLaTeX`)
  2. [**`microtype`**](https://ctan.org/pkg/microtype)
  3. [**`setspace`**](https://ctan.org/pkg/setspace)

### LaTeX Packages for Font Selection and Unicode Support
  1. [**`fontspec`**](https://ctan.org/pkg/fontspec) (only for `XeLaTeX` and `LuaLaTeX`, see also [*`\fontspec` All the Fonts!*](https://www.overleaf.com/latex/templates/fontspec-all-the-fonts/hjrpnxhrrtxc))

  2. [**`unicode-math`**](https://ctan.org/pkg/unicode-math) (only for `XeLaTeX` and `LuaLaTeX`)
     - Loads [`fontspec`](https://ctan.org/pkg/fontspec)

  3. [**`newunicodechar`**](https://ctan.org/pkg/newunicodechar)

### LaTeX Packages for Mathematical and Scientific Typesetting
  1. [**`mathtools`**](https://ctan.org/pkg/mathtools)
     - Loads [`amsmath`](https://ctan.org/pkg/amsmath)
       - Loads [`amstext`](https://ctan.org/pkg/amstext)
         - Loads [`amsgen`](https://ctan.org/pkg/amsgen)
       - Loads [`amsbsy`](https://ctan.org/pkg/amsbsy)
         - Loads [`amsgen`](https://ctan.org/pkg/amsgen)
       - Loads [`amsopn`](https://ctan.org/pkg/amsopn)
         - Loads [`amsgen`](https://ctan.org/pkg/amsgen)

  2. [**`amssymb`**](https://ctan.org/pkg/amssymb)
     - Loads [`amsfonts`](https://ctan.org/pkg/amsfonts)

  3. [**`amsthm`**](https://ctan.org/pkg/amsthm)

  4. [**`mleftright`**](https://ctan.org/pkg/mleftright)

  5. [**`centernot`**](https://ctan.org/pkg/centernot)

  5. [**`siunitx`**](https://ctan.org/pkg/siunitx)

  6. [**`systeme`**](https://ctan.org/pkg/systeme)

  7. [**`polynom`**](https://ctan.org/pkg/polynom)

### LaTeX Packages for Source Code Typesetting
  1. [**`listings`**](https://ctan.org/pkg/listings)

### LaTeX Packages for List Environments
  1. [**`enumitem`**](https://ctan.org/pkg/enumitem)

### LaTeX Packages for Tables
  1. [**`array`**](https://ctan.org/pkg/array)
  2. [**`tabularx`**](https://ctan.org/pkg/tabularx)
  3. [**`booktabs`**](https://ctan.org/pkg/booktabs)
  4. [**`longtable`**](https://ctan.org/pkg/longtable)
  5. [**`multirow`**](https://ctan.org/pkg/multirow)
  6. [**`cellspace`**](https://ctan.org/pkg/cellspace)
  7. [**`tabularray`**](https://ctan.org/pkg/tabularray)
  8. [**`nicematrix`**](https://ctan.org/pkg/nicematrix)

### LaTeX Packages for Colors
  1. [**`xcolor`**](https://ctan.org/pkg/xcolor)

### LaTeX Packages for Graphics Inclusion
  1. [**`graphicx`**](https://ctan.org/pkg/graphicx)

### LaTeX Packages for Placeholder Texts
  1. [**`lipsum`**](https://ctan.org/pkg/lipsum)
  2. [**`blindtext`**](https://ctan.org/pkg/blindtext)

### LaTeX Packages for Citations and Bibliographies
  1. [**`biblatex`**](https://ctan.org/pkg/biblatex)

### LaTeX Packages for LaTeX Programming
  1. [**`ifthen`**](https://ctan.org/pkg/ifthen)

### LaTeX Packages for Hyperlinks and Cross-References
  1. [**`hyperref`**](https://ctan.org/pkg/hyperref)
  2. [**`cleveref`**](https://ctan.org/pkg/cleveref)
  3. [**`bookmark`**](https://ctan.org/pkg/bookmark)

### LaTeX Packages for Vector Graphics Production
1. [**`tikz`**](https://ctan.org/pkg/pgf) (see [the PGF/TikZ section](https://github.com/amanuensisfrances/TeX-et-al/edit/main/README.md#what-is-pgftikz))
2. [**`pgfplots`**](https://ctan.org/pkg/pgfplots)
3. [**`todonotes`**](https://ctan.org/pkg/todonotes)
4. [**`forest`**](https://ctan.org/pkg/forest)

For more package recommendations, see [TeX.SX's "What packages do people load by default in LaTeX?"](https://tex.stackexchange.com/q/553) and [*A one page, dictatorial guide to LaTeX packages*](https://amunn.github.io/assets/latex/latex-guide.pdf).

## What is PGF/TikZ?

[**`pgf`**](https://ctan.org/pkg/pgf) (typeset as **PGF**, stands for Portable Graphics Format) is a lower-level language and LaTeX package for producing vector graphics (e.g., technical illustrations and drawings) from a geometric/algebraic description, with standard features including the drawing of points, lines, arrows, paths, circles, ellipses and polygons. It is platform- and format-independent and works together with the most important TeX backend drivers, including `pdftex` and `dvips` (a DVI to PostScript driver). **`tikz`** (typeset as **Ti*k*Z**, stands for "TikZ ist kein Zeichenprogramm" which is German [recursive acronym](https://en.wikipedia.org/wiki/Recursive_acronym) for "Ti*k*Z is not a drawing program") is a user-friendly syntax layer and set of higher-level macros called that use `pgf`, and both are originally written by Till Tantau and currently developed and maintained by [the PGF/Ti*k*Z team](https://mirror.unpad.ac.id/ctan/graphics/pgf/base/doc/pgfmanual.pdf#subsection.1.5).

For more information, see [TeX.SX Questions Tagged With `[tikz-pgf]`](https://tex.stackexchange.com/questions/tagged/tikz-pgf).

## What are the different LaTeX macros and switches for font sizes, font families, and font styles?

### LaTeX Font Size Switches

  1. **`\tiny`**
  2. **`\scriptsize`**
  3. **`\footnotesize`**
  4. **`\small`**
  5. **`\normalsize`**
  6. **`\large`**
  7. **`\Large`**
  8. **`\LARGE`**
  9. **`\huge`**
  10. **`\Huge`**

### LaTeX Font Family Macros

  1. **`\textrm{<serif/roman-text>}`** (Serif/Roman)
  2. **`\textsf{<sans-serif-text>}`** (Sans Serif)
  3. **`\texttt{<monospaced/typewriter-text>}`** (Monospaced/typewriter)

### LaTeX Font Family Switches

  1. **`\rmfamily`** (Serif/Roman)
  2. **`\sffamily`** (Sans Serif)
  3. **`\ttfamily`** (Monospaced/Typewriter)

### LaTeX Font Weight Macros

  1. **`\textmd{<medium-weight-text>}`** (Medium Weight)
  2. **`\textbf{<boldface-text>}`** (Boldface)

### LaTeX Font Weight Switches

  1. **`\mdseries`** (Medium Weight)
  2. **`\bfseries`** (Boldface)

## LaTeX Font Style Macros

  1. **`\textup{<upright-text>}`** (Upright)
  2. **`\textit{<italic-text>}`** (Italic)
  3. **`\textsl{<slanted-text>}`** (Slanted)
  4. **`\textsc{<text-in-small-caps>}`** (Small Caps)

## LaTeX Font Style Switches

  1. **`\upshape`** (Upright)
  2. **`\itshape`** (Italic)
  3. **`\slshape`** (Slanted)
  4. **`\scshape`** (Small Caps)

## LaTeX Default Font Macro (**`\textnormal{<text-in-default-text-font>}`**)

## LaTeX Default Font Switch (**`\normalfont`**)

## LaTeX Math Mode Font Macros

  1. **`\mathrm{<serif/roman-math>}`**
  2. **`\mathsf{<sans-serif-math>}`**
  3. **`\mathtt{<monospaced/typewriter-math>}`**
  4. **`\mathbf{<boldface-math>}`**
  5. **`\mathit{<italic-math>}`**
  6. **`\mathbb{<blackboard-bold-math>}`**
  7. **`\mathcal{<calligraphic-math>}`**
  8. **`\mathscr{<script-math>}`**
  9. **`\mathfrak{<fraktur-math>}`**
  10. **`\mathbfit{<bold-italic-math>}`**
  11. **`\mathnormal{<math-in-default-math-font>}`**

For more information, see [*Font sizes, families, and styles* on the Overleaf documentation](https://www.overleaf.com/learn/latex/Font_sizes%2C_families%2C_and_styles), [TeX.SX's "Write 'text' \*\*correctly\*\* in equations"](https://tex.stackexchange.com/q/130510), and [TeX.SX's "What's the usual, standard way to write text in math mode?"](https://tex.stackexchange.com/q/394226).

## What are some nice text and mathematics fonts to use for LaTeX?

These are ones I personally use:

### Serif/Roman Text Fonts
  - [**Baskervaldx**](https://mirrors.ctan.org/fonts/baskervaldx.zip) (free with a [GNU GPL2+ license](https://ctan.org/license/gpl2+)), specifically: `Baskervaldx-Reg.otf` for the upright font style, `Baskervaldx-Bol.otf` for the bold style, `Baskervaldx-Ita.otf` for the italic style, and `Baskervaldx-BolIta.otf` for the bold italic font style.
  - [**NewComputerModern**](https://mirrors.ctan.org/fonts/newcomputermodern.zip) (free with a [GUST Font License (GFL)](https://ctan.org/license/gfl)), specifically: `NewCM10-Book.otf` for the upright font style, `NewCM10-Bold.otf` for the bold font style, `NewCM10-BookItalic.otf` for the italic font style, and `NewCM10-BoldItalic.otf` for the bold italic font style.
  - [**BaskervilleF**](https://mirrors.ctan.org/fonts/baskervillef.zip) (free with a [SIL Open Font License (OFL)](https://ctan.org/license/ofl)), specifically: `BaskervilleF-Regular.otf` for the upright font style, `BaskervilleF-Bold.otf` for the bold font style, `BaskervilleF-Italic.otf` for the italic font style, `BaskervilleF-BoldItalic.otf` for the bold italic font style.

### Sans Serif Text Fonts
  - [**URW Classico**](https://mirrors.ctan.org/fonts/urw/classico.zip) (free with a [No Commercial Use license](https://ctan.org/license/nocommercial)), specifically: `URWClassico-Regular.otf` for the upright font style, `URWClassico-Bold.otf` for the bold font style, `URWClassico-Italic.otf` for the italic font style, `URWClassico-BoldItalic.otf` for the bold italic font style.
  - [**NewComputerModern Sans**](https://mirrors.ctan.org/fonts/newcomputermodern.zip) (free with a [GUST Font License (GFL)](https://ctan.org/license/gfl)), specifically: `NewCMSans10-Book.otf` for the upright font style, `NewCMSans10-Bold.otf` for the bold font style, `NewCMSans10-BookOblique.otf` for the italic font style, and `NewCMSans10-BoldOblique.otf` for the bold italic font style.

### Monospace/Typewriter Text Fonts
  - [**JetBrains Mono**](https://github.com/JetBrains/JetBrainsMono/releases/latest) (free with a [SIL Open Font License (OFL)](https://github.com/JetBrains/JetBrainsMono/blob/master/OFL.txt)), specifically: `JetBrainsMono-Light.ttf` for the upright font style, `JetBrainsMono-Bold.ttf` for the bold font style, `JetBrainsMono-LightItalic.ttf` for the italic font style, `JetBrainsMono-BoldItalic.ttf` for the bold italic font style.

### Mathematics Fonts
  - **NewComputerModern Math** (free with a [GUST Font License (GFL)](https://ctan.org/license/gfl)), specifically `NewCMMath-Book.otf`.

For more recommendations, see [TeX.SX's "What best combination of fonts for Serif, Sans, and Mono do you recommend?"](https://tex.stackexchange.com/q/9533), [TeX.SX's "Suggest a "nice" font family for my basic LaTeX template (text and math)"](https://tex.stackexchange.com/q/59702), [TeX.SX's "Which OpenType Math fonts are available?"](https://tex.stackexchange.com/q/425098)

## How do I load fonts when using LuaLaTeX?
Assuming you've installed a TeX distribution and a TeX editor, I will be giving an example of how to load fonts when using `LuaLaTeX` specifically as that is the TeX format (`LaTeX2e`) and engine (`LuaTeX`) I use the most. First, create a main LaTeX file (e.g., `main.tex`). Second, create a fonts folder (e.g., `Fonts/`) in the same directory as your main file and paste the fonts you want to use in this folder. Let's say you have 16 different font files which consist of 4 different font families with 4 font styles each:

1. `<SerifFont>-Regular<serif-font-extension>`
2. `<SerifFont>-Bold<serif-font-extension>`
3. `<SerifFont>-Italic<serif-font-extension>`
4. `<SerifFont>-BoldItalic<serif-font-extension>`
5. `<SansSerifFont>-Regular<sans-font-extension>`
6. `<SansSerifFont>-Bold<sans-font-extension>`
7. `<SansSerifFont>-Oblique<sans-font-extension>`
8. `<SansSerifFont>-BoldOblique<sans-font-extension>`
9. `<MonospacedFont>-Regular<mono-font-extension>`
10. `<MonospacedFont>-Bold<mono-font-extension>`
11. `<MonospacedFont>-Italic<mono-font-extension>`
12. `<MonospacedFont>-BoldItalic<mono-font-extension>`
13. `<FourthFontFamily>-Regular<fourth-font-extension>`
14. `<FourthFontFamily>-Bold<fourth-font-extension>`
15. `<FourthFontFamily>-Italic<fourth-font-extension>`
16. `<FourthFontFamily>-BoldItalic<fourth-font-extension>`

Next, your main file should look something like the following (there may be other ways but this is how I load my fonts when using `LuaLaTeX`):

```
%!TEX program = lualatex

\documentclass[<options>]{<document-class>}

% \usepackage[<language-option>]{babel} % For multilingual typesetting (optional but recommended)
% \usepackage[babel]{microtype} % For microtypography (optional but recommended)
\usepackage{fontspec} % For loading text fonts
\setmainfont[%
    Scale = <font-scale>, % default value is 1
    Path = <fonts-folder>/,
    Extension = <serif-font-extension>,
    UprightFont = *-Regular,
    BoldFont = *-Bold,
    ItalicFont = *-Italic,
    BoldItalicFont = *-BoldItalic
]{<SerifFont>}
\setsansfont[%
    Scale = <font-scale>, % default value is 1
    Path = <fonts-folder>/,
    Extension = <sans-font-extension>,
    UprightFont = *-Regular,
    BoldFont = *-Bold,
    ItalicFont = *-Oblique,
    BoldItalicFont = *-BoldOblique
]{<SansSerifFont>}
\setmonofont[%
    Scale = <font-scale>, % default value is 1
    Path = <fonts-folder>/,
    Extension = <mono-font-extension>,
    UprightFont = *-Regular,
    BoldFont = *-Bold,
    ItalicFont = *-Italic,
    BoldItalicFont = *-BoldItalic
]{<MonospacedFont>}

\begin{document}
    <text>
\end{document}
```

These are main three font families you will use for your LaTeX document. If you want to occassionally switch to a fourth font family, you can use the `\newfontfamily` macro, instead of `\setmainfont`/`\setsansfont`/`\setmonofont`, and define `\FourthFontFamily` ***in the preamble*** as follows:

```
\newfontfamily{\FourthFontFamily}[%
    Scale = <font-scale>, % default value is 1
    Path = <fonts-folder>/,
    Extension = <fourth-font-extension>,
    UprightFont = *-Regular,
    BoldFont = *-Bold,
    ItalicFont = *-Italic,
    BoldItalicFont = *-BoldItalic
]{<FourthFontFamily>}
```

Now you can switch to the fourth font family by writing `{\FourthFontFamily <text>}`. For more information, read [TeX.SX's "How do I use a particular font for a small section of text in my document?"](https://tex.stackexchange.com/q/25249)

## What are some nice LaTeX templates?

- My [`LuaLaTeX-KOMA-Script-Templates`](https://github.com/amanuensisfrances/LuaLaTeX-KOMA-Script-Templates)
- [TeX.SX's "LaTeX templates for writing a thesis"](https://tex.stackexchange.com/q/326)
- [TeX.SX's "Writing and Managing Thesis in LaTeX"](https://tex.stackexchange.com/q/29531)
- [TeX.SX's "Starting a PhD; Any guides to setting up a 'system'?"](https://tex.stackexchange.com/q/31103)
- [TeX.SX's "LaTeX template for resume/curriculum vitae"](https://tex.stackexchange.com/q/80)
- [TeX.SX's "Package for certificates"](https://tex.stackexchange.com/q/46406)
- [TeX.SX's "Does anybody know a good source of (free) ornaments, decorations, frames, backgrounds etc.?"](https://tex.stackexchange.com/q/41159)

Also, see [Peter Flynn's *A university thesis class: Automation and its pitfalls*](https://tug.org/TUGboat/tb33-2/tb104flynn.pdf) and [Nicola L. C. Talbot's *Using LaTeX to Write a PhD Thesis*](https://mirrors.ctan.org/info/dickimaw/dickimaw-thesis.pdf).

## What are some useful LaTeX-related tools?

### 1. [MathJax](https://www.mathjax.org), a cross-browser JavaScript library that displays mathematical notation in web browsers (also, see [*MathJax basic tutorial and quick reference*](https://math.meta.stackexchange.com/q/5020))

### 2. [MathB.in](https://mathb.in/), a pastebin for sharing LaTeX and Markdown source code snippets

### 3. [EditTeX](https://edittex.com/), an online LaTeX equation editor and a converter with LaTeX math mode expressions as inputs and SVG/PNG/JPG files as outputs

### 4. [LaTeX2Image](https://latex2image.joeraut.com/), an online converter with LaTeX math mode expressions as inputs and SVG/PNG/JPG files as outputs

### 5. [`latex2png.com`](https://latex2png.com/), an online converter with LaTeX math mode expressions as inputs and PNG files as outputs

### 6. [Detexify](https://detexify.kirelabs.org/), an online converter with handwritten math symbols as inputs and LaTeX math mode expressions as outputs

### 7. [`unicodeit.net`](https://www.unicodeit.net/), an online converter with LaTeX expressions as inputs and Unicode characters as outputs

### 8. [Unicode / LaTeX Conversion](https://www.johndcook.com/unicode_latex.html), an online converter with Unicode characters as inputs and LaTeX expressions as outputs

### 9. [SimpleTex](https://simpletex.cn/), an OCR software and converter with mathematical formula images as inputs and LaTeX code as outputs

### 10. [pix2tex](https://pix2tex.readthedocs.io/en/latest), an OCR command-line tool with an optional GUI and converter with mathematical formula images as inputs and LaTeX code as outputs

### 11. [Tables Generator](https://www.tablesgenerator.com/latex_tables), an online table generator for LaTeX, HTML, plain text, Markdown, and MediaWiki

### 12. [Quiver](https://q.uiver.app/), an online graphical editor for commutative and pasting diagrams using the [`quiver` package](https://raw.githubusercontent.com/varkor/quiver/master/src/quiver.sty) which loads [`tikz-cd`](https://ctan.org/pkg/tikz-cd) which itself loads [`tikz`](https://ctan.org/pkg/pgf)

## What are some useful resources for reading and learning more about TeX, LaTeX, etc.?

### 1. [The Comprehensive TeX Archive Network (CTAN)](https://ctan.org/)
   - [*What are TeX and its friends?*](https://ctan.org/tex)
   - [`tex` – A sophisticated typesetting engine](https://ctan.org/pkg/tex)
   - [`latex` – A TeX macro package that defines LaTeX](https://ctan.org/pkg/latex)
   - [`amstex` – American Mathematical Society Plain TeX macros](https://ctan.org/pkg/amstex)
   - [`joy-of-tex` – User documentation for the AMS-TeX macro collection](https://ctan.org/pkg/joy-of-tex)
   - [`etex` – An extended version of TeX, from the NTS project](https://ctan.org/pkg/etex)
   - [`pdftex` – A TeX extension for direct creation of PDF](https://ctan.org/pkg/pdftex)
   - [`xetex` – An extended variant of TeX for use with Unicode sources](https://ctan.org/pkg/xetex)
   - [`luatex` – The LuaTeX engine](https://ctan.org/pkg/luatex)
   - [`source2e` – LaTeX2ε kernel documentation for the entire system as one document](https://ctan.org/pkg/source2e)
   - [`macros2e` – A list of internal LaTeX2ε macros](https://ctan.org/pkg/macros2e)
   - [`latex-base` – Base sources of LaTeX](https://ctan.org/pkg/latex-base)
   - [`required` – Packages "required" of a LaTeX distribution](https://ctan.org/pkg/required)
   - [`l3kernel` – LaTeX3 programming conventions](https://ctan.org/pkg/l3kernel)
   - [`l3packages` – High-level LaTeX3 concepts](https://ctan.org/pkg/l3packages)
   - [`usrguide` – User-mode documentation for LaTeX](https://ctan.org/pkg/usrguide)
   - [`lshort-english` – A (Not So) Short Introduction to LaTeX2ε](https://ctan.org/pkg/lshort-english)
   - [`latex2e-help-texinfo` – Unofficial reference manual covering LaTeX2ε](https://ctan.org/pkg/latex2e-help-texinfo) (also, see the website [`latexref.xyz`](https://latexref.xyz/))
   - [`yet-another-guide-latex2e` – A short guide to using LaTeX2ε to typeset high quality documents](https://ctan.org/pkg/yet-another-guide-latex2e)
   - [`l2tabu-english` – English translation of "Obsolete packages and commands"](https://ctan.org/pkg/l2tabu-english)
   - [`clsguide` – Documentation of LaTeX class and package writing](https://ctan.org/pkg/clsguide)
   - [`maths-symbols` – Summary of mathematical symbols available in LaTeX](https://ctan.org/pkg/maths-symbols)
   - [`comprehensive` – Symbols accessible from LaTeX](https://ctan.org/pkg/comprehensive)
   - [`short-math-guide` – Guide to using amsmath and related packages to typeset mathematical notation with LaTeX](https://ctan.org/pkg/short-math-guide)
   - [`beginlatex` – A beginner's guide to LaTeX](https://ctan.org/pkg/beginlatex) (also, see the updated version, [*Formatting Information*](https://latex.silmaril.ie/formattinginformation))
   - [`latex-for-undergraduates` – A tutorial aimed at introducing undergraduate students to LaTeX](https://ctan.org/pkg/latex-for-undergraduates)
   - [`undergradmath` – LaTeX Math for Undergraduates cheat sheet](https://ctan.org/pkg/undergradmath)
   - [`latex-doc-ptr` – A direction-finder for LaTeX resources available online](https://ctan.org/pkg/latex-doc-ptr)
   - [`tex-overview` – An overview of the development of TeX](https://ctan.org/pkg/tex-overview)
   - [`ltnews` – The latest LaTeX news](https://ctan.org/pkg/ltnews)

### 2. [The LaTeX Project](https://www.latex-project.org/)
   - [*The LaTeX Project (aka LaTeX3 Project)*](https://www.latex-project.org/latex3)
   - [`ltx3info.pdf`/*The LaTeX3 Project* - Frank Mittelbach, Chris Rowley](https://www.latex-project.org/help/documentation/ltx3info.pdf)
   - [*Core Documentation*](https://www.latex-project.org/help/documentation) (for the most recent version of the user documentation, visit `usrguide` on CTAN which is linked above]
   - [*The LaTeX2e Kernel Code Repository*](https://github.com/latex3/latex2e)
   - [*The LaTeX3 Programming Language* - David Carlisle, Chris Rowley, Frank Mittelbach](https://www.latex-project.org/publications/1997-DPC-TUB-tb18-4-expl3-proposal.pdf)
   - [*TeX, LaTeX and math* - Enrico Gregorio](https://www.latex-project.org/publications/2020-egreg-TUB-tb127gregorio-math.pdf)
   - [`learnlatex.org`: Taking LaTeX training fully interactive - David Carlisle, Paulo Roberto Massa Cereda, Joseph Wright](https://www.latex-project.org/publications/2020-DPC-TUB-tb128carlisle-learnlatex.pdf)

### 3. [The TeX and LaTeX documentation lookup system (texdoc)](https://texdoc.org/)
   - [`tex.pdf`](https://texdoc.org/serve/tex.pdf/0) (a version of [`tex.web`](https://mirrors.ctan.org/systems/knuth/dist/tex/tex.web) compiled as a PDF thanks to Knuth's [Literate Programming](https://en.wikipedia.org/wiki/Literate_programming))

### 4. [The TeX Users Group (TUG)](https://tug.org/)
   - [*Just what is TeX?*](https://tug.org/whatis.html)
   - [*LaTeX vs. MiKTeX: The levels of TeX*](https://tug.org/levels.html)
   - [*Getting started with TeX, LaTeX, and friends*](https://tug.org/begin.html)
   - [*TeX Reference Manual* (2002) - David Bausum](https://tug.org/utilities/plain/trm.html)
   - [*Macros: A complement to \smash, \llap, and \rlap* (2001) - Alexander R. Perlis](https://tug.org/TUGboat/Articles/tb22-4/tb72perlS.pdf)
   - [*Tables in LaTeX2ε: Packages and Methods* (2007) - Lapo Filippo Mori](https://www.tug.org/pracjourn/2007-1/mori/mori.pdf)

### 5. [The TeX FAQ](https://texfaq.org/)
   - [*Things with “TeX” in the name*](https://texfaq.org/FAQ-texthings)

### 6. [TeX Stack Exchange (TeX.SX)](https://tex.stackexchange.com/)
   - [TeX Stack Exchange Community Wiki Questions](https://tex.stackexchange.com/search?tab=votes&q=wiki%3atrue)
   - [TeX Stack Exchange's "What is the difference between TeX and LaTeX?"](https://tex.stackexchange.com/q/49)
   - [TeX Stack Exchange's "What are TeX and LaTeX?"](https://tex.stackexchange.com/q/6776)
   - [TeX Stack Exchange's "The differences between TeX engines"](https://tex.stackexchange.com/q/13593)
   - [TeX STack Exchange's "Differences between LuaTeX, ConTeXt and XeTeX"](https://tex.stackexchange.com/q/36)
   - [TeX Stack Exchange's "Glossary of TeX and LaTeX terms"](https://tex.stackexchange.com/q/58431)
   - [TeX Stack Exchange's "Which manuals are on your 'TeX Reference' shelf?](https://tex.stackexchange.com/q/66)
   - [TeX Stack Exchange's "What are good learning resources for a LaTeX beginner?"](https://tex.stackexchange.com/q/11)
   - [TeX Stack Exchange's "Everyday LaTeX and workflow?"](https://tex.stackexchange.com/q/22431)
   - [TeX Stack Exchange's "Where do I start LaTeX programming?"](https://tex.stackexchange.com/q/12668)
   - [TeX Stack Exchange's "Consistent typography"](https://tex.stackexchange.com/q/29840)

### 7. [`learnlatex.org`](https://www.learnlatex.org/)

### 8. [Overleaf Documentation](https://www.overleaf.com/learn)
   - [*What's in a Name: A Guide to the Many Flavours of TeX*](https://www.overleaf.com/learn/latex/Articles/What%27s_in_a_Name%3A_A_Guide_to_the_Many_Flavours_of_TeX#What%E2%80%99s_in_a_name?)

   - [*The TeX family tree: LaTeX, pdfTeX, XeTeX, LuaTeX and ConTeXt*](https://www.overleaf.com/learn/latex/Articles/The_TeX_family_tree%3A_LaTeX%2C_pdfTeX%2C_XeTeX%2C_LuaTeX_and_ConTeXt)

   - [*A six-part series: How do TeX macros actually work?*](https://www.overleaf.com/learn/latex/A_six-part_series%3A_How_do_TeX_macros_actually_work%3F)
     - [*How TeX macros actually work*: Part 1](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_1)     
     - [*How TeX macros actually work*: Part 2](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_2)
     - [*How TeX macros actually work*: Part 3](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_3)
     - [*How TeX macros actually work*: Part 4](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_4)
     - [*How TeX macros actually work*: Part 5](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_5)
     - [*How TeX macros actually work*: Part 6](https://www.overleaf.com/learn/latex/How_TeX_macros_actually_work%3A_Part_6)

   - [*A New Series of Articles: TeX Tokens and Related Concepts—But Why (and How)?*](https://www.overleaf.com/learn/latex/Articles/A_New_Series_of_Articles%3A_TeX_Tokens_and_Related_Concepts—But_Why_(and_How)%3F)
     - [*What is a "TeX token"?*](https://www.overleaf.com/learn/latex/Articles/What_is_a_%22TeX_token%22%3F)
     - [*What is a TeX token list?*](https://www.overleaf.com/learn/latex/Articles/What_is_a_TeX_token_list)

   - [*A six-part article series on \expandafter, TeX tokens and expansion*](https://www.overleaf.com/learn/latex/Articles/A_six-part_article_series_on_%5Cexpandafter%2C_TeX_tokens_and_expansion)
     - [*How does \expandafter work: An introduction to TeX tokens*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_An_introduction_to_TeX_tokens)
     - [*How does \expandafter work: The meaning of expansion*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_The_meaning_of_expansion)
     - [*How does \expandafter work: TeX uses temporary token lists*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_TeX_uses_temporary_token_lists)
     - [*How does \expandafter work: From basic principles to exploring TeX's source code*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_From_basic_principles_to_exploring_TeX%27s_source_code)
     - [*How does \expandafter work: A detailed macro case study*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_A_detailed_macro_case_study)
     - [*How does \expandafter work: A detailed study of consecutive \expandafter commands*](https://www.overleaf.com/learn/latex/Articles/How_does_%5Cexpandafter_work%3A_A_detailed_study_of_consecutive_%5Cexpandafter_commands)

   - [*Learn LaTeX in 30 minutes*](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)
   - [*An Introduction to LuaTeX (Part 1): What is it—and what makes it so different?*](https://www.overleaf.com/learn/latex/Articles/An_Introduction_to_LuaTeX_(Part_1)%3A_What_is_it%E2%80%94and_what_makes_it_so_different%3F)
   - [*An Introduction to LuaTeX (Part 2): Understanding \directlua*](https://www.overleaf.com/learn/latex/Articles/An_Introduction_to_LuaTeX_(Part_2)%3A_Understanding_%5Cdirectlua)
   - [*How to draw Vector Graphics using TikZ in LaTeX*](https://www.overleaf.com/learn/latex/Articles/How_to_draw_Vector_Graphics_using_TikZ_in_LaTeX)
   - [*Getting started with BibLaTeX*](https://www.overleaf.com/learn/latex/Articles/Getting_started_with_BibLaTeX)

### 9. [The TeX article on Wikibooks](https://en.wikibooks.org/wiki/TeX) and [The LaTeX article on Wikibooks](https://en.wikibooks.org/wiki/LaTeX)

### 10. [texblog](https://texblog.org/)

### 11. [TikZBlog](https://latexdraw.com/)

### 12. Recommended Books on TeX and LaTeX
   - *Computers and Typesetting, Volume A: The TeXbook* (1986) - Donald E. Knuth [(Source code available on CTAN)](https://ctan.org/pkg/texbook)
   - *Computers and Typesetting, Volume B: TeX: The Program* (1986) - Donald E. Knuth
   - [*TeX by Topic, A TeXnician's Reference* (2019) - Victor Eijkhout](https://raw.githubusercontent.com/VictorEijkhout/tex-by-topic/main/TeXbyTopic.pdf)
   - [*TeX for the Impatient* (2020) - Paul W. Abrahams, Kathryn A. Hargreaves, and Karl Berry](https://ctan.org/pkg/impatient)
   - *A Beginner's Book of TeX* (1991) - Raymond Seroul , Silvio Levy
   - *LaTeX: A document preparation system*, 2nd Edition (1994) - Leslie Lamport
   - *The LaTeX Companion*, 3rd Edition (2023) - Frank Mittelbach, Ulrike Fischer
   - *A Guide to LaTeX*, 4th Edition (2003) -  Helmut Kopka, Patrick W. Daly
   - *More Math Into LaTeX*, 5th Edition (2016) - George Grätzer
   - *Digital Typography Using LaTeX* (2003) - Apostolos Syropoulos, Antonis Tsolomitis, Nick Sofroniou
   - *LaTeX and Friends* (2012) - M. R. C. van Dongen
   - [*LaTeX for Complete Novices* (2012) - Nicola L. C. Talbot](https://mirrors.ctan.org/info/dickimaw/dickimaw-novices.pdf)

### 13. Miscellaneous TeX, LaTeX, and Typography Resources
   - [*Notes On Programming in TeX* (2021) - Christian Feuersänger](https://pgfplots.sourceforge.net/TeX-programming-notes.pdf)
   - [*Mathematical Typesetting with LaTeX* (2017) - Herbert Voß](https://www.gang.umass.edu/~franz/latexmanual.pdf)
   - [*LaTeX3: Programming in LaTeX with Ease*](https://www.alanshawn.com/latex3-tutorial)
   - [*A Few Notes on Book Design* (2018) - Peter Wilson](https://mirrors.ctan.org/info/memdesign/memdesign.pdf)

## What are some alternatives to TeX, LaTeX, etc.?

### 1. [Typst](https://typst.app/)
### 2. [Heirloom Troff](https://n-t-roff.github.io/heirloom/doctools.html)
### 3. [AsciiDoc](https://asciidoc.org/)
### 4. [SILE](https://sile-typesetter.org/) (also, see [*SILE: A new typesetting system* - Simon Cozens](https://tug.org/TUGboat/tb38-1/tb118cozens.pdf))
### 5. [Patoline](https://patoline.github.io/)

For more alternatives, see [*Alternatives to TeX*](https://texfaq.org/FAQ-alternatives) and [TeX.SX's "Alternatives to LaTeX"](https://tex.stackexchange.com/q/120271).
