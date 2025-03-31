# Kotlin for LaTeX Listings [![Build LaTeX](https://github.com/cansik/kotlin-latex-listing/actions/workflows/main.yml/badge.svg)](https://github.com/cansik/kotlin-latex-listing/actions/workflows/main.yml)
When I was writing my bachelor thesis using [Kotlin](https://kotlinlang.org/) and needed to document some code in [LaTeX](https://www.latex-project.org/), I realized that the [lstpackage](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings) does not support Kotlin syntax highlighting by default. So, I decided to create a language template for it.

![Example](https://github.com/cansik/kotlin-latex-listing/releases/download/example/example.png)

Check out this example of the default style or [download](https://github.com/cansik/kotlin-latex-listing/releases/download/example/kotlin_example.pdf) the complete document.

Feel free to add more keywords or define new styles!

## How to use it?
First of all, you need to copy the language definition into your LaTeX document:

```latex
\usepackage[dvipsnames]{xcolor}
\usepackage{listings}

\lstdefinelanguage{Kotlin}{
  comment=[l]{//},
  commentstyle={\color{gray}\ttfamily},
  emph={filter, first, firstOrNull, forEach, lazy, map, mapNotNull, println},
  emphstyle={\color{OrangeRed}},
  identifierstyle=\color{black},
  keywords={!in, !is, abstract, actual, annotation, as, as?, break, by, catch, class, companion, const, constructor, continue, crossinline, data, delegate, do, dynamic, else, enum, expect, external, false, field, file, final, finally, for, fun, get, if, import, in, infix, init, inline, inner, interface, internal, is, lateinit, noinline, null, object, open, operator, out, override, package, param, private, property, protected, public, receiver, reified, return, return@, sealed, set, setparam, super, suspend, tailrec, this, throw, true, try, typealias, typeof, val, var, vararg, when, where, while},
  keywordstyle={\color{NavyBlue}\bfseries},
  escapeinside={//(`}{`)},
  morecomment=[s]{/*}{*/},
  morestring=[b]",
  morestring=[s]{"""*}{*"""},
  ndkeywords={@Composable, @Preview, @Deprecated, @JvmField, @JvmName, @JvmOverloads, @JvmStatic, @JvmSynthetic, Array, Byte, Double, Float, Int, Integer, Iterable, Long, Runnable, Short, String, Any, Unit, Nothing},
  ndkeywordstyle={\color{BurntOrange}\bfseries},
  sensitive=true,
  stringstyle={\color{ForestGreen}\ttfamily},
}
```

Then you need to set the language of your listing to `Kotlin`:

```latex
\begin{lstlisting}[caption={Simple code listing.}, label={lst:example1}, language=Kotlin]
// this is a simple code listing:
println("hello kotlin from latex")
\end{lstlisting}
```

And finally, your listing should look like this:  
![Simple Example](https://github.com/cansik/kotlin-latex-listing/releases/download/example/simple.png)  
*(The border is not part of the language definition. Check out [example.tex](example/kotlin_example.tex) for this style.)*

### Contributors  
Feel free to add new or missing keywords and style enhancements—just create a pull request. The GitHub Actions command automatically builds the example PDF and PNG and uploads them to the [Example release](https://github.com/cansik/kotlin-latex-listing/releases/tag/example).

Thanks to [@ppizarror](https://github.com/ppizarror), [@ice1000](https://github.com/ice1000), [@etwasanderes2](https://github.com/etwasanderes2/), [@erdodif](https://github.com/erdodif)
