The GC3 Beamer/LaTeX theme
==========================

This directory hosts the GC3 style files for use with the LaTeX
[beamer][1] document class.  You can see an example in the
[example.pdf](https://github.com/gc3-uzh-ch/beamer-theme-gc3/blob/master/example.pdf?raw=true)
file.

The GC3 theme is based on the Beamer theme [UZHNEU][2] by Juergen
Spitzmueller and the [Corporate Design section of the University of Zurich][3],
released on October 2010.


Distributed files
-----------------

The following files are included in this directory:

* `beamerthemegc3.sty`: The beamer theme file.
* `gc3.sty`: A LaTeX package with additional commands and customizations frequently used in GC3 presentations.
* `example.tex`: A sample presentation file.

### Logos

The GC3 theme files includes the [University of Zurich][uzh] logos on the
title slide (unless the `informal` style option is given, see "Usage"
below).

The logo files are not included in this repository for copyright
reasons; if you work at the [UZH][uzh], you can
[download them from the UZH Corporate Design website][logos].

The files containing the logos _must_ be named `uzh_logo_d_pos.pdf` or
`uzh_logo_e_pos.pdf`: the `e` one is the English/International
version, the `d` one is the German-language logo.  If you compile your
slides to a Postscript file instead of PDF, then you should use the
`.eps` files of the logos, instead of the `.pdf` ones.


Usage
-----

To use the GC3 beamer theme, copy the `beamerthemegc3.sty`, the
`gc3.sty` and the `uzh_logo_*_pos.pdf` files into the directory where
your LaTeX/beamer source is.

Include this command in your `.tex` file:

        \usetheme{gc3}

The GC3 theme looks better with serif and math serif fonts; to
activate those you need to pass options `serif` and `mathserif` to the
"beamer" document class:

        \documentclass[serif,mathserif]{beamer}

The `example.tex` file provides a sample presentation in the English
language with the "serif" font style.

### Options

By default, the GC3 theme prints the University logo and heading on
the title slide.  If you want to suppress this behavior and make the
title slide use the same look as the other ones, use the `informal`
option:

        \usetheme[informal]{gc3}

The GC3 theme detects the language in use and uses the German version
of the UZH logo if Beamer has been passed the `german` option.  You
can force the use of the German logo by passing option `german` (or
`deutsch`):

        \usetheme[german]{gc3}

Conversely, you can force usage of the English/International version
of the logo with the `english` option:

        \usetheme[english]{gc3}


Optional features from `gc3.sty`
--------------------------------

The `gc3.sty` LaTeX package defines a few additional typesetting
commands and environments that we have found useful.
To use them, insert this line in the preamble:

    \usepackage{gc3}

The following commands and LaTeX environments are defined in
`gc3.sty`:

* `\+`

  Adds a larger vertical separation between paragraphs or blocks; may be repeated multiple times for greater effect.

* `\begin{lstlisting} ... \end{lstlisting}`, `\begin{python} ... \end{python}`, `\begin{sh} ... \end{sh}`

  We load the [listings](http://www.ctan.org/pkg/listings) package and
  pref-configure it with colors that should blend well with the
  GC3/UZH slide set style.

  The `python` and `sh` environments are just shorthands for
  `\begin{lstlisting}[language=python]` and `...[language=sh]`
  respectively.

* `\HL{text}`

  Use `\HL` to highlight a region of text: `\HL{highlighted text}`.
  An optional highlighting color can be specified:
  `\HL[yellow!25]{yellow highlighter}`; color specifications follow
  the syntax allowed by the LaTeX
  [xcolor](http://www.ctan.org/pkg/xcolor) package.

* `\begin{question} ... \end{question}`

  Typeset a question.  Use Beamer's `\pause` and `\only` commands to reveal the answer.

* `\begin{references} ... \end{references}`, `\begin{seealso} ... \end{seealso}`

  Typeset references to additional material.

* `\begin{describe}{item} descriptive text \end{describe}`

  Typeset one item of a definition list; the item is typeset on a line of its own and highlighted.

* `\hl{text}`

  This is the highlighting used in the `describe` environment.

* `\begin{exercise} ... \end{exercise}`,
  `\begin{exercise*}[optional label] ... \end{exercise*}`

  Typeset an exercise; exercises are labeled sequentially with capital roman letters A, B, C, ...
  The starred version of the environment lets you specify the label (or does not label the block
  if no label text is provided.


Copyright and License
---------------------

The original [_UZHNEU_ theme][2] is Copyright 2010 Juergen Spitzmueller <spitzmueller@ds.uzh.ch>.

Modifications are Copyright 2012 Grid Computing Competence Center, University of Zurich <info@gc3.lists.uzh.ch>

The GC3 theme style files can be redistributed and/or modified under
the terms of the GNU Public License, version 3 or --at your option-- any
later version.


<!-- References: -->
[1]: https://bitbucket.org/rivanvx/beamer/wiki/Home
[2]: https://idcmslive01.uzh.ch/cd/live/vorlagenboerse/downloads.html#15
[3]: http://www.cd.uzh.ch/index.html

[uzh]: http://www.uzh.ch/
[logos]: http://www.cd.uzh.ch/downloads/logos.html

<!--
 LocalWords:  english usetheme
 -->
