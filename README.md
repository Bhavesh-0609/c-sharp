# c-sharp
C# documentation

**Basics**

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

<br>**Variable types , formate string and constant in code**
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

<br>**Type conversion theory**

>In C#, there are two types of casting:
>
>Implicit Casting (automatically) - converting a smaller type to a larger type size<br>
>char -> int -> long -> float -> double <br>
>Explicit Casting (manually) - converting a larger type to a smaller size type<br>
>double -> float -> long -> int -> char <br>

**Implicit Casting**<br>
>Implicit casting is done automatically when passing a smaller size type to a larger size type:
```
int myInt = 9;
double myDouble = myInt;       // Automatic casting: int to double

Console.WriteLine(myInt);      // Outputs 9
Console.WriteLine(myDouble);   // Outputs 9
```

**Explicit Casting**<br>
>Explicit casting must be done manually by placing the type in parentheses in front of the value:
```
double myDouble = 9.78;
int myInt = (int) myDouble;    // Manual casting: double to int

Console.WriteLine(myDouble);   // Outputs 9.78
Console.WriteLine(myInt);      // Outputs 9
```
