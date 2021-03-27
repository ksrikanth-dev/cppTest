Structure and Union:
********************
- A structure in C/C++ is a user defined data type that allows us to group together the data items of heterogenous type.
Example: We can create a structure named Student to hold the data of a student like name, roll no, subjects, marks, grade, phone number etc.

- A union is a special data type that allows storing different data types in the same memory location.
We can define a union with many members, but only one member can contain a value at any given time. Unions provide an efficient way of using the same memory location for multiple purposes. 
In short, we can say - union allows us to create a versatile variable, which can hold data of any of it's member's type at any given time.

![image](https://user-images.githubusercontent.com/47342068/112730725-245f0380-8f59-11eb-88af-43e89d4a8d95.png)

Storage classes:
****************
- A storage class defines the scope (visibility) and life-time of variables and/or functions within a C++ Program. These specifiers precede the type that they modify.Here are the storage classes available in C++:
    auto
    static
    extern
    register
    mutable

auto ->
    - This is the default storage class for all local variables.
    - auto variables would have garbage value if not initialized explicitely.

static ->
    - static variables are created in the beginning of program execution and 
    live till program termination. So, static variables are created once and destroyed once unlike local variables that are created and destroyed on each invocation of the function in which the local variables are defined.
    - The static modifier may also be applied to 
    global variables/functions. When this is done, it causes that variable's/function's scope to be restricted to the file in which it is declared.
    - In C++, when static is used on a class data member, it causes only one copy of that member to be shared by all objects of its class.
    - Static variables are initialized with 0 by default

extern ->
    - When we have multiple files and we defined a global variable or function (in one of the files), which will be used in other files also, then extern will be used in another file to give reference of defined variable or function. Just for understanding extern is used inform the compiler that the variable/function is declared somewhere else(not in the currect file where it's declared as extern).
    - The extern storage class is used to give a reference of a global variable/function that is visible to ALL the program files.
    - Compiler, during the linking phase, will identify and link the candidate variable or function if present in any of the files provided during compilation. If the externalized variable or function is not found, linking will fai.
    - When we use 'extern', the variable cannot be initialized as all it does is point the variable name at a storage location that has been previously defined.
    - The extern modifier is most commonly used when there are two or more files sharing the same global variables or functions.

register ->
    - The register storage class is used to define local variables that should be stored in a register instead of RAM. This means that the variable has a maximum size equal to the register size (usually one word) and can't have the unary '&' operator applied to it (as it does not have a memory location).
    {
        register int  miles;
    }
    - The register should only be used for variables that require quick access such as counters. It should also be noted that defining 'register' does not mean that the variable will be stored in a register. It means that it MIGHT be stored in a register depending on hardware and implementation restrictions.

mutable ->
    - The mutable specifier applies only to class data members.
    - Sometimes there is a requirement to modify one or more data members of class/struct through const function even though we don’t want the function to update other members of class/struct. This task can be easily performed by using the mutable keyword. The keyword mutable is mainly used to allow a particular data member of const object to be modified. When we declare a function as const, `this` pointer passed to function becomes const. Adding mutable to a variable allows a const pointer to change members.
    - That is, a mutable member can be modified by a const member function/through a const object.

