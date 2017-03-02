# Raven Variable Naming

This file contains some common naming conventions that should be followd for all code running on the Raven. It is based off of Google's [naming guidelines](https://google.github.io/styleguide/cppguide.html#Naming).

## General Naming Rules

Names should be descriptive; avoid abbreviation.

Give as descriptive a name as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. Do not use abbreviations that are ambiguous or unfamiliar to readers outside your project, and do not abbreviate by deleting letters within a word.

## File Names

Filenames should be all lowercase and can include underscores (\_) or dashes (-).

Examples of acceptable file names:

    my_useful_class.cpp
    my-useful-class.pp
    myusefulclass.cpp
    myusefulclass_test.cpp

C++ files should end in .cpp and header files should end in .h.

In general, make your filenames very specific. For example, use http\_server_logs.h rather than logs.h. A very common case is to have a pair of files called, e.g., foo\_bar.h and foo_bar.cpp, defining a class called FooBar.

Inline functions must be in a .h file. If your inline functions are very short, they should go directly into your .h file.

## Type Names

Type names start with a capital letter and have a capital letter for each new word, with no underscores: MyExcitingClass, MyExcitingEnum.

The names of all types — classes, structs, type aliases, enums, and type template parameters — have the same naming convention. Type names should start with a capital letter and have a capital letter for each new word. No underscores. For example:

    // classes and structs
    class UrlTable { ...
    class UrlTableTester { ...
    struct UrlTableProperties { ...

    // typedefs
    typedef hash_map<UrlTableProperties *, string> PropertiesMap;

    // using aliases
    using PropertiesMap = hash_map<UrlTableProperties *, string>;

    // enums
    enum UrlTableErrors { ...

## Variable Names

The names of variables (including function parameters) and data members are all lowercase, with underscores between words. Data members of classes (but not structs) additionally have trailing underscores. For instance: a\_local\_variable, a\_struct\_data\_member, a\_class\_data\_member\_.

### Common Variable Names

    string table_name;  // OK - uses underscore.
    string tablename;   // OK - all lowercase.
    string tableName;   // Bad - mixed case.

### Class Data Members

Data members of classes, both static and non-static, are named like ordinary nonmember variables, but with a trailing underscore.

    class TableInfo {
      ...
     private:
      string table_name_;  // OK - underscore at end.
      string tablename_;   // OK.
          static Pool<TableInfo>* pool_;  // OK.
    };




