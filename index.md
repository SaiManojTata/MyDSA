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



