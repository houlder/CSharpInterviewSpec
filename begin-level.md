### What is the difference between static, public, and void?

Public declared variables can be accessed from anywhere in the application. Static declared variables can be accessed globally without needing to create an instance of the class. Void is a type modifier which states the method and is used to specify the return type of a method in C#.

### What is an object?

An object is a class instance that can be used to access class methods. The "New" keyword can be used to construct an object.

### Define Constructors.

A [constructor](https://www.simplilearn.com/tutorials/c-sharp-tutorial/c-sharp-constructor "constructor") is a member function with the same name as its class. The constructor is automatically invoked when an object is created. While the class is being initialized, it constructs all the values of data members.

### What are Jagged Arrays?

The Array which comprises elements of type array is called Jagged Array. The elements in Jagged Arrays can be of various dimensions and sizes.

### What is the difference between out and ref parameters?

When an argument is passed as a ref, it must be initialized before it can be passed to the method. An out parameter, on the other hand, need not to be initialized before passing to a method.

### What is the benefit of ‘using’ statement in C#?

The ‘using’ statement can be used in order to obtain a resource for processing before automatically disposing it when execution is completed.

### What is serialization?

In order to transport an object through a network, we would need to convert it into a stream of bytes. This process is called Serialization.

### Can “this” command be used within a static method?

No. This is because only static variables/methods can be used in a static method.

### Differentiate between Break and Continue Statement.

Continue statement - Used in jumping over a particular iteration and getting into the next iteration of the [loop.](https://www.simplilearn.com/tutorials/asp-dot-net-tutorial/for-each-loop "loop.")

Break statement - Used to skip the next statements of the current iteration and come out of the loop.

### List the different types of comments in C#.

The different types of comments in C# are:

-   XML comments

Example -

/// example of XML comment

-   Single Line comments

Example -

// example of single-line comment

-   Multi-line comments

Example -

/* example of an

multiline comment */

### Explain the four steps involved in the C# code compilation.

Four steps of code compilation in C# include -

-   Source code compilation in managed code.
-   Newly created code is clubbed with assembly code.
-   The Common Language Runtime (CLR) is loaded.
-   Assembly execution is done through CLR.

### Discuss the various methods to pass parameters in a method.

The various methods of passing parameters in a method include -

-   Output parameters: Lets the method return more than one value.
-   Value parameters: The formal value copies and stores the value of the actual argument, which enables the manipulation of the formal parameter without affecting the value of the actual parameter.
-   Reference parameters: The memory address of the actual parameter is stored in the formal argument, which means any change to the formal parameter would reflect on the actual argument too.

### Name all the C# access modifiers.

The C# access modifiers are -

-   Private Access Modifier - A private attribute or method is one that can only be accessed from within the class.
-   Public Access Modifier - When an attribute or method is declared public, it can be accessed from anywhere in the code.
-   Internal Access Modifier - When a property or method is defined as internal, it can only be accessible from the current assembly point of that class.
-   Protected Access Modifier - When a user declares a method or attribute as protected, it can only be accessed by members of that class and those who inherit it.
