
# Java Class :  Encapsulating Object State & Behavior 

## Learning Goals

- Define common characteristics of objects including state and behavior
- Define fundamental Java class members: fields, constructors, and methods

## Java Primitive versus Reference Data Types

So far, we've mostly worked with variables that are declared as **primitive data types**, which include:
byte, short, int, long, float, double, boolean, and char. 

We have also worked with a few **reference** data types.
A reference data type represents any instantiable class (`String`, `Scanner`, etc), as well as arrays.

In the next few lessons, we will learn how to create new reference data types by defining new Java classes! 

## Classes in Java

Java is an object-oriented programming language. This means it thinks of the
world as "objects". Java can model a physical object such as a dog, bike, or television.
Java can also model abstract objects such as an event (birthday party, 
music concert, company meeting), the components of a web browser (menu bar, button, 
popup dialog, scrollbar), or even a programming language (Java, Python, Javascript).

All objects have **state** and **behavior**.   
- State encapsulates the relevant properties (data) about an object. 
- Behavior is the set of operations that access and modify the object state.

For example, consider the state and behavior of a dog, a television, or a button displayed on a web page:

| Object                | State                                                          | Behavior                                                           |
|-----------------------|----------------------------------------------------------------|--------------------------------------------------------------------|
| Dog                   | name <br> breed <br> age <br> is wagging tail                  | eat a treat <br> fetch a toy <br> bark                             |
| Television            | volume <br> channel <br> size <br> brand <br> model <br> is on | change the channel <br> turn volume up or down <br> turn on or off |
| User interface button | color <br> shape <br> label <br> location  in window           | click                                                              |

In Java, a software object also has state and behavior.  State is stored
in variables that are called **fields** and behavior is implemented in **methods**.

In an object-oriented programming language, like Java, a **class** is the general description of
an object's state and behavior.

- A **class** is the blueprint that defines a new data type (state and behavior).
- An **object** is an _instance_ of a **class**.

The basic syntax of a Java class definition is shown below:

```java
public class ClassName {
    
    //fields
    ...
            
    //constructors
    ...
            
    //methods
    ...
    
}
```

Here are a few things to note:
- The `public` keyword is covered in a later lesson on **access modifiers**.
- The `class` keyword indicates we are defining a new Java class.
- The class name should follow standard naming conventions, which are described in a subsequent section.
- The open curly brace `{` indicates the beginning of the class definition and
  has a matching close curly brace `}` at the end of the class definition.
  The area between the curly braces is called the **class body**. The class body contains:
  - fields (variables) to store the state of the class and its objects.
  - constructors to initialize the state of new objects by assigning values to the fields.
  - methods to implement the behavior of the class and its objects.

In this lesson, we will focus on defining fields to encapsulate state.
The syntax and implementation of constructors and methods will be covered in a later lesson.

- A field is a variable that stores a property of an object or the class itself.
  - An **instance variable** stores a value in each instance of the class (i.e. each object has its own copy of the field).
  - A **static variable** (also called a **class variable**) stores a single value in the class (i.e. there is only one copy of the field).
- A field is normally defined on its own line of code with a `;` at the end.
- A field is defined using a variable declaration that has a "type" and a "name", such as `String breed;`.
  - The type allows us to tell Java what type of value we expect this property to be (i.e. `int`, `String`, etc).
  - The name is how we want to be able to refer to the property.
- A field may have additional **access and non-access modifiers**, which are covered in later lessons.

## Defining a `Dog` Class

Consider how we might define a Java class to store data about two dogs: an 8-year-old Great Dane
named Bruno, and a 5-year-old Pug named Penny.
Both dogs have the same data structure (i.e. set of properties such as name, breed, etc.)
but may have different values for each property ("Bruno" vs "Penny", "Great Dane" vs "Pug", etc).

![dog objects](https://curriculum-content.s3.amazonaws.com/6676/java-mod2-oop-fundamentals/2dog_objects.png)

Let's define a class named `Dog` with fields (instance variables) to store their name, breed, age, and whether their tail is wagging:

```java
public class Dog {
    
    String name;
    String breed;
    int age;
    boolean waggingTail;
    
} 
```

Constructors and methods are omitted from the current class definition.
Eventually we will add methods that operate on the fields, such as a method
named `eatTreat()` that assigns the `waggingTail` field to true.

Once we have defined the `Dog` class, we can create many instances of the class.
The visualization above depicts how memory is allocated to store the state of two `Dog`
instances, with each having a separate copy of the fields. As we've seen in previous lessons,
when a method declares a variable with a primitive type such
as `int` or `boolean`, the value is stored on the stack.
A variable declared with a reference type however represents an
object, and objects stored their fields in a part of memory called the heap. 

But how do we create a `Dog` class instance in Java?
How is memory allocated in the heap to store the fields for each class instance?
How do we assign values to the fields?

All these question will be answered in the next couple of lessons!

## Naming conventions

By convention, in Java the name of the class always starts with an uppercase character.
If the name of the class has multiple words in it, each word starts with an uppercase character.

- Example: `RemoteController`.   
  This is often referred to as "**pascal case**", meaning multiple words are
  put together where each word starts with an uppercase character.

Field names start with a lowercase letter and then capitalize the first
letter of every subsequent word.

- Example: `waggingTail`.   
  This is referred to as "**camel case**".

A field that represents a constant value is specified using the keyword `final` and should
contain all uppercase letters with an underscore `_` between multiple words.

- Example: `SPEED_OF_LIGHT`.




## Conclusion

Java is a class-based, object-oriented programming language.  A class defines the
data structure (fields), initialization (constructors), and behavior (methods)
of the objects that are instances of the class.

## Resources

- [Java Tutorial - Classes and Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/index.html)   
- [Declaring classes in Java](https://docs.oracle.com/javase/tutorial/java/javaOO/classdecl.html)   