% Libraries
% Domhnall O'Hanlon
% 10th March 2015

# Part 4: Libraries (.h files)

## Preprocessor Directives

Up until now we haven't really paid any great attention to the `#include` code at the beginning of our programs. The `.h` files that are included are known as header files or preprocessor directives. This is because the contents of these files are called *before* the main.c is compiled.


### Writing a simple header.

Lets create a header with some commonly used mathematical constants

```
 DEFINE PI = 3.141593
 DEFINE EULER = 1.6
```

If you're using an IDE you'll see that this new .h file is saved in a new folder called "headers". Typically your compiler will expect your headers to be in a predefined location ------ and this is implied in the code by using brackets `#include <someHeader.h>` however, our hearder is stored in the same directory as our source code so acccess it we use quotation marks instead:
`#include "myHeader.h"`


## stdio.h

We've been using the C **st**andar**d** **i**nput **o**utput library for a while now, so let's take a closer look at what it contains and some of the other functions it gives us access too.  

### Working with `char`

There are two functions that allow you to read and write single characters in the console. 

```

getchar()

putchar()


```

### ASCII Table

[Ascii Table](#!table2.md)
<a href="table.html" target="_blank">Searchable Table</a>

puts()
gets()

## stdlib.h

## ctype.h

probably contains these:
isalpha()
isdigit()
...probably!

isupper()
islower() //check for upper or lower case

toupper()
tolower() //text transforms

### Password validator

use the functions to check if p/w contains upper case letter, lower case letter and "special" character



## string.h

**Concatenation**
strcat(arg1, arg2),

    arg1: string that you want to extend
    arg2: string that you want to add onto arg1.

## math.h


floor()
ceil() //not seal() - make this function!

returns an absolute value
what the difference between modulus (little measure) and modulo?
abs()

pow(n, exponent) //a la old school batman


returns the square root of n
sqrt(n)

### -b formula.

use these maths functions to solve for the roots of a qudratic equation.


generate a random number. 
rand()

### Lotto Number picker

luckyNums = (rand()%42) + 1 //same as dice game.

### Dice game

roll = (rand()%6) + 1 //returns 0-5 and adds one to it.

print out ASCII dice.


### Price is Right

higher or lower?