# C++ guide
A guide to the programming language C++

# Table of Contents
<!--ts-->
   * [Introduction](#Introduction)
   * [Hello World](#Hello-World)
   * [Pointers](#Pointers)
   * [File I/O](#File-I/O)
<!--te-->

# Introduction
Why would we want to learn C++ when easier langauges like Python that do all the work for us exist? It's close to the hardware, so it gives much more control over things like memory management and optimization. Python is great for scientific coding where we don't really care about performance, but for actual programs (simulations, airplanes navigation systems, etc.), we'll want something that can be highly optimized.

Because it allows so much optimization, it's a very popular language that is in high demand. Anyone can pick up a lanugauge like Python in a few weeks. However, many won't put in the effort to learn C++. This tutorial is written for people with a basic understanding of code who want to learn C++.

Learning it will teach you what is really happening under the hood in programming languages. But you're not here to find out why you should learn it; you're here to actually learn it. Let's get started.

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

# Pointers

The major feature of C++ that isn't present in many other languages is the use of **pointers**. Pointers are just that; rather than containing an actual value, they are an address that *points* to an actual value. Consider the below example:

```
int i = 4;
int *j = &i;
```

Here, ```int i``` is an actual value, defined to be 4. ```int *j``` is not an actual value, but rather it is the address of i, which contains the actual value of 4. If you ```cout<<j;```, the compiler will print the address of i.

When we define a pointer, we use ```*```. It's easiest to read the definition ```int *j``` backwards: j is a pointer to an int. When we get more complex defintions later, this trick will be useful.

By defining a pointer, the right side of the equal sign must be an address. The ```&``` is shorthand in C++ for **address** (it can be used in other ways, but we'll ignore those for now). ```&``` can be placed in front of any variable to get its address. We can even do ```&j```, which will get us the address of j's content (which contains the address of i).

The key feature of pointers is that since it is an address, any changes made to the content of that address will affect the pointer's value itself. Suppose we change the above example to the following:

```
int i = 4;
int *j = &i;
i = 6;
```

Because j points to the address of i itself, it is equal to whatever i is equal to. If we change i to 6, j also now equals 6.

What if we wanted to see what the value of j is and not just its address? We'll have to do something called **dereferencing**. To make things confusing, the dereference operator is the same as the pointer definition operator: ```*```. In order to get the value of j, we'd have to do: ```cout<<*j;```.

Pointers seem complex at first, but as long as you remember these few simple rules, you should get a good grasp on them as you learn. 

# File I/O

Reading in files is something handled by the standard library. An open file is represented in C++ with by a *stream*. Any input/output operation performed on this stream is applied to the physical file associated with it. There are three types of streams in the standard library:
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

Most often, we'll use ```fstream``` for the convenience. However, if you want the most optimization, you should use ```ifstream``` and ```ofstream``` as needed. 

# Classes

Object oriented programming is a cornerstone of the c-family languages. C++ is no different. In this section we'll learn what an class is and how to make one.

A class is our own custom data type. We can control what kind of operations can be done to this data type.

# Data Structures

The main reason to use C++ is its control over data structures. For the next few sections of this tutorial, we'll focus on building some of those data structures.

# Linked Lists




