# Bash Tester
Bash Scripts for locally running and debugging programs with constrained Time and Memory Limits for C/C++, Python, Java.

# Supported Platforms
Linux Distibutions

# Supported Languages
C++ (`g++` or `clang++`)
Python 2 (`python`)
Java (`jdk`)

# Functionality
*to build the source files*
`$ build main.cpp` - compiles the cpp file and generates the executable if no error is caught
`$ build main.py` - performs a syntax-check of the py file
`$ build Main.java` - compiles the java file and renders the bytecode in class file if no error is caught
`$ build file1 [file2 [file3...[fileN]...]]` - to build multiple files at once

*to execute the programs with time and memory usage statistics*
*and limit on memory usage (virtual limit for cpp and py, as jvm has its own memory management)*
`$ run main` - no extension assumes c++ application (elf format)
`$ run main.py` - interprets the python program
`$ run Main.class` - executes the java application

*to debug or stress-test program (written in C++/Python/Java)*
*the required programs - a main program, a checker program, and a random input generator (rig) program*
`$ debug main check.class rig.py`
`$ debug <main-program> <checker-program> <rig-program> [<number-of-inputs> [<time-limit-for-main>]]`
*tips for debug script*
1. square brackets denote optional arguments
2. the `main-program` can be heuristically tested (for out-of-bounds error, runtime exceptions and other errors) against the `rig-program` program by setting `main-program = checker-program`.
*testing java program against python rig for 1000 cases and 2s time limit (per case) for the main (java) program*
`$ debug Main.class Main.class rig.py 1000 2`

# Sample
The terminal shows error handling/compile error messages natively when using the scripts.
![alt text](https://github.com/sidhantnagpal/bash-tester/blob/master/sample/sample.png "Sample")

# Setup
1. Copy & Place the scripts (.sh) files in your bin folder (or a folder where you keep other scripts).
2. Open a terminal in the bin folder and execute the following commands, granting the scripts permission to execute:
```
$ chmod +x build
$ chmod +x run
$ chmod +x debug
```
3. To access the scripts from anywhere in the system, add the location in your $PATH or place/symlink them in ~/.local/bin/.

# License
MIT
