
# Part 1: Input > Process > Output

In this secion you will write your first C programs, and learn about the differnt bits and pieces that are required to compile and run software written in C. By the end of this section you should be able to

  * Write a simple, interactive, exectuable program.
  * Understand essential C syntax
  * Be aware of different data types in C



## Hello World!

"Hello World" is typically the first program that students learn to write, regardless of what language they're learning. It's origins are as old <a href="http://en.wikipedia.org/wiki/%22Hello,_World!%22_program#History" target="_blank">as C itself</a> so let's follow in the footsteps of all the great programmers and write it for ourselves. 

``` 
    #include <stdio.h>

    int main(){
      printf("Hello World");

      return 0;
    }

```

<!-- \newpage -->

## Analysis

The first line of our Hello World programs has `#include <stdio.h>` which **includes** commands for inputting and outputting data. We will cover these functions in greater detail in the [libraries](#!C4_libraries.md) section.
The next line `int main()` creates a function called main that returns a whole number (integer) when it finishes. Again, we will also cover functions in [much greater detail](#!C12_functions.md) but for now it is sufficient to know that every program that you write must contain a `main()` function. The contents of any function are placed between braces (sometimes called curly braces) like these `{ }`. In the Hello World example, out main function only does two things; firstly it prints the message *Hello World* and then it exits successfully by returning 0. Each of these steps that the program takes is called a **statement**. Note that every statement you write in C (and many other langauges) will always end with a semicolon. 
For a more humorous take on semicolons see the following guide:
<a href="http://theoatmeal.com/comics/semicolon" target="_blank">
<img src="images/semicolon.png" alt="Oatmeal's Guide to Semicolons">
</a>  

## Comments

Obviously, as the weeks go on we'll be cerating more and more sophisticated programs, and we'll also be collaborating with other programmers. In both of these instances it is useful to have have some human-readable text that gives some clue as to what the program or function we are looking at is supposed to do. C has comments for this very purpose. There are two types of comments:

Single line comments that are indicated with two forward slashes `//`

``` 
    //this is a single line comment.

```

Multi line comments, which can span one or more lines. A multi line comment begins with `/*` and ends with `*/`. 

``` 
    /*
    This is a 
    multiline
    comment
    */
```

Originally C only supported multi line comments and support for single line comemnts was introduced after the release of the C++ language. For full backwards compatibility with older compilers it is recommended that you always use multiline comments.
<!-- \newpage -->

## Escape Characters

What if you wanted print the words *Hello* and *World* on seperate lines? How would you insert a line break into your text? In the example above, the text you want to display is contained between double quotes, but what if you wanted to display some dialog, like, *Domhnall said "hello world"*, how do you display double quotes without inadvertently closing one string and opening another by accident? Try it if you like.

The solution is to use **escape characters**. This means the symbol you want to display, or keyboard character you want to enter,  is escaped by placing a backslash, `\`,  in front of it. Try the following example

``` 

    #include <stdio.h>
    #include <stdlib.h>

    int main(){
      printf("Alice said \"Hello World\" \n Bob said \"Hello World\" too.");

      return 0;
    }

```

The `printf()` function will print out every character it sees inbetween the open and closing double quotes. In the example above, to display quotes in the console you have to escape them by preceding the quotes with a backslash. 
You also have to explicitly tell the complier when you want to go on to a new line, and this is acheived using the new line escape character, `\n`. A complete list of escape characters is included in the table below.  

sequence| output
------|-------------------
`\a`  |  Alarm (Beep, Bell)
`\b`  |  Backspace
`\f`  |  Formfeed
`\n`  |  Newline (Line Feed);
`\r`  |  Carriage Return
`\t`  |  Horizontal Tab
`\v`  |  Vertical Tab
`\\`  |  Backslash
`\'`  |  Single quotation mark
`\"`  |  Double quotation mark
`\?`  |  Question mark
`\nnn` |  A character where nnn interpreted as an octal number
`\xhh` | The character where hh interpreted as a hexadecimal number

<!-- \newpage --> 

## Variables

A variable is simply a placeholder where we are going to store some information in the computer's memory. There are three things you need to do to create a variable in your program. First you need to tell the compiler what **type** of data you'll be working with - i.e. is it a number or letters etc. Then you need to name your variable, in other words **declare** it, so that you can refer to it elsewhere in your code. Finally you need to give your variable a value, or **initialise** it, somewhere in your code, otherwise you will get an *unused variable* error message from the compiler. 

## Types of Variables

### Integer Types

Integer data types are for storing whole numbers. There are signed and unsigned variants of these, where the allocated size is the same but the range oof possible values is changed. 

Variable Name   | C Identifier  | Size    | Range
----------------|---------------|---------|--------
Character       | char          | 8 bit   | 0 - 255
Integer         | int           | 16 bit  | pm 32,000
Short           | short         | 16 bit  | pm 32,000
Long            | long          | 32 bit  | pm 2 billion


### Floating Point Types

Floating point data types allow increasing levels of presicsion for calculations by providing more and more decimal places. For most engineering applications 15 decimal places will usually suffice.

Variable Name   | C Identifier  | Size    | Precision
----------------|---------------|---------|--------
Float           | float         | 32 bit  | 6 decimal places
Double          | double        | 64 bit  | 15 decimal places
Long            | long          | 80 bit  | 19 decimal places

## Conversion Characters

Many functions, such as `printf()`, will allow us to substitute in varaibles rather than having to hard code in variables. Take the following example:

```
#include <stdio.h>

int main(){
  int myInt = 42;

  printf("Your integer is %d", myInt);

  return 0;
}
```

The `printf()` function is now getting two pieces of information, seperated by commas. The first piece of information is a string or message to display and the second piece of information is the name of the variable we want to display. 
At the end of the string there is a new sequence of characters `%d`. This tells the compilers to go and find a varaible and substitute in its value in place of the `%d`. The `myInt` parameter tells the compiler which variable that should be. There are different **conversion characters** depending on which type of data you want to substitute into your function. The following table contains a complete list.

Character   | Argument to Display
------------|------------
   `%c`     | Single character (char)
   `%d`     | Signed decimal integer (int)
   `%e`     | Signed floating-point value in E notation
   `%f`     | Signed floating-point value (float)
   `%g`     | Signed value in %e or %f format, whichever is shorter
   `%i`     | Signed decimal integer (int)
   `%o`     | Unsigned octal (base 8) integer (int)
   `%s`     | String of text
   `%u`     | Unsigned decimal integer (int)
   `%x`     | Unsigned hexadecimal (base 16) integer (int)
   `%%`     | (percent character)

## Examples

In the first example we see how you can output a specific number of digits from the float pi. By default a float will display six decimal places but you and add values to the conversion character to change this. `.5` means that five decimal places should be printed, `.4` means display four decimal places, `.3` measn 3 and so on. Take a look at the following example:

``` 
  int main(){
    printf("I ate some %f", 3.141592);
    printf("I ate some %.4f", 3.141592);
    printf("I ate some %.2f", 3.141592);

    return 0;
  }
```

In the example above there is a (deliberate) rounding error. The first 8 digits of Pi are 3.1415926 so we should have rounded our float up to 3.141593. In order to rectify this mistake we have to make three changes - but in larger programs a small change in specification might require you to make hundreds or thousands of changes. This is another example of where variables are extememly useful. The following code snippet has improved the previous example by including variables:

``` 
  int main(){

    //declare a floating point variable and name it "pi"
    float pi;

    //initialise pi by assigning it a value of 3.141593
    pi = 3.141593;

    printf("I ate some %f", pi);
    printf("I ate some %.4f", pi);
    printf("I ate some %.2f", pi);

    return 0;
  }
```
Now, if we have to make any change to our program we simply have to change the varible once and all the functions that rely on it will get the updated value.
To make your life easier you can also **declare** and **initialise** a variable in one line like so:

``` 
  float pi = 3.141593;
```

## Arrays

We'll explore arrays in more detail in <a href="#!C10_arrays.md">chapter 4</a> so this is just a quick introduction. As you may know already, an array is simply a collection of data. The only syntactic difference between a primative data type and an array is an extra set of square brackets e.g.`int integerArray[];` Each new element of an array is seperated by a comma. For example, you might use an array to store your lotto numbers: `int luckyNums[] = {4,8,15,16,23,42};`

### Indexing

What is we want to know,for example, what the third element of an array is? Well, we can look it up using it's **index**. Just like with a book, an index is used to look up information you want to find. Now intuitively you might think that the third element of an array would be found at index 3 - however C, like that vast majority of programming languages, start indexing arrays at 0. This means the the first elements is at index 0, the second is at index 1 and so on. So to print our third lottery number to the console we could write:

``` 
  printf("%d", luckyNums[i]);
```


## Input!!

<!-- number 5 is alive?
 -->
So far we've been manipulating predefined data - this is all well and good but it doesn't make for particularly interactive programs. In this section we will look at the `scanf()` function, which is used for reading (or scanning!) in data from the console.


### scanf() syntax

Both `scanf()` and `printf()` are part of the `<stdio.h>` header, so hopefully they will look quite similar to you. As we saw before, when printing data we needed to tell the function both the **type** of data we are working with and a **value** for that data to have. Take a look at the following simple example:

```
 int myInt;

 scanf("%d", &myInt);
```



If you build and run the previous example you will just see a console with a blinking cursor - not particularly intuitive for the end user. 

```
 int age;

 printf("What year were you born in ? \n");
 scanf("%d", &age);

```

<!-- \newpage -->

### Challenge

Improve the snippet above so that it asks the user for their year of birth and tells them their (approximate!) age.

<!-- **stretch goal** use system time and users D.o.B to get exact age, or to create a birthday countdown. -->


## Downloads

<a href="https://domhnallohanlon.github.io/cnotes/01_input_process_output.pdf" class="btn btn-primary">Download Notes as PDF</a>