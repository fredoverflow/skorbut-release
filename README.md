![skorbut logo](https://i.imgur.com/J9j9MNs.png)

![first example](https://i.imgur.com/PlMxIbC.png)

## What is skorbut?

skorbut is a simple teaching environment for a subset of C with a memory visualizer.
If you ever had trouble visualizing arrays and pointers, you have come to the right place.

## Does the name mean anything?

*skorbut* is German for *scurvy*, an illness that is caused by a lack of Vitamin C.
skorbut also lacks C in the sense that it implements only a restricted subset of C.

## Where do I download skorbut?

Click [this download link](https://github.com/fredoverflow/skorbut-release/raw/master/skorbut.jar).
If for some reason this doesn't work, click `skorbut.jar` in the list above, then `Download`.

## How do I start skorbut?

skorbut requires Java version 8 or later: https://adoptopenjdk.net

On Windows, you can simply run a jar by double-clicking on it.

On other operating systems, open a terminal where the jar lives and write:

    java -jar skorbut.jar

## How do I save my code?

The code is automatically saved to a new file each time you click the start button.
The save folder is named `skorbut`, and it is located in your home directory.
The full path is displayed in the title bar.

## Does skorbut support auto-indentation?

Yes, just hit Enter or Tab.

## What about auto-completion?

Ctrl+Space after an identifier auto-completes to the longest common prefix of all identifiers in scope.
For example, if `foo`, `bar` and `baz` are in scope, then `f` will be auto-completed to `foo`,
but `b` will only be auto-completed to `ba`, because both `bar` and `baz` start with `ba`.

skorbut has scope-aware auto-completion for all identifiers *except* `struct` members;
those are auto-completed globally, i.e. after `.` or `->`, *all* `struct` members are considered for auto-completion.
(That's because auto-completion has no type information available yet. Changing this would be a Herculean task.)

## What features of C are currently missing?

Non-exhaustive list off the top of my head:

| Feature             | Priority |
| ------------------- | -------- |
| preprocessor        | very low |
| variadic functions  | very low |
| compound assignment | low      |
| null pointer        | medium   |
| union               | very low |
| return struct       | low      |

## Wait, no preprocessor? How do I `#include <stdio.h>`?

You don't need to include anything, the following standard library functions are already available:

- printf
- scanf
- puts
- putchar
- getchar
- malloc
- free
- realloc
- qsort
- bsearch
- time

## What about my own header files?

skorbut does not support multiple translation units, so there would be no point in supporting header files.

## How do I define constants without `#define`?

For integral constants, you can use anonymous enumerations like `enum { N = 10 };`

## Is skorbut open source?

Not yet, but I will probably open-source skorbut when I lose interest in further development. Don't hold your breath though ;)
