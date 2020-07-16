# CsharpInterviewQandA
C# questions and answers

# Dependency Injection, LinkedList and Queue
Reverse LinkedList, CRUD in LinkedList
Different Type of Dependency Injection 


# Problem Solving on Strings
like reverse string in multiple ways, count the occurance of char in string, sub string

# Solving Matrix Problems.

# [SOLID Principles](https://github.com/venk120soft/software-design-principles/blob/master/SOLID%20principles)
###### Single Responsibility Principle 
it states that a class should have one and only reason to change.
###### Open Closed Principle Principle 
it states that a class should be open for extension and closed for modifications.
###### Liskov Substitution Princple 
it states that Derived types must be substitutable for their base types
###### Interface Segrigation Principle 
it states that a client should never be forced to implement an interface that he doesn't use
###### Devpendency Inversion Principle 
it states that Entities are must depend on abstractions not on concretions. It means high level module must not depend on the low level module, but they should depend on abstractions.


                                                                  OOPS  
##### 1.What is the difference between Object based programming and Object-oriented programming?
   - If a language supports only encapsulation then it is called as object-based programming language. Ex: vb
   - If a language supports encapsulation, inheritance and polymorphism, then it is called as object-oriented programming language. Ex: C#, Java, C++
##### 2.What are the Main concepts of oops?
     There are four main concepts of oops
      a) Encapsulation
      b) Inheritance
      c)Polymorphism
      d)Abstraction
##### 3.What is encapsulation and its advantage?
    -Grouping of related things together is called encapsulation.
    -due to encapsulation we can achieve portability.
##### 4.What is Data hiding?
    - Hiding unnecessary information from user is called as data hiding.
    - due to data hiding we can protect behavior of component.
    - data hiding can be implemented by using access modifiers.
##### 5.What is Abstraction? 
   -Hiding complete implementation details from the user is called as abstraction.
  -Due to abstraction we can make user feel easy and comfortable while using component.
##### 6.What is the difference between data hiding and abstraction?
   -Data Hiding is hiding unnecessary information from user, so that we can protect behavior of component.
  -Abstraction is hiding of complete implementation details, so that component usage becomes easy.
##### 7.What is the difference between encapsulation and class?
    -Encapsulation is oops concept but class is a feature of language by which we can implement encapsulation.
##### 8.How to implement encapsulation in C#?
   -By using class, struct, interface, enum.
##### 9.What are the access modifiers?
Access Modifiers:  These are used to restrict the accessibility of the members up to some boundaries.
	By the Access Modifiers we can achieve data hiding.
  There are four access modifiers
    a) private
    b) protected
    c) public
    d) internal.
we can combine protected and internal 
##### 10.What is the behavior of protected internal?
     -protected internal is combination of two access modifiers.
     -with in same assembly it will be like an internal, outside assembly it will be like a protected.
so that we can make use of it in any class of same assembly and only derived classes outside assembly.
##### 11.What is object?                                                                                Ans: -it is an instance of class.
##### 12.What is min size of object if there is no member in class?               Ans: -8bytes
##### 13.What is default access modifier for class?                                        Ans: -internal
##### 14.What is default access modifier for members in class?                    Ans: -private
##### 15.What is the base class for all classes in .net?			          Ans: -System.Object.
##### 16.What is the difference between class and structure?
1) Class
- it is reference type  
- All access modifiers allowed          
- All types of methods allowed    
- destructor is allowed      
- All types of constructors allowed        
- Inheritance possible           
- it can implement interface     
2) Struct
- it is value type
- protected not allowed.
- virtual and abstract methods not allowed.
- destructor not allowed.
- default constructor not allowed.
- inheritance is not possible
- it also can implement interface.
##### 17.is it possible to define method in enum type? 				 Ans: -No
##### 18. How to initialize object?
     -in two ways we can initialize object.
      a) by using object initializer. Ex: Test obj= new Test() { a=1, b=2 }
      b) by using Constructor. Ex: Test obj= new Test(1,2);
