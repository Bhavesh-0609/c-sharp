# C#
C# documentation

## Basics

>So in this section, you learned the basics of C#.
>
>C# vs .NET
>
>C# is a programming language, while .NET is a framework. It consists of a run-time environment (CLR) and a class library that we use for building applications.
>
>CLR
>
>When you compile an application, C# compiler compiles your code to IL (Intermediate Language) code. IL code is platform agnostics, which makes it possible to a take a C# program on a different computer with different hardware architecture and operating system and run it. For this to happen, we need CLR. When you run a C# application, CLR compiles the IL code into the native machine code for the computer on which it is running. This process is called Just-in-time Compilation (JIT).
>
>Architecture of .NET Applications
>
>In terms of architecture, an application written with C# consists of building blocks called classes. A class is a container for data (attributes) and methods (functions). Attributes represent the state of the application. Methods include code. They have logic. That's where we implement our algorithms and write code.
>
>A namespace is a container for related classes. So as your application grows in size, you may want to group the related classes into various namespaces for better maintainability.
>
>As the number of classes and namespaces even grow further, you may want to physically separate related namespaces into separate assemblies. An assembly is a file (DLL or EXE) that contains one or more namespaces and classes. An EXE file represents a program that can be executed. A DLL is a file that includes code that can be re-used across different programs.
>
>In the next section, you'll learn about basics of the C# language, including variables, constants, type conversion and operators.

# <br>Primitive Types and Expressions
## Variable types , formate string and constant in code
```
using System;
namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            /* byte number = 2;
            int count = 10;
            float totalPrice = 20.95f;
            char character = 'A';
            string firstName = "Mosh";
            bool isWorking = true; */

            //You can also declare variables with var
            /*var number = 2;
            var count = 10;
            var totalPrice = 20.95f;
            var character = 'A';
            var firstName = "Mosh";
            var isWorking = true;

            Console.WriteLine(number);
            Console.WriteLine(count);
            Console.WriteLine(totalPrice);
            Console.WriteLine(character);
            Console.WriteLine(firstName);
            Console.WriteLine(isWorking);*/

            // fromate strings
            /*Console.WriteLine("{0} {1}", byte.MinValue, byte.MaxValue); ;
            Console.WriteLine("{0} {1}", float.MinValue, float.MaxValue);*/

            // constant
            const float PI = 3.14f;
            // PI = 1; // you can not change the value of const variable it will give error
        }
    }
}
```

## Type conversion theory

>In C#, there are two types of casting:
>
>Implicit Casting (automatically) - converting a smaller type to a larger type size<br>
>char -> int -> long -> float -> double <br>
>Explicit Casting (manually) - converting a larger type to a smaller size type<br>
>double -> float -> long -> int -> char <br>
>
>### Implicit Casting<br>
>Implicit casting is done automatically when passing a smaller size type to a larger size type:
```
int myInt = 9;
double myDouble = myInt;       // Automatic casting: int to double

Console.WriteLine(myInt);      // Outputs 9
Console.WriteLine(myDouble);   // Outputs 9
```

>### Explicit Casting<br>
>Explicit casting must be done manually by placing the type in parentheses in front of the value:
```
double myDouble = 9.78;
int myInt = (int) myDouble;    // Manual casting: double to int

Console.WriteLine(myDouble);   // Outputs 9.78
Console.WriteLine(myInt);      // Outputs 9
```
>### Type conversion in code
```
using System;

namespace type_conversion
{
    class Program
    {
        static void Main(string[] args)
        {
            // Implicit Casting 
            byte b = 1;
            int i = b;
            Console.WriteLine(i);

            // Explicit Casting
            int a = 10;
            byte j = (byte)a;
            Console.WriteLine(j);

            // Non-compatible
            // converting string to number with 'Convert' class function
            var number = "1234";
            int k = Convert.ToInt32(number);
            Console.WriteLine(k);

            // converting string into boolean
            string str = "true";
            bool l = Convert.ToBoolean(str);
            Console.WriteLine(l);
        }
    }
}
```
## Operators
>- Arithmetic Operators
>- Comparison Operators
>- Assigment Operators
>- Logical Operators
>- Bitwise Operators

