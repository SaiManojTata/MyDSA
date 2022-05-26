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