##### 19.What are accessor and mutator methods?
-a method which is designed to get value from variables of class is called as accessor method.
-a method which is designed to modify values of variables of class is called as mutator method.
##### 20.What is the difference between property and indexer?
     - property is a member of class or struct which provides a flexible mechanism to read and write from and to the variable of class or struct.
     - it can be static. 
     - it cannot be overloaded.
     - Indexer is also a member of class or struct which is also providing flexible mechanism to read and write from and to the variable of class or struct by using subscript and index.
   -indexer cannot be static.
  -always name of indexer must be this, and it can be overloaded
##### 21.Is it possible to define property as static?                                        Ans: -yes
##### 22.is it possible to define indexer as static?                                          Ans: -no
##### 23.What is the use of base keyword?
   -with the help of base keyword, we can access the base class members from derived class.
   -always base keyword will refer to immediate base class members.
   -We can call base class constructor from derived class constructor.
##### 24.What is Constructor?
     -it is a special method in the class which is invoked automatically when the class has been instantiated.
     -it can be used to initialize instance variables of class to some meaningful initial values once object has been created.
##### 25.Why name of constructor and class name must be same?
       -to make the compiler to identify it easily.
##### 26.Why return type is not allowed for constructor at programmer level?
   -constructor should not be used for any other purpose, it must be used for only initialization.
##### 27.What are different types of constructors available?
     -static constructor: A constructor which is defined as a static member of the class 
     -non static constructor: A constructor defined as the non- static member of the class
       a) default constructor: A Constructor which doesn’t have the parameters
       b) parametric constructor: A Constructor with Parameters.
##### 28.Explain static constructor?
   - A constructor can be defined as a static member.
   - static constructor should not have access modifier
   - it must be parameter less.
   - it cannot be overloaded.
   - it can be used to initialize static variables of class but not non static variables.
   - it is invoked one and only once when the class has been loaded into appDomain by class loader.
##### 29.When the static constructor is invoked?
    -it is invoked one and only once when the class has been loaded into appDomain by class loader.
##### 30.Is it possible to overload static constructor?                                     Ans: -no
##### 31.What is the need of copy constructor?
  -it is used to initialize a new object with the help of an existing object when new object has been created.
##### 32.What is destructor and when is it invoked?
    -it is also a special method which is invoked automatically before object destruction takes place by Garbage collector.
   -the name of the destructor and the name of the class must be same.
   -it must be preceded by ~ character. 
   -access modifiers can't be applied
   -It must be parameter less
##### 33.What is disadvantage of destructor?
    -the destructor in the class is represented by finalize( ) of object in IL code
    -when GC decide to deallocate the memory then it will check if there is any finalize() defined for the object if so then the object will be moved to freachable queue.
    - finalize() of object is invoked which intern invokes finalize() of System.Object
    -finalize() of System.Object invokes GC to deallocate memory, so that it will be an extra burden to the GC when the destructor has been defined for the class.
##### 34.when the class is loaded into App Domain?
   - the class can be loaded into the application domain in the following situations 
    a) when the first object of the class has been created
    b) when the static method of the class has been invoked.
##### 35.How to invoke base class constructor in Derived class constructor?
    - by using base Keyword.
##### 36.What is namespace?
    -It is a logical container which can contain classes, interfaces, enums, delegates, structures
    -with the help of the namespace we can avoid name collisions.
    - A namespace can contain another name space also.
##### 37.Can we apply access modifier to namespace?                                     Ans: -No
##### 38.Is it possible to declare instance variables in namespace?                    Ans: -No
##### 39.What is alias name for namespace and when is it required?
  -While including too many namespaces in the application with the help of using keyword   then there is a chance of duplicate members.
  - to avoid the conflict, we can assign a temporary name to the duplicate member which is called as alias name for the namespace.
##### 40.What is the difference between By Ref and By Val?