>### Arithmetic Operators
>Arithmetic operators are used to perform common mathematical operations:
>![2022-01-02](https://user-images.githubusercontent.com/92302123/147879525-0c8cfd9f-5423-4b4c-b352-f012c23c39f6.png)
>### Comparison Operators
>Comparison operators are used to compare two values:
>![2022-01-02 (1)](https://user-images.githubusercontent.com/92302123/147880091-1be55e51-a77a-4f48-8324-4b68c1525f71.png)
>### Assignment Operators
>Assignment operators are used to assign values to variables.
>![2022-01-02 (2)](https://user-images.githubusercontent.com/92302123/147880270-fdb86303-3dbc-41bf-8363-a7c0e73a6bd5.png)
>### Logical Operators
>Logical operators are used to determine the logic between variables or values:
>![2022-01-02 (3)](https://user-images.githubusercontent.com/92302123/147880356-0de8afde-a4cb-4cc0-a634-a4fbfe2ebda2.png)
>### Bitwise Operators
>![2022-01-02 (4)](https://user-images.githubusercontent.com/92302123/147880497-3d028dd1-0d57-4469-9840-19ec976274e3.png)
## Primitive Types and Expressions (full summery)
>[13.1 Summary Primitive Types And Expressions.pdf](https://github.com/Bhavesh-0609/c-sharp/files/7800777/13.1.Summary.Primitive.Types.And.Expressions.pdf)

# Non-Primitive Types
## Class
>A class is a user-defined blueprint or prototype from which objects are created. Basically, a class combines the fields and methods(member function which defines actions) into a single unit. In C#, classes support polymorphism, inheritance and also provide the concept of derived classes and base classes.
```
using System;

namespace classes
{
    public class Person
    { 
        public string FirstName;
        public string LastName;

        public void Introduce()
        {
            Console.WriteLine("My name is " + FirstName + " " + LastName);
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Person john = new Person();
            // var john = new Person(); // u can also write like this
            john.FirstName = "John";
            john.LastName = "Smith";
            john.Introduce();
        }
    }
}

```
## Array
>Array is a data structure to store a collection of variables of same type

>syntax
```
int[] numbers = new int[3];
// int[] number = new int[3] {1, 2, 3}; // declaring and assigning value at same time
```
>Code of array
```
using System;

namespace array_in_c_sharp
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] numbers = new int[3];
            // var number = new int[3]; // you can also write like this
            numbers[0] = 1;

            Console.WriteLine(numbers[0]);
            Console.WriteLine(numbers[1]); // empty arrays default value in int is 0
            Console.WriteLine(numbers[2]);

            var flags = new bool[3];
            flags[0] = true;

            Console.WriteLine(flags[0]);
            Console.WriteLine(flags[1]); // empty arrays default value in boolean is false
            Console.WriteLine(flags[2]);

            var names = new string[3] { "Jack", "John", "Mary" }; //object initialization syntax
        }
    }
}
```
## Strings
>String is a sequence of characters.
>e.g. "Hello World"

>Syntax
```
string firstName = "Mosh";
```
>Concatenating strings
```
string name = firstName + " " + lastName;
```
>String formating
```
string name = string.Format ("{0} {1}", firstName, lastName);
```
>Using string join
```
var numbers = new int[3] {1,2,3};
string list = string.Join(",", numbers);
```
>String Elements
```
string name = "Mosh";
char fristChar = name[0]; // output will be 'M' from "Mosh"
// name[0] = 'm'; // this will give error b'cause Strings are immutable - Once you create them, you cannot change them.
```
>### Important in strings
>
>Strings are immutable - Once you create them, you cannot change them. like showen below
```
// name[0] = 'm'; // this will give error b'cause Strings are immutable - Once you create them, you cannot change them.
```
