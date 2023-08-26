
# Object Oriented Programming Notes - Last Minute Revision :white_check_mark: 

Here we have last minute revision notes of object oriented programming language. These questions will familiarize you with the most important object-oriented programming concepts and help you ace your job interviews :raised_hands:


## Most Asked OOPS Interview Questions

### 1: What is OBJECT-ORIENTED PROGRAMMING?

**Answer**: Object-oriented programming is a programming paradigm built on the concept of objects.

In Other Words, it is an approach to problem-solving where all computations are carried out using objects.

---

### 2: Class and Object

**Answer**: 

**Class**: A class is the building block that leads to Object-Oriented programming. A Class is like a Blueprint or template that defines the properties (attributes) and behaviors (methods) that the objects of that class will have.

**Object**: 
  1. An Object is an instance of a Class. When a class is defined, no memory is allocated but when it is instantiated (i.e. an object is created) memory is allocated.
  2. An object is a specific instance created from a class. It's like the actual item built using the blueprint

**Example** : Car is a Class and its objects can be SUV , Swift , Porsche


### 3: Constructor

**Answer**: 

- Constructors are special class members which are called by the compiler every time an object of that class is instantiated.

- Constructors have the same name as the class and may be defined inside or outside the class definition.

There are 3 types of constructors:

    1. Default constructors
    2. Parameterized constructors
    3. Copy constructors

1. **Default Constructor**: Default constructor is the constructor which doesn’t take any argument. It has no parameters.

2. **Parameterized Constructor**: A constructor is called Parameterized Constructor when it accepts a specific number of parameters.

3. **Copy Constructor**: A copy constructor is a member function which initializes an object using another object of the same class.

#### Characteristics of the constructor:

- Constructor has the same name as the class itself.
- Constructors don’t have a return type.
- A constructor is automatically called when an object is created.
- It must be placed in the public section of class.
- If we do not specify a constructor, C++ compiler generates a default constructor for object (expects no parameters and has an empty body).
- Constructors can be overloaded.
- Constructor cannot be declared virtual.


### 3: this Keyword

**Answer**: The **this** keyword refers to the current instance of class or the current object. The this keyword essentially allows you to access the attributes and methods of the current object

Example: consider a class 
```java
class Student{
    String studentRollNo;
    String studentName;
    int studentAge;
    float studentGPA;

    // All the Above fields Are Attributes
    Student(String studentRollNo,String studentName,int studentAge,float studentGPA){
        this.studentRollNo=studentRollNo;
        this.studentName=studentName;
        this.studentAge=studentAge;
        this.studentGPA=studentGPA;
    }
}
```
**Explanation** : Here if object is created as  Student stu1 = new Student("1","Deepak",23,8.53f); 
and then the constructor assignement would be stu1.studentRollNo=studentRollNo; -> stu1.studentRollNo="1"; 

#### Uses  of this Keyword:
    1. this can be used to refer current class instance variable.
    2. this can be used to invoke current class method (implicitly)
    3. this() can be used to invoke current class constructor.
    4. this can be passed as an argument in the method call.
    5. this can be passed as argument in the constructor call.
    6. this can be used to return the current class instance from the method.



### 5: Code for the Concepts covered above : 
```java
package org.example;

class Student{
    String studentRollNo;
    String studentName;
    int studentAge;
    float studentGPA;

    // All the Above fields Are Attributes
    Student(String studentRollNo,String studentName,int studentAge){
        this.studentRollNo=studentRollNo;
        this.studentName=studentName;
        this.studentAge=studentAge;
    }

    Student(String studentRollNo,String studentName,int studentAge,float studentGPA){
        this(studentRollNo,studentName,studentAge);
        this.studentGPA=studentGPA;
    }
    // Parameterized Constructor to initialize the attributes
    public void printStudentDetails(){
        System.out.println("Details of the Student are  : ");
        System.out.println("Name :" + this.studentName);
        System.out.println("Roll-No : "+this.studentRollNo);
        System.out.println("Age : " + this.studentAge);
        System.out.println("GPA : " + this.studentGPA);
    }

    // Method to perform specific Behaviour [In this case Print details]

}

public class Main {
    public static void main(String[] args) {
        Student Deepak = new Student("19-527","Deepak Varma",23,8.53F);
        Deepak.printStudentDetails();
    }
}
```