By Val:
- it is read only variable in a method
- By default all the variables passed are by val
- No need to be initialized
- changes won’t reflect
- Ex:We only Add the changes in Answer paper.
By Ref:
- it is read and write variable in method. 
- it must be preceded by ref keyword
- it must be initialized while passing to method.
- changes are reflected
- Ex: If you take question paper for the exam, you make the changes in the same question paper and give it to the invigilator.
i.e we are writing the answers in the same question paper.
 
##### 41.What is difference between out and ref parameters?
                Out
-it is write only variable in method  
-it must be preceded by out keyword  
-it need not to be initialized while passing it      to method    
- changes are reflected
- Ex: If you take question paper for the exam, you will write your answers in your sheet 
                Ref :
- it is read and write variable in method. 
- it must be preceded by ref keyword
- it must be initialized while passing to method.

- changes are reflected
- Ex: If you take question paper for the exam, you make the changes in the same question paper and give it to the invigilator.
i.e we are writing the answers in the same question paper.

##### 42.What is the purpose of params keyword?
   - To pass the array of parameter to the method is called as params Keyword.
##### 43.What is binding?
  - Replacing the method invocation with appropriate base reference is called as binding or linking
##### 44. How many types of bindings are available?
  - There are two types of binding
   a) Static Binding: If the binding process has been carried out during the compilation it is called as Static binding
   b) Dynamic Binding: If the binding process has been carried out at the time of running the application then it is called as dynamic binding
##### 45.What is Method overloading?
     -defining number of methods with the same name and different signatures is called as Method Overloading
     -Method Overloading is possible within the same class as well as its derived classes.
     -Any types of methods can be Overloaded.
     -No Keyword must be required for the method.
##### 46.What is Method overriding?
   -Defining a number of methods with the same name, same signature and return type with different functionality is called as method Overriding.
   -It is Possible with in the derived classes only
   -Only virtual and Abstract methods can be Overridden
   -override Keyword must be used.
##### 47.What is the difference between Method overloading and Method overriding?
##### 48.What is polymorphism?
     - Having Different forms to the same method is called as Polymorphism.
     -With the help of polymorphism, we can perform different actions with same method invocation
##### 49.What are the types of polymorphism?
     -There are two types of polymorphism
    a) static Polymorphism: - If the Polymorphism is implemented by using Static binding then it is Static Polymorphism
       -In C# Static polymorphism can be implemented by using method Overloading and operator Overloading
    b) Dynamic polymorphism: -If polymorphism is implemented by using dynamic binding then it is called as Dynamic Polymorphism
       -In C# Dynamic polymorphism is implemented by using method Overriding
##### 50.What is the difference between abstract class and interface?
Abstract Class:                                                           
- It is Partially unimplemented class 
- Complete Abstraction is not Possible
- All Types of members are allowed      
- Object cannot be created       
- Access modifier can be applied to the members of the abstract class
- Constructor and destructor are allowed                                                                                                                                                Interface:
- Fully Unimplemented class
- Complete Abstraction is possible
- Only methods, Properties and indexes are allowed
- Object cannot be created
- Access modifiers can’t be applied explicitly, public is the default access modifier 
- Constructor and destructor are not allowed                                                          
##### 51.Can we apply private or protected access modifier to interface?            Ans: -No
##### 52.why access modifiers cannot be applied to members of interface?
  - By default, members of interface are public, and members of the interface must be always exposed.
##### 53.why object cannot be created for abstract class or interface?
    -Abstract classes are Partially unimplemented so that some of the members are not defined 
    -Interface is fully unimplemented so that none of the members will have the implementation
    -If the object creation is made possible then we need to call the members without implementation. Thus, object creation for abstract class and interface must be avoided
##### 54.can we declare member of interface as static?                                        Ans: -No
##### 55.why multiple inheritance is not possible for classes?
  -Deriving a new class from two or more bases classes is called multiple inheritance
  -when the class is derived from too many base classes then there is a chance of duplicate members with full implementation
  -when that member is invoked w.r.t derived class object then there would be an ambiguous situation.
  -to avoid this ambiguous situation multiple inheritance in classes is not allowed in c#.
