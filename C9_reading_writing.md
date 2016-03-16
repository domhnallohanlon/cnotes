# Reading & Writing to Disk

In this section we will look at reading and writing data to the operating system rather than just the console. By the end of this section you should be able to write a program in C that can create, read, update or delete a file stored on a users computer.

##Motivation

So far we've performed caluclation in memory, and displayed data in the console (command line), however, these actions are temporary and once the program has exited we can no longer see the output of our program. Indeed, once the computer is rebooted or shut down that almost all traces of that program are irrevocably gone. If our piece of software was supposed to store data for a social media app - or worse, our balance in a banking app -then this would be a complete disaster. 

This section will be a stepping stone to working with databases, but for the moment plain text and flat file will fulfil our needs.  

##Types of Files

###Sequential

### Random Access

## Modifying Files

To modify a give file you must have the appropriate permissions. Once you load a file into memory you need to specify which permissions your application should have 

r - read

Read only status allows you to view the contents of a document, however you can not change the existing content or add any new content to the document. 

w - write
Write permission allows you to change the entire contents of the document.

a - append
The append flag allows new data to be added to a document without overwriting or modifying any of the existing content. This is ideally suited to creating event logs or error logs which can be used to keep a record (log) of some specific activity.


use of the + 


###Opening a File

`fopen()` 
opens an existing file or creates one if you tell it to "w"


###Writing to a File
`fprintf()` 
print data to your file. 

###Reading from a File

###Closing a File
`fclose()`
close the files and frees up system memory once your finished writing to your file.

###Deleting a File