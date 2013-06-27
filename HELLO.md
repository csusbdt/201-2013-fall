# Hello Program

## Overview

This document explains how to write, compile and run a simple C++ console program
from the Linux command line.
When the program runs, it prints _hello_.

## Instructions

Create a file named hello.cpp with the following contents.

````
#include <iostream>

using namespace std;

int main(int argc, char * args[])
{
    cout << "Hello.\n";
}
````

From a terminal window, run the following command to compile _hello.cpp_.

    c++ hello.cpp

The above command generates an executable file named _a.out_.
To run this file, issue the following from the command line.

    ./a.out

