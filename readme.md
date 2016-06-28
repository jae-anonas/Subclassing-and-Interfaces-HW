---
title: Subclassing and Interfaces
type: Homework
duration: "1:00"
creator:
    name: Charlie Drews
    city: NYC
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Subclassing, Abstract Classes, and Interfaces

> ***Note:*** _You can discuss with classmates, but everyone must submit their own answers_

## Exercise

#### Requirements

- Fork this repo, then add your answers direcly to this **readme.md** file
  - After forking, you can clone, edit the readme in the text editor of your choice, and push back to Github...
  - Or, you can edit the readme [right from the browser](https://help.github.com/articles/editing-files-in-your-repository/)
- After adding your answers, submit a **pull request**

#### Questions

1. What is the difference between *member variables* (also called *instance variables*) and *class variables* (w/ keyword `static`)? Which can be accessed without creating an instance of the class?

Member variables can be different among different instances of the same class but static variables will always be the same during the lifetime of the program. Static variables can be accessed without creating an instance

2. Does it make sense to write  *getter* and *setter* methods for a `public` member variable? What about `private` variables?

It doesn't make sense since a public member variable can be accessed(changed,viewed) using the "." operator. Private variables, on the other hand, can only be changed within the class which is why we need public methods called getters and setters so we can access them outside and also validate the values we put in it.

3. What are some benefits of making member variables `private`?

An advantage is restriction of access which can make our classes more robust, especially when other developers use them.

4. If class A extends class B, which is the super class and which is the sub class? Which would you call parent, and which would you call child?

Class B is the super class and class A is the subclass. The parent would be the super class B and the child would be class A.

5. What does it mean for a class to *inherit* methods and/or variables from its parent class?

It means that the child class will have the methods and variabes of its parent class.

6. Consider the following code, where class Refrigerator extends class Appliance, and `getTemperature()` is a method in Refrigertor, but NOT in Appliance:
  ```
  Appliance myAppliance = new Refrigerator();
  double temperature = myAppliance.getTemperature();
  ```
  Why will this call to `getTemperature()` cause an error? How will *casting* help solve this issue?
  
This is because an object of type Appliance will not recognize the methods in an object of type Refrigerator. To fix this, we can write:
    double temperature = ((Refrigerator)myAppliance).getTemperature();

7. In a normal class (also called a *concrete* class), do you need to *implement* all of the methods, or can your simply *declare* some? What about in an `abstract` class?

Yes. You have to implement all the methods in a concrete class. In an abstract class, you can implement some and you can just declare the others for implementation of a class which extends it.

8. What about an `interface`? Can you implement any methods in an interface? Can you declare methods in an interface?

You can't implement any method in an interface, you can only declare them.

9. Can you create an instance of an `abstract` class? Also, look up the Java keyword `final` and see if you can explain why a class CANNOT be both `abstract` and `final`.
 
You can create an instance of an abstract class but you will still have to implement the abstract methods in it as you create its instance.
A class can't be both final and abstract since when using "final", we're basically telling the computer that we do not want the member variables and methods to be overridden which defeats the purpose of using abstract where we want the abstract methods to be implemented(overridden).

10. What happens when a method *overrides* another method? If a parent and child class have methods with the same name, when you call that method on an instance of the child class, which implementation of the method will be executed?

When a method overrides another, it means that there is an implementation of the exact same method in a class' parent class. When this happens, the method of the child class will be executed, and the same method in the parent class will be considered overridden.

11. What is the relationship between `List`, `LinkedList`, and `ArrayList`? Why do we call a method *polymorphic* if it takes an input of type `List` rather than an input of type `LinkedList` or `Arraylist`, and why is that useful?

LinkedList and ArrayList are subclasses of List.
We call that method "polymorphic" because it can accept different types of input(e.g. LinkedList, ArrayList).
The usefulness of polymorphism can be seen when using System.out.println(). We can put different variable types inside those parentheses and it would still work. Had that function only accepted strings, we would need other function names to print ints, doubles, etc.

#### Deliverable

This file, with your answers added

## Additional Resources

Refer to the [Classes lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/classes-lesson), the [Subclassing lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/subclasses-lesson), and the [Interfaces & Abstract Classes lesson](https://github.com/ga-adi-nyc/Course-Materials/tree/master/lessons/java-essentials/interfaces-and-abstract-classes-lesson).

Feel free to google these concepts as well. There are plenty of Java tutorial websites and StackOverflow posts that can help you. But be sure to write up your answers in your own words - copying and pasting some text does NOT help you actually learn!
