## The Heap

You can allocate extra memory using the heap during run-time and free it up again once you're finished using it.

`malloc()`


once you're finished with the memory from the heap you should free it up again so that the system can use it again.
`free()`

### Example Application

A program that accepts an arbitrary number of inputs and returns the average of these numbers. 

- won't have to know the array size in advance.
- make use of the heap as and when required.