# C++ guide
A guide to the programming language C++

# Table of Contents
<!--ts-->
   * [Introduction](#Introduction)
   * [Hello World](#Hello-World)
<!--te-->

# Introduction
Why would we want to learn C++ when easier langauges like Python that do all the work for us exist? It's close to the hardware, so it gives much more control over things like memory management and optimization. Python is great for scientific coding where we don't really care about performance, but for actual programs (simulations, airplanes navigation systems, etc.), we'll want something that can be highly optimized.

Because it allows so much optimization, it's a very popular language that is in high demand. Anyone can pick up a lanugauge like Python in a few weeks. However, many won't put in the effort to learn C++. 

Learning it will teach you what is really happening under the hood in programming languages. But you're not here to find out why you should learn it; you're here to actually learn it. 

The best way I to learn I feel is to do real applications. In this tutorial, we'll be building data structures, reading in files, and building actual applications. Each section will be about building a program. I'll explain that steps we take in each section.

# Hello World
Many things beyond what is provided in the standard C language must be imported in C++. To print out a simple "Hello world", we're going to have to import ```<iostream>```, which will allow us to use a printing command called ```cout```. The following is a finished version:
```
#include <iostream>
using namespace std;

int main() {
    cout<<"Hello World";
    return 0;
}
```

All our C++ classes must have ```int main()```. If you know any other language, you're familiar with the concept of having a main method as an entry point. In C++, this method always has ```int``` return type. Often, we return 0 since this int return value isn't what our program is focused on.

## Standard libraries

C++ has three distinct sets of tools available: 
1. The core lanuage, which contains variables and data types
2. The standard library (```std``` from above), which contains a set of functions for manipulating strings and files
3. The standard template library, which contains a ton of functions for manipulating data structures

The core language is C++ itself. The other two must be imported using ```#include```. In the rest of our programs, we'll use a mix of all three.

# Reading in files

Reading in files is something handled by the standard library. In this section, we'll make a program to read in a CSV file (spreadsheet, a.k.a. Comma Separated Value file), which we will then convert to a vector where the data can be easily manipulated

First, we'll need to import some of the standard library. An open file is represented in C++ with by a *stream*. Any input/output operation performed on this stream is applied to the physical file associated with it. There are three types of streams in the standard library:
1. ```ifstream```: A stream to read in files
2. ```ofstream```: A stream to write to files
3. ```fstream```: A stream to both read in and write to files

Files can be manipulated using streams the same way we use ```cin``` and ```cout```. The only difference is we have to open and close the file, so our changes are applied to it. To open a basic file and write something to it, we'd do the following:

```
#include <iostream>
#include <fstream>
using namespace std;

int main(){
  fstream myFile;
  myFile.open("example.txt");
  myFile<<"Text to be written";
  myFile.close();
  return 0;
}
```

Most often, we'll use ```fstream``` for the convenience. However, if you want the most optimization, you should use ```ifstream``` and ```ofstream``` as needed. For this program, we'll use ```fstream```.