##### 56.What is private implementation for interface member?
   -while implementing the interface members if the methods are defined w.r.t interface name then it is called as private implementation
   -In this implementation members must be private members of the class so that interface members can be invoked w.r.t interface variable name only but not w.r.t object of implemented class.
   -It is also called as explicit implementation of interface
##### 57.What is sealed class?
   -If a class is declared as sealed class then it can’t be extended 
        i.e Inheritance is not possible for that class 
##### 58.What is Extension method and how to define it?
  -If a method is defined to provide extra functionality to existing type without disturbing its originality then it is called as extension method.
   -it is introduced from C# 3.0
   -It must be static method
   -IT must be defined with in the static class
   -it must have the parameter of the type to be extended
   -parameter must be preceded by this keyword
##### 59.Can we Overload destructor?                                                                   Ans: -No
##### 60.What is the use of Dispose()?
  -It is used to invoke the GC dynamically.
##### 61.What is the difference between String and StringBuilder classes?
  - Both are used to manipulate and maintain the string 
  -each method of the string will return another string object
  -each method of string builder will manipulate with in the same object without returning another string object
##### 62.What is the advantage of var keyword?
  - it is introduced from C# 3.0
  -It is used to declare the local variables
  -var type of variable must be initialized during the declaration itself.
  -Type of variable will be decided based on its initialization 
  -It cannot be initialized with null, but it can contain the reference of object
  -var type of variable cannot be passed as a parameter to the method.
##### 63.Can we assign null to var type of variable?                                                  Ans: -No
##### 64.Can u allow class to be inherited, but method must be prevented from being overridden?
##### 65.What is the difference between abstract method and virtual method?
abstract method:                                                    
-Abstract Keyword must be used   
-It should not have definition in the base class  
-It must be overridden in the derived classes        
-It must be with in the abstract class   
virtual method:
-virtual keyword must be used
-It must have the definition in the base class
-It may or may not be in the derived classes
-It can be with in the abstract and non-abstract classes
##### 66.Can we define virtual method as private member?                              Ans: - No
##### 67.Can we define abstract method as private member?                            Ans: - No
##### 68.Can we define abstract method as static?                                            Ans: - No
##### 69.Can we declare private class in namespace?
- No, members of the namespace must be either internal or public
##### 70.What is the difference between new and override keywords?
  - New is used to create the object dynamically
  -Override keyword is used to override either virtual or abstract methods
##### 71.Can we Create object without defining class?
  -Yes, we can create an object by using new operator with some initialization.
  -Based on initialization appropriate anonymous type will be defined by the compiler.
##### 72.What is the purpose of this?
  -it is a predefined reference variable which contains the reference of a current object or active object.
  - when the names of the parameters and instance variable names are same then instance variables can be differentiated from the parameters by using this keyword.
  -This can be used with instance methods only. i.e. non-static methods
##### 73.What is the difference between Array and ArrayList?
Array:      
-it is typed collection            
-fixed size             
-boxing and unboxing not needed  
ArrayList:
-it is untyped collection
-size will be increased dynamically.
-extra burden of boxing and unboxing.
##### 95.What is Manifest?

##### 74.What is difference between List and ArrayList?
   List                                                           
ArrayList
-it is generic collection   
-boxing and unboxing is not needed   
-size will be increased dynamically                                          
-it is non generic collection
-Extra burden of boxing and unboxing
-size will be increased dynamically        
##### 75.What is the difference between Hashtable and Sorted List?
-both the collections are defined as Dictionaries where in elements are stored in the form of (key, value) pair, but in sorted List values are maintained according to keys in ascending order.
##### 76.What is assembly?
     -it is language independent, self-described portable software component.
