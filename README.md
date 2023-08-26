
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

**Explanation** : Here if object is created as  Student stu1 = new Student("1","Deepak",23,8.53f); 
and then the constructor assignement would be stu1.studentRollNo=studentRollNo; -> stu1.studentRollNo="1"; 

#### Uses  of this Keyword:
  1.this can be used to refer current class instance variable.
  2.this can be used to invoke current class method (implicitly)
  3.this() can be used to invoke current class constructor.
  4.this can be passed as an argument in the method call.
  5.this can be passed as argument in the constructor call.
  6.this can be used to return the current class instance from the method.



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

