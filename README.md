# pandoc-wrapfig: A pandoc filter for pdf/LaTeX export with the wrapfig package

pandoc-wrapfig is a simple [pandoc][] filter written in python 3. It simply allows use of the
[wrapfig][] package so that (specified) figures will have text wrapped around them.

## Installation

Obviously, the wrapfig package must be installed.

A pandoc template must be used that contains `\usepackage{wrapfig}`. The included template is the
default pandoc LaTeX template with this line added.

## Usage

Simply include ` {x}` at the end of the captions for figures that are to be wrapped. `x` is a number
that specifies the width of the wrap in inches. Setting it to 0 will cause the width of the figure
to be used (as per the wrapfig package instructions). Figures without the tag will float as usual.

To use a specific  length, you may also add `cm`,`pt`or `in` like `{5cm}`.

Also, wrapfig allows optional specification of the "number of narrow lines" that are aquivalent to 
height of the image. Though guessed by wrapfig, this sometimes has to be adjusted. This is possible 
by adding a second number to the `{}` argument like: `{5cm,28}`.

Wrapping is specific to pdf/LaTeX output. For other formats, the tag is simply removed.

[pandoc]: http://pandoc.org
[wrapfig]: https://www.ctan.org/pkg/wrapfig?lang=en
