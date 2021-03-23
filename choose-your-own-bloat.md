# A Choose-Your-Own-Bloat Adventure

## The Appeal Of C

Although we commonly associate the C programming language with resource-constrained environments such as operating system kernels and embedded systems, that's not
why I love working with the language.

For me, the appeal of C is everything that the standard library DOESN'T contain.

Languages that have great "out of the box" functionality can also make us lazy. Our first thought isn't "how do I implement this?" but rather "who has implemented
this already and how does their tool work?"

Of course, it is very handy for a business to have out-of-the-box solutions to common problems, because in business, developer time is money, and endless iterations
of the same problems keep coming up.

Its no mystery why Python, JavaScript and C# are so ubiquitous in industry. But for learning the mechanics of programming IN GENERAL, we have to take the opposite
approach and move closer to the hardware. Not further from it.

## Every Function That I Want To Use Is Problematic

A common experience for folks learning C is to google various keywords from the standard library, only to discover Stack Overflow answers warning the reader
specifically NOT to use them, due to their inherent security vulnerabilities or other shortcomings.

I'm sure that this has made many folk throw their hands up and say "pffft, I'll learn another language instead."

## Ncurses To The Rescue

By far the biggest way to avoid pain with C, is simply to use a curses library on nix for ANY program that requires user input from the terminal. That won't
eliminate all issues with the standard library, but it definitely helps!

## Assorted Weirdness

Array out of bounds? Say hello to [undefined behaviour](https://en.wikipedia.org/wiki/Undefined_behavior).

Code compiles okay? You might still get a [segfault](https://en.wikipedia.org/wiki/Segmentation_fault) when you run the binary.

From a business standpoint, these are headaches that you don't need.

But from a "learning programming" standpoint, clearing the obstacles in your path will only make you better!

## Praying To Malloc

I addressed this issue in [another blog post](https://github.com/sammi-turner/Blog/blob/main/setting-forth-in-c.md). Its not rocket science.

Want to return a pointer to an array from a function and you need to reserve some memory for that?

Simply say a prayer to 'malloc' and your prayer will be answered with bytes. Then don't forget to give thanks with 'free' to the RAM god when you're done.

## The C Function You Want Doesn't Exist

So why not write it yourself?