### 5: The main features of OOPs?

**Answer**: The main four pillar of oops are given below.

![pillar of OPPS](/assets/images/pillar_of_OOPS.png)


---

### 6: Inheritance

**Answer**: Inheritance is one of the most important features of Object-Oriented Programming. The capability of a class to derive properties and characteristics from another class is called Inheritance.


**Real Life Example**

<img src="/assets/images/inheritance.png" width="400" height="400">

There are 5 types of Inheritance:

    1. Single Inheritance
    2. Multiple Inheritance
    3. Multilevel Inheritance
    4. Hierarchical Inheritance.
    5. Hybrid Inheritance.

1. **Single Inheritance**: When a subclass(child) inherits a base class is called single inheritance.

```java
package org.example;

class Shape{
    String shapeName;

    public Shape(String shapeName) {
        this.shapeName = shapeName;
    }

    public void printShapeName(){
        System.out.println("The Shape is : " + this.shapeName);
    }
}

class Triangle extends Shape{

    double height;
    double base;

    public Triangle(String shapeName,double height,double base) {
        super(shapeName);
        this.height = height;
        this.base=base;
    }

    public double calculateArea(){
        return 0.5*height*base;
    }
}

public class Main {
    public static void main(String[] args) {
        Triangle triangle = new Triangle("triangle",3,5);
        triangle.printShapeName();
        System.out.println("The Area of the triangle is : " + triangle.calculateArea());
    }
}


```
**Output**
The Shape is : triangle
The Area of the triangle is : 7.5





2. **Multilevel Inheritance**: In this type of inheritance, a derived class is created from another derived class.

```java

package org.example;

class Animal{
    void eat(){System.out.println("eating...");}
}
class Dog extends Animal{
    void bark(){System.out.println("barking...");}
}
class BabyDog extends Dog{
    void weep(){System.out.println("weeping...");}
}

public class Main {
    public static void main(String[] args) {
        BabyDog d=new BabyDog();
        d.weep();
        d.bark();
        d.eat();
    }
}


```
**Output**
> Base class A \
weeping...
barking...
eating...



4. **Hierarchical Inheritance**: In this type of inheritance, more than one subclass is inherited from a single base class.

<img src="/assets/images/typesofinheritance.jpg" width="400" height="400">

```java
package org.example;

class Shape{
    String shapeName;

    public Shape(String shapeName) {
        this.shapeName = shapeName;
    }

    public void printShapeName(){
        System.out.println("The Shape is : " + this.shapeName);
    }
}

class Triangle extends Shape{

    double height;
    double base;

    public Triangle(String shapeName,double height,double base) {
        super(shapeName);
        this.height = height;
        this.base=base;
    }

    public double calculateArea(){
        return 0.5*height*base;
    }
}

class Circle extends Shape{
    double radius;
    Circle(String shapeName,double radius){
        super(shapeName);
        this.radius=radius;
    }
    public double calculateArea(){
        return 3.14*radius*radius;
    }

}

public class Main {
    public static void main(String[] args) {
        Triangle triangle = new Triangle("triangle",3,5);
        triangle.printShapeName();
        System.out.println("The Area of the triangle is : " + triangle.calculateArea());

        Circle circle = new Circle("Circle",5);
        circle.printShapeName();
        System.out.println("The Area of the Circle is : " + circle.calculateArea());
    }
}


```

**Output**
The Shape is : triangle
The Area of the triangle is : 7.5
The Shape is : Circle
The Area of the Circle is : 78.5




### 7: Encapsulation

**Answer**: 

- In normal term encapsulation is defined as wrapping up of data and information under a single unit.
- Encapsulation define as binding together the data and function that manipulates them.
- It Refers to [DATA-HIDING]

