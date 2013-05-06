An example SBT project which uses macro paradise 2.10 (Scala macro-paradise 2.10, SBT 0.12)

1) Macro paradise 2.10 makes it possible to utilize quasiquotes, a feature of the full-fledged macro paradise
ported to Scala 2.10.x: [http://docs.scala-lang.org/overviews/macros/quasiquotes.html](http://docs.scala-lang.org/overviews/macros/quasiquotes.html).

2) Macro paradise 2.10 is runtime binary compatible with vanilla Scala 2.10.x,
which means that macros, libraries and applications compiled with macro paradise 2.10
can be compiled against and linked against with vanilla Scala 2.10.x. If that's not the case,
please let me know at [eugene.burmako@epfl.ch](eugene.burmako@epfl.ch).

3) Quasiquotes from the full-fledged macro paradise require a number of additional reflection APIs to work,
but here in macro paradise 2.10 we are bound by binary compatibility restrictions. Therefore I had to externalize
extra dependencies by requiring a variable named `quasiquoteCompat` implementing the additional APIs to be present
in lexical scope most of the times you use quasiquotes. A sample (quite dirty!) implementation of `quasiquoteCompat`
is provided in [macros/src/main/scala/Compat.scala](macros/src/main/scala/Compat.scala).
