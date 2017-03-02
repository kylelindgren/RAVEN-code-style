# Raven Variable Naming

This file contains some common naming conventions that should be followd for all code running on the Raven. It is based off of Google's [naming guidelines](https://google.github.io/styleguide/cppguide.html#Naming).

## General Naming Rules

Names should be descriptive; avoid abbreviation.

Give as descriptive a name as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. Do not use abbreviations that are ambiguous or unfamiliar to readers outside your project, and do not abbreviate by deleting letters within a word.

## File Names

Filenames should be all lowercase and can include underscores (\_) or dashes (-).

Examples of acceptable file names:

    my\_useful_class.cpp
    my-useful-class.pp
    myusefulclass.cpp
    myusefulclass_test.cpp

C++ files should end in .cpp and header files should end in .h.

In general, make your filenames very specific. For example, use http\_server_logs.h rather than logs.h. A very common case is to have a pair of files called, e.g., foo\_bar.h and foo_bar.cpp, defining a class called FooBar.

Inline functions must be in a .h file. If your inline functions are very short, they should go directly into your .h file.


