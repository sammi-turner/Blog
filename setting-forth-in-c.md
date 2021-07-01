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

C was created in a time when hardware constraints were a much more pressing concern than they are now (July 2021).

But even today, C is widely used in resource-constrained environments like device drivers, embedded systems and operating system kernels.

C is also still popular in the desktop userland of open source unix-like operating systems, which have a culture of writing applications that are not resource-heavy.

## What the heck is a pointer anyway?

Sadly, the more general and abstract the discussion gets with regard to pointers, the more confused the student is likely to get.

So you won't find any abstract diagrams of integers sitting in pigeon holes with arrows pointing in all directions in this blog post.

Instead, I will present the following program as an appetiser.

Note that the underscore symbol on line 7 should be left out if you are not using the Windows MSVC compiler.

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char* getVedder() {
    char* eddieVedder = malloc(50);
    eddieVedder = _strdup("I'm freeeee!\nSetting forth in the universe...");
    return eddieVedder;
}

int main() {
    char* chorus = getVedder();
    printf("\n%s\n\n%s\n\n", chorus, chorus);
    free(chorus);
}
```

## Why are there so many asterisks in that snippet?

1. Nearly all programming languages use a single asterisk to denote multiplication, and so does this code snippet, on the second line of the 'getVedder()' function body.

2. In the snippet, you will also see asterisks after the data type 'char'. This denotes that the function returns [a pointer](https://en.wikipedia.org/wiki/Pointer_(computer_programming)) to a char, rather than a single char. But be warned that putting an asterisk before the identifier or between 'char' and the identifier also has the same meaning in C. So expect to see those notations elsewhere!

## What is the output of that program?

After successful compilation, running the executable makes your terminal emulator sing the chorus from "Setting Forth".

Of course, we could do that with a simple 'printf' statement in the main function. But that wouldn't help us explain dynamic memory allocation, would it?

So instead, we make our 'getVedder()' function borrow some bytes from the operating system with 'malloc', and then call 'free()' when we no longer need them.

## What does getVedder() do?

1. Reserves 50 bytes of memory for the 'eddieVedder' array using 'malloc'.
2. Copies our hard-coded lyrics to the array.
3. Returns a pointer to the array.

## What does the main function do?

1. Sets chorus equal to the result of calling 'getVedder()'.
2. Prints a format string where percent-s is a placeholder for 'chorus' and slash-n denotes a line break.
3. Frees up the memory borrowed earlier using malloc.

## Okay, that was cool. What now?

- If you are using Windows, then play with the code in my [C89 boilerplate repo](https://github.com/sammi-turner/Windows-C89-Boilerplate).
- If you are using a unix-like desktop operating system, then the [man pages](https://en.wikipedia.org/wiki/Man_page) should help you out.
- Check out C programming YouTubers like [Jacob Sorber](https://www.youtube.com/watch?v=liWdn92SAvs)
- Write non-trivial applications in C.

## Have fun!