##### 77.Is IL language is OO?                                                                              Ans: NO
##### 78.What are different types of assemblies?
     -there are three types of assemblies
     a) Private Assembly: -an assembly without strong name key is called as private assembly
         -when private assembly is used in application, then copy of it will be available as part of application.so that memory will be wasted when too many applications are running at a time.
         -if some changes are made in assembly then they are not reflected to application until its compilation.
     b) Public or Shared Assembly: -an assembly with a strong name key and placed in GAC is called as shared assembly or public assembly.
                                                             -Advantages:
           -No memory wastage if even too many applications using same assembly are running.
           -If some changes are made to assembly then those changes are automatically reflected to application without recompilation
     c)Satellite Assembly-it is private or public assembly with resource file.
                -it is used while creating assembly for multi linguistic purpose.
##### 79.What is digital signature of an assembly?
    -it is a combination of private key and hash algorithm value of assembly.
    -digital signature of an assembly will be checked while installing it into GAC.
##### 80.What is PE file?
    -an assembly with win32 header is called as PE file
    -it is microprocessor independent.
##### 81.What is ilasm.exe?
    -it is a tool which is used to convert assembly into PE file.
##### 82.What is ILDASM.exe?
    -it is also a tool which is used to see the content of assembly in text format.
##### 83.What are advantages of generics?
     -Boxing and unboxing burden can be reduced while working with collections.
     -Code burden on developer can be reduced.
##### 84.What is boxing and unboxing?
     -Converting value type into reference type is called boxing.
     -During boxing type casting will be done implicitly
    -Converting reference type to value type is called as unboxing
    -during unboxing type casting must be done explicitly
##### 85.What are the disadvantages of boxing and unboxing?
     -During boxing and unboxing values must be copied from method stack to managed heap and vice versa.
     -During unboxing if typecasting is not done properly then it will raise exception called InvalistCastException.
##### 86.What is delegate?
     -delegates are similar to function pointers in C++,however, delegates are type-safe and secure
     -it is reference type which represents method.
     -.delegates are used to pass methods as arguments to other methods.
     -delegate object can contain reference of method
    -with the help of delegate object, we can invoke a method dynamically based on its reference.
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/object-oriented-programming#Delegates
##### 87.What are different types of delegates?
     there are two types of delegates
    a) Single Cast Delegate-if delegate object contains only one method reference then it is called as single cast delegate.
    b) Multi Cast Delegate: -if delegate object contains more than one method reference then it is called as multicast delegate.
       -with the help of multicast delegate, we can invoke multiple methods sequentially with single call.
##### 88.What is lambda expression?
      -representing complete method definition with the help of simple expression is called as lambda expression
##### 89.What are different types of lambda expressions?
     -there are two types of lambda expressions
      a) Predicate: A lambda expression which is designed to return either true or false is called predicate
      b) Projection: A lambda expression which is designed to return other than true or false is called projection.
##### 90.What is Anonymous method?
   A method which is assumed by the compiler based on the definition of the delegate and definition of the method given by developer is called as anonymous method.
##### 91.What is dll hell problem?
    -in windows environment all application dll s are copied to the system32 folder of windows directory, so that there is a chance of overwriting one application dll by another application dll.
    -if share dll’s are used by multiple applications then due to uninstallation of one application, another application may be affected which is called as dll hell problem.
##### 92.explain different parts of assembly version?
     Assembly version contains four parts
      a) Major: this part indicates the new namespace, class, interface, delegate insertion into assembly
      b) Minor: this part indicates the new methods, properties, insertion into assembly
      c) Build: this part indicates the number of times bugs fixed in assembly
      d) Revision: this part indicates how many times assembly has been rebuilt irrespective of bugs reported or not
##### 93.What is the purpose of checked and unchecked blocks?
     -checked block is used to provide a piece of code where there is a chance of raising Overflow Exception.
     -Unchecked block does raise Overflow Exception.
##### 94.What is typeof()?
   -it is operator which is used to extract complete type information dynamically.
   -it will return System.Type object

##### 95.What is Web.config?
 -It is a configuration File for an asp.net web application.
 -It is an XML Document that defines configuration information regarding the web application it will store the information how the application will act
 -the Web.config file contain the information regarding 
 Security configuration, session state configuration, compilation settings, database connection settings, Application language.
