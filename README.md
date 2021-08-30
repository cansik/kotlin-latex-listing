# Kotlin for LaTeX Listings [![Build LaTeX](https://github.com/cansik/kotlin-latex-listing/actions/workflows/main.yml/badge.svg)](https://github.com/cansik/kotlin-latex-listing/actions/workflows/main.yml)
Currently, I am writing my bachelor thesis with [Kotlin](https://kotlinlang.org/) and need to document some code in [LaTeX](https://www.latex-project.org/). The [lstpackage](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings) does not support kotlin syntax highlighting by default, so I decided to create a language template for it.

![Example](https://github.com/cansik/kotlin-latex-listing/releases/download/example/example.png)

Check out this example of the default style or [download](https://github.com/cansik/kotlin-latex-listing/releases/download/example/kotlin_example.pdf) the whole document.

Feel free to add more keywords or new styles!

## How to use it?
First of all you have to copy the language definition into your latex document:

```latex
\usepackage[dvipsnames]{xcolor}
\usepackage{listings}

\lstdefinelanguage{Kotlin}{
  comment=[l]{//},
  commentstyle={\color{gray}\ttfamily},
  emph={filter, first, firstOrNull, forEach, lazy, map, mapNotNull, println},
  emphstyle={\color{OrangeRed}},
  identifierstyle=\color{black},
  keywords={!in, !is, abstract, actual, annotation, as, as?, break, by, catch, class, companion, const, constructor, continue, crossinline, data, delegate, do, dynamic, else, enum, expect, external, false, field, file, final, finally, for, fun, get, if, import, in, infix, init, inline, inner, interface, internal, is, lateinit, noinline, null, object, open, operator, out, override, package, param, private, property, protected, public, receiveris, reified, return, return@, sealed, set, setparam, super, suspend, tailrec, this, throw, true, try, typealias, typeof, val, var, vararg, when, where, while},
  keywordstyle={\color{NavyBlue}\bfseries},
  morecomment=[s]{/*}{*/},
  morestring=[b]",
  morestring=[s]{"""*}{*"""},
  ndkeywords={@Deprecated, @JvmField, @JvmName, @JvmOverloads, @JvmStatic, @JvmSynthetic, Array, Byte, Double, Float, Int, Integer, Iterable, Long, Runnable, Short, String, Any, Unit, Nothing},
  ndkeywordstyle={\color{BurntOrange}\bfseries},
  sensitive=true,
  stringstyle={\color{ForestGreen}\ttfamily},
}
```

Then you have to set the language of your listing to `Kotlin`:

```latex
\begin{lstlisting}[caption={Simple code listing.}, label={lst:example1}, language=Kotlin]
// this is a simple code listing:
println("hello kotlin from latex")
\end{lstlisting}
```

And finally your listing should look like this:
![Simple Example](https://github.com/cansik/kotlin-latex-listing/releases/download/example/simple.png)
*(The border is not part of the language definition. Check out the [example.tex](example/kotlin_example.tex) for this style.)*

### Contributors
Feel free to add new or missing keywords and style enhancements. Just create a pull request. The github actions command automatically builds the example PDF and PNG and uploads it to the [Example release](https://github.com/cansik/kotlin-latex-listing/releases/tag/example).

Thanks to [@ppizarror](https://github.com/ppizarror), [@ice1000](https://github.com/ice1000), [@etwasanderes2](https://github.com/etwasanderes2/)
