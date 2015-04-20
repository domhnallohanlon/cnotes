# Functions

As you've no doubt seen during your maths studies, a function is something that takes one or more arguments (inputs) and produces some return (output). In C you can of course create lots of different types of functions, using any of the data types that the language supports, but for the purpose learning about functions some mathematical examples are quite useful.

## Creating Functions

So, what data type does a function have? Well, that depends on what type of data it returns. If you want to create a function that squares two numbers and returns the result then it will probably have an integer type. If you want to get the average or root of some numbers then it makes more sense to use a float. The process of creating a function is known as **declaring** a function. Typically, functions are declared just below any `#include` calls at the beginning of your code. This declaration tells the compiler not just what return type to expect but all the number and type of arguments the function accepts. This can also be refered to as the function **prototype**.  The code associated with how the function actually performs is known as the **definition** of the function. Let's create a simple function that squares an integer input:

```
#include <stdio.h> 

 int num, result;
 int square(int i);

 int main(){
     
     printf("Please enter a number to square\n");
     scanf("%d", &num);

    result = square(num);
     printf("%d squared is %d \n",num, result );
     return 0;
 }

  int square(int i){
    return i*i;
}
```


## Maths

Create functions to calculate the area of a square, circle, cube and sphere.