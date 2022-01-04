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
>### Code of array
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
### Escape characters
![2022-01-03 (1)](https://user-images.githubusercontent.com/92302123/147927980-ac6129df-8c18-40ce-b12f-846b05e680f0.png)
>### Verbatim string
>
>adding path is string will not look good because of escape characters because you have to add doble back slash for a single back slash
>
>e.g.
```
string path = "c:\\projects\\project1\\folder1"; // dont do this
```
>in verbatim string you dont have to add double back slash like shown belowe
```
string path = @"c:\projects\project1\folder1"; // it is verbatim string
```
>### Full code of strings
```
using System;

namespace strings
{
    class Program
    {
        static void Main(string[] args)
        {
            string firstName = "Mosh";
            string lastName = "Hamedani";

            var fullName = firstName + " " + lastName;

            var myFullName = string.Format("My name is {0} {1}", firstName, lastName); // concatinating string with function

            var names = new string[3] { "John", "Jack", "Marry" }; // string array
            var formattedName = string.Join(",", names); // formating strings with couma "," 
            // Console.WriteLine(formattedName);

            var text = "Hi John\nLook into the following paths\nc:\\folder\\folder2\nc:\\folder3\\folder4"; // this is simple string and not look so good
            var verbString = @"Hi John
                Look into the following paths
                c:\folder\folder2
                c:\folder3\folder4"; // this is verbatim string and its denoted with @ sign in verbatim string you dont have to use escape characters
            Console.WriteLine(text);
        }
    }
}
```

## Enum
>An enum is a special "class" that represents a group of constants (unchangeable/read-only variables).
>In enum if we don't set any value to the members of enum then the first member is going to be automatically set to zero and from there every member's value will be increamented by 1.
>syntax
```
public enum ShippingMethod
{
    RegularAirMail = 1,
    RegisteredAirMail = 2,
    Express = 3
}
```
>How to access enum
```
var method = ShippingMethod.Express;
```
>Enum's basic data type is int. if you want to change to other data type then you have to declere enum like this
```
public enum ShippingMethod : byte
{
    RegularAirMail = 1,
    RegisteredAirMail = 2,
    Express = 3
}
```
> ### Enum full code
```
using System;

namespace enum_in_c_sharp
{
    public enum ShippingMethod
    {
        RegularAirMail = 1,
        RegisteredAirMail = 2,
        Express = 3
    }
    class Program
    {
        static void Main(string[] args)
        {
            var method = ShippingMethod.Express;
            Console.WriteLine((int)method); // converting string to their number(int)

            var methodId = 3;
            Console.WriteLine((ShippingMethod)methodId); // converting the number to their string

            Console.WriteLine(method.ToString());

            var methodName = "Express";
            var shippMethod = (ShippingMethod)Enum.Parse(typeof(ShippingMethod), methodName);
            Console.WriteLine(shippMethod);
        }
    }
}
```
## Value type and Reference type
>### Value type 
>A data type is a value type if it holds a data value within its own memory space. It means the variables of these data types directly contain values.
> 
>The following data types are all of value type:
>- bool
>- byte
>- char
>- decimal
>- double
>- enum
>- float
>- int
>- long
>- sbyte
>- short
>- struct
>- uint
>- ulong
>- ushort
>
>#### Passing Value Type Variables
>When you pass a value-type variable from one method to another, the system creates a separate copy of a variable in another method. If value got changed in the one method, it wouldn't affect the variable in another method.
>
>Example: Passing Value Type Variables
```
static void ChangeValue(int x)
{
    x =  200;

    Console.WriteLine(x);
}

static void Main(string[] args)
{
    int i = 100;

    Console.WriteLine(i);
    
    ChangeValue(i);
    
    Console.WriteLine(i);
}
```
>### Reference Type
>Unlike value types, a reference type doesn't store its value directly. Instead, it stores the address where the value is being stored. In other words, a reference type contains a pointer to another memory location that holds the data.
>
>The followings are reference type data types:
>- String
>- Arrays (even if their elements are value types)
>- Class
>- Delegate
>
>#### Passing Reference Type Variables
>When you pass a reference type variable from one method to another, it doesn't create a new copy; instead, it passes the variable's address. So, If we change the value of a variable in a method, it will also be reflected in the calling method.
>
>Example: Passing Reference Type Variable
```
static void ChangeReferenceType(Student std2)
{
    std2.StudentName = "Steve";
}

static void Main(string[] args)
{
    Student std1 = new Student();
    std1.StudentName = "Bill";
    
    ChangeReferenceType(std1);

    Console.WriteLine(std1.StudentName);
}
```
> ### Value type and Reference type full code
```
using System;

namespace reference_type_and_value_type
{
    class Program
    {
        static void Main(string[] args)
        {
            var a = 10;
            var b = a;
            b++;
            Console.WriteLine(string.Format("a : {0}, b: {1}", a, b));
            
            var array1 = new int[3] { 1, 2, 3 };
            var array2 = array1;
            array2[0] = 0;
            Console.WriteLine(string.Format("array1[0] : {0}, array2[0]: {1}", array1[0], array2[0]));
        }
    }
}
```
