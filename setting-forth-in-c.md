# Setting Forth In C

## Malloc and freeeeeee

```
Be it no concern  
Point of no return  
Go forward in reverse
This I will recall
Everytime I fall
I'm free
Setting forth in the universe
Oh I'm free
Setting forth in the universe
Out here realigned
A planet out of sight
Nature drunk and high
Oh I'm free
I'm free...
```

As you can see from those lyrics, dynamic memory allocation in C strongly reminds me of an [Eddie Vedder song](https://www.youtube.com/watch?v=KDlsH8MbDbs).

## Newcomers to C, aren't usually new to programming

Which creates a problem for those newcomers as they have become accustomed to the run-time environment of their old language handling a lot of work for them.

Yeah, C doesn't do that.

Those languages also have features like "string" or "vector" data types, which C does not possess out-of-the-box.

The standard library of C is also rather sparse, and the APIs provided are platform-specific to Windows, MacOS, GNU/Linux, etc.

## Why does C handle memory differently than most other languages?

C was creaated in a time when hardware constraints were a much more pressing concern than they are now (December 2020).

But even today, C is widely used in resource-constrained environments like device drivers, embedded systems and operating system kernels.

C is also still popular in the GNU/Linux desktop userland, which has a culture of writing applications that are not resource-heavy.

## What the heck is a pointer anyway?

Sadly, the more general and abstract the discussion gets with regard to pointers, the more confused the student is likely to get.

So you won't find any abstract diagrams of integers sitting in pigeon holes with arrows pointing in all directions in this blog post.

Instead, I will present the following program as an appetiser.

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char *getVedder() {
  char *eddieVedder;
  eddieVedder = malloc(sizeof(char) * 50);
  strcpy(eddieVedder, "I'm freeeee!\nSetting forth in the universe...");
  return eddieVedder;
}

int main() {
  char *chorus;
  chorus = getVedder();
  printf("%s\n\n%s\n\n", chorus, chorus);
  free(chorus);
  system("pause"); /* Windows Only */
}
```

## Why are there so many damn asterisks in there?

1. The line marked "Windows Only" is used when double clicking on Windows executables and should be deleted before compilation on Linux and MacOS machines. In common with many other programming languages, C uses the asterisk symbol in its comment delimiters.

2. Nearly all programming languages use a single asterisk to denote multiplication, and so does this code snippet, on the second line of the '*getVedder()' function body.

3. The signature line of the 'getVedder()' function, the declaration of 'eddieVedder', and the declaration of 'chorus' have an asterisk in front of them. This denotes that the function returns [a pointer](https://en.wikipedia.org/wiki/Pointer_(computer_programming)) to a char, rather than a plain old single value. But be warned that putting an asterisk after 'char' or between 'char' and the identifier has the same meaning in C. So expect to see that notation elsewhere!

## What is the output of that program?

After successful compilation, running the executable makes your terminal emulator sing the chorus from "Setting Forth".

Of course, we could do that with a simple 'printf' statement in the main function. But that wouldn't help us explain dynamic memory allocation, would it?

So instead, we shall pass a pointer to a char array as a parameter, to our 'getVedder()' function.

## What does getVedder() do?

1. Declares a pointer to a local "eddieVedder" array.
2. Reserves a chunk of memory for the array using "malloc".
3. Copies our hard-coded lyrics to the array.
4. Returns the array.

## What does the main function do?

1. Declares a pointer to a "chorus" array.
2. Sets chorus equal to the result of calling "getVedder()".
3. Prints a format string where percent-s is a placeholder for "chorus" and slash-n denotes a line break.
4. Frees up the memory borrowed earlier using malloc.
5. On Windows, execution of the program is paused, and the user is prompted to "press any key".

## Okay, that was fun. What now?

* Read books on C. Including [K & R](https://en.wikipedia.org/wiki/The_C_Programming_Language). Second hand copies or PDF downloads are by far the most affordable options.
* Screw Udemy. You don't need them.
* Feed cryptic error messages into your search engine of choice.
* Feed your general questions about C into your search engine of choice.
* Write non-trivial programs in C.
* Experiment. Enjoy yourself.
* Read the follow up to this post....
