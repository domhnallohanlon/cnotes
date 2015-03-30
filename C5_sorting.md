% Searching and Sorting
% Domhnall O'Hanlon
% 24th March 2015

## Sorting

### Bubble Sort

```
    #include <stdio.h>
    #include <stdlib.h>
    #include <ctype.h>
    #include <string.h>
    #include <math.h>

    int main(){
        int i, temp, sorted;
        int howMany = 10;
        int goals[howMany];

        printf("Original List: \n");
        for(i =0; i<howMany; i++){
            printf("%d \n", goals[i]);
        }

        while(1){

            sorted = 0;

            for(i =0; i<howMany-1; i++){
                if(goals[i] > goals[i+1]){
                    temp = goals[i];
                    goals[i] = goals[i+1];
                    goals[i+1] = temp;
                    sorted = 0;
                }
            }

            if(sorted == 0){
                break;
            }
        }

        printf("\n Sorted List: \n");

        for(i = 0; i<howMany; i++){
            printf("%d \n", goals[i]);
        }

        return 0;
        
    }


### Quick Sort