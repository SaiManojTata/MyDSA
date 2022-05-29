# Revising concepts of C++

## Basics 

```
int main(int argc, char* argv[])
```

argc **(Argument Count)** - Stores the number of arguments on the command line passed by the user 

argv - Array of character pointers which lists all the arguments passed

std::cout - Defined in iostream header file (predefined)

## OOP
OOP stands for Obejct-Oriented Programming.

* Object is an entity with state and behavior. 
* Software objects are just like real-world objects. 
* They have **state** in the form of variables called fields, and in the form of member functions called methods. 

* Hiding internal details (state) of the object and the actions being performed by the methods is known as **data-encapsulation**. 
* A class is a prototype of objects. An object is an instance of class. 
* Example: - Human is a class of living being and a person Sam is an instance of the class Human 

```
class Bulb
{
  private:
  // Instance Variables
    bool isOn;
  
  public:
  // Constructor
    Bulb();
  // Instance Method
    virtual void turnOn();
  // Instance Method
    virtual void turnOff();
};
```

## Passing Parameters 

**Pass by value** - By default, all parameters passed, are passed-by-value. This means, a separate copy is created inside the called method and none of the changes made in this method will be reflected in the calling method. 

**Pass by reference** - We can pass by reference by using the ```&``` operator. A variable ```var``` which is passed by reference is the same in the calling method and the called method. So, the changes to ```var``` made in the called method will be reflected in the calling method. 

**Pass by pointer** - When we pass the address of variable inside the calling method to the called method, then then changes are also reflected in the calling method. 

## Const correctness (from the standard) 

* Using the keyword ```const``` prevents the ```const``` objects from getting mutated. 

```
* void f1(const std::string& s);      // Pass by reference-to-const
* void f2(const std::string* sptr);   // Pass by pointer-to-const
* void f3(std::string s);             // Pass by value
```

* Declaring the const-ness of a parameter ensures type safety. 

* ```const X* p``` - p is a pointer to an X that is const [same as X const* p]
* ```X* const p``` - p is a const pointer to a X (X is non-const)
* ```const X* const p``` - p is a const pointer to a X that is const
* ```const X& x``` - x is a reference to an X that is const [same as X const& x]
* ```X& const x``` - does not make sense! x is a constant reference to a X, but references are already const!

Avoid confusion! 
* ```int const``` and ```const int``` are the same, but ```int const* ``` and ```int* const``` are not the same!
* ```int* const``` is a pointer to a const integer, whereas ```int const*``` is a constant pointer to a non-const integer.

A const member function does not mutate the object. It only inspects the object. 
Const member functions are indicated by adding the keyword ```const``` as a suffix. 

## Types of Variables 

* Instance Variables : Unique to each instance/object of a class 
* Class Variables : It is any field with a ```static``` modifier. There is exactly one copy of these variables regardless of how many instances of how many instances of the class are created. 
* Local Variables : Temporary variables in a method are called local variables. Only visible in the method in which they are declared. 

## Methods 

* Class Methods : Used to create class methods (should be invoked with the class name without                     the need to create even a single instance of the class)
* Instance Methods : Can only be invoked over an instance of a class
* Constructor : Invoked over objects when they are created 
* Destructor : Invoked over object when they are destroyed

## Access Modifiers 

* *Private* - visibility only within its own class 
* *Public* - visibility to all the classes in the package
* *Protected* - visibility within its own class and the subclasses its own class 

## Abstract Class 

An abstract class is a class that is designed to be specifically used as a base class. An abstract class contains at least one pure virtual function. You declare a pure virtual function by using a pure specifier (= 0) in the declaration of a virtual member function in the class declaration.

```
class Test {
public:
  virtual void f() = 0;
};
```

Test::f is a pure virtual function. A functional declaration cannot have both a pure specifier and a definition. 

```
struct A {
  virtual void g() { } = 0; // this is not allowed by the compiler
};
```

A pure virtual function is a function with no definition. Using an abstract class makes code reusable (for example, area of a shape can be defined as 
```virtual float Area() = 0``` in an abstract class, and other classes like Rectangle, Triangle can have their own implementations of this function area). 

Return type of virtual functions must be consistent throughout all of its implementing classes. 

