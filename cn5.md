% Hello C...TYI!
% Domhnall O'Hanlon
% March 7, 2017

\setcounter{page}{41}

# Functions

As you've no doubt seen during your maths studies, a function is something that takes one or more arguments (inputs) and produces some return (output). In C you can of course create lots of different types of functions, using any of the data types that the language supports, but for the purpose learning about functions some mathematical examples are quite useful.

## Creating Functions

So, what data type does a function have? Well, that depends on what type of data it returns. If you want to create a function that squares two numbers and returns the result then it will probably have an integer type. If you want to get the average or root of some numbers then it makes more sense to use a float. The process of creating a function is known as **declaring** a function. Typically, functions are declared just below any `#include` calls at the beginning of your code. This declaration tells the compiler not just what return type to expect but all the number and type of arguments the function accepts. This can also be refered to as the function **prototype**.  The code associated with how the function actually performs is known as the **definition** of the function. Let's create a simple function that squares an integer input:

``` C
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

### Square

see the first example for squaring number.

### Circle

``` C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define PI 3.141593

float circle();

float result;

int main() {
    
    circle();
    printf("The area is %.2f units squared.\n\n", result);
}

float circle(){
    float rad;
    printf("What is the radius of the circle?\n");
    scanf("%f", &rad);
    result = PI*rad*rad;
    return result;
}

```

\newpage
### Cube & Sphere

``` C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define PI 3.141593

float circle();
float cube();
float sphere();

float result;

int main() {
    
    cube();
    printf("The area is %.2f units squared.\n\n", result);
    
    sphere();
    printf("The area is %.2f units squared.\n\n", result);
}



float cube(){
    float side;
    printf("Enter the side length: \n");
    scanf("%f", &side);
    result = 6 * side * side;
    return result;
}


float sphere(){
    float rad;
    printf("What is the radius of the circle?\n");
    scanf("%f", &rad);
    result = 4*PI*rad*rad*rad;
    result = result/3;
    return result;
}

```


\newpage
## Summary

Having read this chapter, and completed all the programming exercises, you should now be comfortable with creating your own functions and calling them from anywhere in your main method.