**Advantages**

- Increased security of data.
- Encapsulation allows access to a level without revealing the complex details below that level.
- It reduces human errors.
- Makes the application easier to understand.

**Real Life Example**

<img src="/assets/images/encapsulation.png" width="400" height="400">

```java

package org.example;

class Student{
    private String studentRollno;
    private String studentName;
    private float studentGPA;


    public String getStudentRollno() {
        return studentRollno;
    }

    public String getStudentName() {
        return studentName;
    }

    public float getStudentGPA() {
        return studentGPA;
    }

    public void setStudentRollno(String studentRollno) {
        this.studentRollno = studentRollno;
    }

    public void setStudentName(String studentName) {
        this.studentName = studentName;
    }

    public void setStudentGPA(float studentGPA) {
        this.studentGPA = studentGPA;
    }

    @Override
    public String toString() {
        return "Student{" +
                "studentRollno='" + studentRollno + '\'' +
                ", studentName='" + studentName + '\'' +
                ", studentGPA=" + studentGPA +
                '}';
    }
}


public class Main {
    public static void main(String[] args) {

        Student Deepak = new Student();
        Deepak.setStudentName("Deepak");
        Deepak.setStudentRollno("19E51A0527");
        Deepak.setStudentGPA(8.53f);

        System.out.println(Deepak);
    }
}


```

**Output**
Student{studentRollno='19E51A0527', studentName='Deepak', studentGPA=8.53}

---


### 8: Polymorphism

**Answer**: 

- The word polymorphism means having many forms. Polymorphism occurs when there is a hierarchical mode inheritance.



**Advantages**

Polymorphism allows us to reuse code by creating one function that’s usable for multiple uses. We can also make operators polymorphic and use them to add not only numbers but also combine strings. This saves time and allows for a more streamlined program.

**Real Life Example**

<img src="/assets/images/polymorphism.png" width="400" height="400">


There are 2 types of Polymorphism:

    1. Compile time Polymorphism
    2. Run time Polymorphism
   
1. **Compile time Polymorphism [STATIC]**: Compile-time polymorphism is a polymorphism that is, the function call is resolved during the compilation process.


**Method overloading**

- When there are multiple Methods with the same name but take different parameters as an arguments then these Methods are said to be overloaded.
- Methods can be overloaded by changing the number of arguments or and changing the type of arguments and or changing the return type of the methods.


```java
package org.example;

class Math{
    int add(int a , int b){
        System.out.println("Integer Addition of 2 numbers");
        return a+b;
    }

    double add(double a , double b){
        System.out.println("Double Addition of 2 numbers");
        return a+b;
    }

    int add(int a, int b, int c){
        System.out.println("Integer Addition of 3 numbers");
        return a+b+c;
    }
}

public class Main {
    public static void main(String[] args) {
        Math operations = new Math();
        System.out.println(operations.add(4,5));
        System.out.println(operations.add(4.2f,5.8f));
        System.out.println(operations.add(4,5,6));
    }
}


```

**Output**
Integer Addition of 2 numbers
9
Double Addition of 2 numbers
10.0
Integer Addition of 3 numbers
15




2. **Runtime Polymorphism [DYNAMIC]**

- Runtime polymorphism is also known as dynamic polymorphism or late binding. In runtime polymorphism, the Method call is resolved at run time.
- This type of polymorphism is achieved by Method Overriding.



```java
package org.example;

class Shape{
    String shapeName;

    public Shape(String shapeName) {
        this.shapeName=shapeName;
    }

    void calculateAndPrintArea(){
        System.out.println("Printing Area");
    }
}

class Triangle extends Shape{
    double base;
    double height;

    Triangle(String shapeName,double base,double height){
        super(shapeName);
        this.base = base;
        this.height = height;
    }

    void  calculateAndPrintArea(){
        double area = 0.5 * base * height;
        System.out.println("The Area of " + shapeName + " Is : " + area);
    }
}
public class Main {
    public static void main(String[] args) {
        Shape triangle = new Triangle("Triangle",3,4);
        triangle.calculateAndPrintArea();
    }
}


```

