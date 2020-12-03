# Write Libraries, Not Languages

## The Toylang Concept Is Flawed

I had originally set out to create a new programming language as both a technical challenge for myself and a possible "teaching language" for newcomers to programming.

My thought process was that beginners learning serious production languages would quickly come across code that they didn't understand online, and that this experience would work against their own confidence of having understood the basics.

But now, I think that the idea of a "toy language" which can easily be "mastered" is only half right.

Rather than try to create a walled garden of language simplicity for beginners, it would make more sense to create a library of simplicity and encourage beginners to master that library first.

Then, when they have a good grasp of the basics, they can expand their efforts to the much larger ecosystem of the underlying language.

The Uberlang Concept Is Also Flawed

If you are looking for powerful, general purpose programming languages which are as simple to write as Python, but which compile to native binaries that perform as well C or C++, then both Nim and Crystal fit the bill.

But my gut feeling is that as self-contained languages outside of the current mainstream, most programmers will never use either of them.

The time required to learn an entirely new language is too great if it locks us into a ghetto where there are no jobs, less open source code available to us, less documentation, fewer interoperable tools and a smaller online community.

For all of its downsides, I can Google (actually Start-Page for me) any elementary problem in C++ and quickly obtain sensible, relevant answers from a wide variety of sources.

Try the same exercise for Nim or Crystal and the lack of relevant results outside of official documentation is pretty tragic.

Sweetening C++ 

Since I have ruled out both the Toylang and the Uberlang paths as academic dead-ends without practical applications, it would make sense to pick the largest and most well established Swiss Army Knife in programming (C++) and set about making it noob friendly with the aid of a header file.

I have created a GitHub repo for that purpose. At the the last edit, it contains only 182 SLOC and a README file.

4 macros, 18 functions, 15 system headers and 13 using declarations.

The aim is not to provide any new functionality, but rather to make basic functionality in the terminal easy to understand, pleasing to the eye, and quick to type out for the beginner.

By "basic functionality", I mean doing the following.
Printing text to the screen.
Taking text input from the user.
Performing operations on variables.
Converting one data type to another.
Error handling.
Seeding and generating pseudo-random numbers.
Checking if a named file exists.
Writing to a named text file.
Appending a string to a text file.
Reading from a text file to a string.
Reading from a text file to a vector.
Writing from a vector to a text file.
Deleting a named file from the working directory.
Control flow.
Functions.
Why not Python?

Although Python has some great libraries and looks deceptively simple on the screen, it does have some major drawbacks that I wanted to avoid.
The white-space syntax is confusing. The concepts of scope and delimiters are very important in programming. Curly braces and semi-colons are great for making those concepts explicit.
The reference implementation of Python has no compile step. Personally, I'd much rather catch the syntax errors at compile time, so that at runtime, only the semantic errors are possible.
Although the benchmarks of Python are unlikely to cause issues with simple terminal apps, as soon as the need for optimisation arises, the switch to C, C++ or Rust becomes inevitable.
But is it memory safe?

Nothing in the Sugar header file or the basic functionality that I have mentioned involves the use of, let alone the misuse, of raw pointers. So Sugar itself is perfectly safe.

Programs using Sugar-Hpp

A very simple todos app.

A command line version of Yahtzee.