##### 96.What is Global.asax?
It is also called as Asp.Net application File it is an optional file that can contain code for responding to the application level events raised by asp.net or http address
Application-Start, Application-end, Session-Start, Session-end, Application-Begin request, Application-Authentication request. 
##### 97.What is AppDomain?
It is a Temporary memory block maintained by the CLR For the .Net Enabled Applications
##### 98.What is Enumeration(or) enum?
 -Enum is used to define our own data type by specifying the possible set of identifiers
 -It cannot contain Methods
 -Each Identifier will be represented by using Integer values, generally values will be starting from 0 and ending n-1 if there are n identifiers
 - we can assign our own values also 
 -Enum can be defined with in the class or outside the class i.e. with in the namespace
 -Access Modifiers can be applied to the enum.
Ex: enum color {red, green, blue, yellow}
    Color c=c.red //c value is ‘0’
```javascript
namespace EnumDemo{
enum color {red, green, blue, yellow}
Class Program {
public static void main(string args[]){
color c=color.green; 
console.writeline(“your colr ”+c);
Consol.WritreLine(“c value”+(int)(c));
}
}
}
```
##### 99. Where do you work with the static?
To initialize the static variables, where there is no need of creating the object but want to Access.
##### 100. What is Reflection? 
Reflection provides that describes assemblies, modules and types. We can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties. If you are using attributes in your code, reflection enables you to access them.

Here's a simple example of reflection using the static method :
GetType - inherited by all types from the Object base class - to obtain the type of a variable:

##### 101. What is the Difference between Const and ReadOnly keywords?
const, readonly both keywords are used to define the variables.
const variables can’t be re-assigned, it has to be assigned when it is declared.
const is implicitly a static variable, so it can be accessed with the class name(A.piValue)

readonly can’t be re-assigned in other than the constructor.
readonly is having reference to it.

let’s say when we create this variables in assembly A and referenced in assembly B wanted to access them using the reflection in one of the classes in assembly B Then, If we change the const value to 20 from 10 in assembly A and compiled it then, the const value still be 10 in assembly B. until unless we compile assembly B as well.

But in case of readonly, as it maintains the reference to it no need to compile the assembly B, its enough to compile assembly A the changes will reflect to all it references where the assembly is used.
##### 102. What is Garbage Collector?
Garbage Collector is a programme that manages the memory deallocation.
Main objective of Garbage Collector is free up the heap memory by destroying unreachable objects
unreachable objects are said to be 
if the value becomes null
if re assign the value to it
Object created inside method 
##### 103. What is the difference between IEnumerator and IEnumerable ?
IEnumerable is an interface that defines one method GetEnumerator which returns an IEnumerator interface, this in turn allows readonly access to a collection. A collection that implements IEnumerable can be used with a foreach statement.
```javascript
interface IEnumerable{
IEnumerator GetEnumerator();
}
interface IEnumerator{
          public object Current;
          public void Reset();
          public bool MoveNext();
}
```
IEnumerator only gives readonly access to the list
##### 104. What is the Difference between IEnumerable and IQueriable?
IEnumerable exists in the System.Collections namespace, suitable for querying data from in-memory collections like List, Array and so on.

While querying data from the database, IEnumerable executes "select query" on the server-side, loads data in-memory on the client-side and then filters the data. 

IEnumerable is beneficial for LINQ to Object and LINQ to XML queries.
IEnumerable extends IQueryable

IQueryable is beneficial for LINQ to SQL queries.
```javascript
interface IQueryable : IEnumerable{
// support for Linq to Sql Queries
}
```
##### 105. What is the purpose of private constructor in a class?
A class with private constructor can’t be inherited.
We cannot create an object for the class which has private constructor.
The use of Private constructor in modern programming is to implement Singleton or Factory patterns
Classes with private constructors are  used for utility classes

Note: "A class with ONLY private constructor can not be inherited or instantiated."  A class with private constructor can be inherited or instantiated if there is at least one public constructor
##### 106. When should we use private constructor over static class? 