**Output**
The Area of Triangle Is : 6.0

---

**Final can be used to prevent overriding**


### 9: Acess Modifiers In Java 

<img src="/assets/images/AM.png" width="400" height="400">

### 10: Abstraction

**Answer**: 

- Data Abstraction is one of the most essential and important feature of Object Oriented Programming in c++.
- Abstraction means displays only the relevant attributes of objects and hides the unnecessary details like the background details and implementation.
- It refers to [IMPLEMENTATION-HIDING]

**Advantages**

- Helps user to avoid writing the low level code.
- Avoids code duplication and increases reusability.
- Helps to increase security of an application or program as only required details are provided to the user.

**Real Life Example**

<img src="/assets/images/abstraction.png" width="400" height="400">

```java
package org.example;

import java.util.StringJoiner;

abstract class Shape{
    String shapeName;

    Shape(String shapeName){
        this.shapeName = shapeName;
    }

    abstract double calculateArea();

    void printShapeName(){
        System.out.println("The Shape is : " + this.shapeName);
    }
}

class Circle extends Shape{
    double radius;
    Circle(String shapeName,double radius){
        super(shapeName);
        this.radius = radius;
    }
    @Override
    double calculateArea() {
        return 3.14 * radius * radius;
    }
}
public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle("Circle",2);
        circle.printShapeName();
        System.out.println(circle.calculateArea());
    }
}

```
**Output**
The Shape is : Circle
12.56

---

### 10: Abstract Classes 

**Answer** : 
An abstract class in Java is one that is declared with the abstract keyword. It may have both abstract and non-abstract methods(methods with bodies)

**Properties** : 
    1. An instance of an abstract class can not be created.
    2. Constructors are allowed.
    3. We can have an abstract class without any abstract method.
    4. There can be a final method in abstract class but any abstract method in class(abstract class) can not be declared as final  or in simpler terms final method can not be abstract itself as it will yield an error: “Illegal combination of modifiers: abstract and final”
    5. We can define static methods in an abstract class
    6. We can use the abstract keyword for declaring top-level classes (Outer class) as well as inner classes as abstract
    7. If a class contains at least one abstract method then compulsory should declare a class as abstract 
    8. If the Child class is unable to provide implementation to all abstract methods of the Parent class then 9. we should declare that Child class as abstract so that the next level Child class should provide implementation to the remaining abstract method

### 11: Interfaces 

**Answer** : 

- An interface in Java is a blueprint of a class. It has static constants and abstract methods.
- The interface in Java is a mechanism to achieve abstraction. 
- There can be only abstract methods in the Java interface, not method body. 
- It is used to achieve abstraction and multiple inheritance in Java.


### 11: Multiple Inheritance 

**Answer** : 
Java Supports Multiple Inheritance using the concept of Interfaces 

```java
package org.example;

import java.util.Collection;

interface Shape{
    double calculateArea();
    void displayShapeName();
}
interface Color{
    String getShapeColor();
}

class Circle implements Shape,Color{
    String shapeName;
    double radius;
    String shapeColor;

    Circle(String shapeName,double radius, String shapeColor){
        this.shapeName = shapeName;
        this.radius = radius;
        this.shapeColor = shapeColor;
    }
    @Override
    public double calculateArea() {
        return 3.14 * radius * radius;
    }

    @Override
    public void displayShapeName() {
        System.out.println("The Shape is :- " + shapeName);
    }

    @Override
    public String getShapeColor(){
        return shapeColor;
    }
}
public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle("Circle",2,"Purple");
        System.out.println("THe Color of the Shape is :  " + circle.getShapeColor());
        circle.displayShapeName();
        System.out.println(circle.calculateArea());
    }
}
```

**Output** 
THe Color of the Shape is :  Purple
The Shape is :- Circle
12.56

---


