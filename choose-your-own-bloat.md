# A Choose-Your-Own-Bloat Adventure

## The Appeal Of C

Although we commonly associate the C programming language with resource-constrained environments such as operating system kernels and embedded systems, that's not
why I love working with the language.

For me, the appeal of C is everything that the standard library DOESN'T contain.

Languages that have great "out of the box" functionality can also make us lazy. Our first thought isn't "how do I implement this?" but rather "who has implemented
this already and how does their tool work?"

Of course, it is very handy for a business to have out-of-the-box solutions to common problems, because in business, developer time is money, and the same problems keep emerging in many different guises.

Its no mystery why Python, JavaScript and C# are so ubiquitous in industry. But for learning the mechanics of programming IN GENERAL, we have to take the opposite
approach and move closer to the hardware. Not further from it.

## Every Function That I Want To Use Is Problematic

A common experience for folks learning C is to google various keywords from the standard library, only to discover Stack Overflow answers warning the reader
specifically NOT to use them, due to their inherent security vulnerabilities or other shortcomings.

I'm sure that this has made many folk give up on C and switch to one with a larger toolkit for common tasks.

## Use non-standard libraries for user input

By far the biggest way to avoid pain with C, is to use a non-standard library for ANY program that requires user input in the terminal. That won't
eliminate all issues with the standard library, but it definitely helps.

Specifically, I am thinking of 'ncurses.h' for GNU/Linux (or Windows, via Cygwin) and 'conio.h' for Windows MSVC compiler.

## Assorted Weirdness

Array out of bounds? Say hello to [undefined behaviour](https://en.wikipedia.org/wiki/Undefined_behavior).

Code compiles okay? You might still get a [segfault](https://en.wikipedia.org/wiki/Segmentation_fault) when you run the binary.

Code compiles and runs? It might do what you intended, but then accuse you of [stack smashing](https://stackoverflow.com/questions/1345670/stack-smashing-detected#1347464) afterwards.

From a business standpoint, those are headaches that you simply don't need.

But from a "learning programming" standpoint, clearing the obstacles in your path will only make you a better programmer.

## Praying To Malloc

I addressed this issue in [another blog post](https://github.com/sammi-turner/Blog/blob/main/setting-forth-in-c.md). Its not rocket science.

Simply say a prayer to Malloc and that prayer will be answered with bytes.

But don't forget to give thanks to the RAM God with 'free' when you're done, or he will curse you with [memory leaks](https://www.youtube.com/watch?v=Fgb8l2Ve8vo).

## That C Function You Want Doesn't Exist

So why not write it yourself?
