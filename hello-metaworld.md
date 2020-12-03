# Hello, Metaworld!

A "Hello, World!" program generally is a computer program that outputs or displays the message "Hello, World!".

According to Wikipedia...

> Such a program is very simple in most programming languages, and is often used to illustrate the basic syntax of a programming language.

> It is often the first program written by people learning to code. It can also be used as a sanity test to make sure that a computer language is correctly installed, and that
the operator understands how to use it.

By contrast, a "Hello, Metaworld!" program, is a parent computer program that when run, produces a child program that yields the output "Hello, Metaworld!".

Here is an example of such a program, written in C++, using the LLVM compiler. Although substituting LLVM for a different C++ compiler should be trivial.

```
#include "sugar.hpp"

int main() {
  string line = "";
  string hello[5];

  hello[0] = "#include \"sugar.hpp\"";
  hello[1] = "";
  hello[2] = "int main() {";
  hello[3] = "  say \"Hello Metaworld\\n\";";
  hello[4] = "}";

  for (int i=0; i<5; i++) {
    line = hello[i] + "\n";
    fileAppend("meta.cpp", line);
  }

  system("clang++ meta.cpp -o meta && ./meta");
}
```

The 'say' and 'fileAppend' functions belong to the Sugar header file and are only there to simplify the code in 'main.cpp'. Both child and parent programs use this header.

The child program is embedded in the five line 'Hello' array.

We then loop through the array to append each line in turn, with a line break, to 'meta.cpp'. The 'meta.cpp' file is automatically created when line 0 is appended.

Note the escape characters on lines 0 and 3.

The double-quote becomes backslash-quote. The backslash-n becomes double-backslash-n. Without those, our child program won't work.

The penultimate line is a system call that first compiles 'meta.cpp' and then runs the binary created by it.

Isn't that just "Hello World" with extra steps?

At one level, yes it is.

But on another, it also shows us the germ of an idea.

The concept of a "program that writes programs".

> Meta-programming is a programming technique in which computer programs have the ability to treat other programs as their data. It means that a program can be designed to read,
generate, analyse or transform other programs, and even modify itself while running. In some cases, this allows programmers to minimise the number of lines of code to express a
solution, in turn reducing development time. It also allows programs greater flexibility to efficiently handle new situations without recompilation.

But why tho?

*shrug*

[Reasons](https://www.youtube.com/watch?v=SWU_DgjSwRU).
