# OOP in Java
> Collection of Java code examples and explanations covering OOP concepts.

## Intro
**OOP stands for Object-Oriented Programming. It is a programming paradigm that organizes software design around objects, which are instances of classes. Here, we'll explore the basics of OOP in Java, including classes, objects, inheritance, polymorphism, and encapsulation.**  

In order to fully understand the main concepts of OOP,  it is importand to familiarize ourselves with Java classes and their components such as constructors, methods, access modifiers and objects. 

## Classes
In object-oriented programming (OOP), a class is a blueprint for creating objects. It defines the data and behavior that all objects of that type share. Classes are used to organize code and data, and to make code more reusable.

```java
public class MyClass {
    
}
```
## Methods
In Java, a method is a block of code that performs a specific task. The code inside of a method is executed when the method is called. It can accept input parameters, execute a sequence of statements, and optionally return a value.
```java
public class MyClass {
    public void myMethod() {
        // method body
    }

    public int myAgeMethod(int age) {
        // method body
        return age;
    }
}
```


## Main Method
The main method is a special method in Java that serves as the entry point for a Java application. When you run a Java program, it starts executing the code from the main method.
```java
public class MyClass {

    // main method
    public static void main(String[] args){  
        
    }
    
    
    
    // Normal methods
    public void myMethod() {
      
    }

    public int myAgeMethod(int age) {
        
        return age;
    } 
}
```

## Constructors
A constructor is a special method used to initialize objects of a class. It has the same name as the class and doesn't have a return type. The code inside a constructor will run whenever a object is created. We will discuss objects very soon. 

```java
public class MyClass {
    
    // Default Constructor
    public MyClass() {
        
    }
    // Parametarized Constructor
    public MyClass(int a, String b) {
        
    }

    // main method
    public static void main(String[] args){  
    
    }
    
    // Normal methods
    public void myMethod() {
      
    }

    public int myAgeMethod(int age) {
        
        return age;
    } 
}
```

## Fields
Fields are basically the variables declared within a class. 
```java
public class MyClass {
    int x = 0;
}
```

## Objects
An object is an instance of a class. In OOP a class describes the structure and behavior of an object. The class acts as a template or a blueprint for creating individual instances of that object.
Bellow code how an object is created. 

```java
// for default constructor
MyClass obj1 = new MyClass();

// for parameterized constructor
MyClass obj2 = new MyClass(25, 'Hello World');
```
## Working with multiple classes
In order to fully demonstrate the advantages of objects, it is very importand to learn working with multiple classes.

```java
public class Student {
    public String name;
    public int age;
    public int classRoll;

    public void printDetails(){
        System.out.println("Roll: "+classRoll+", Name: "+name+", Age: "+age);
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Student stud1 = new Student();
        Student stud2 = new Student();

        stud1.name = "Messi";
        stud1.age = 12;
        stud1.classRoll = 1;

        stud2.name = "Ronaldo";
        stud2.age = 15;
        stud2.classRoll = 2;

        stud1.printDetails();
        stud2.printDetails();
    }
}
```
*Output:*
```
Roll: 1, Name: Messi, Age: 12
Roll: 2, Name: Ronaldo, Age: 15
```
Same task can be done more cleanly with parametarized constructor. 
```java
public class Student {
    String name;
    int age;
    int classRoll;

    public Student(String name, int age, int classRoll) {
        this.name = name;
        this.age = age;
        this.classRoll = classRoll;
    }

    public void printDetails(){
        System.out.println("Roll: "+classRoll+", Name: "+name+", Age: "+age);
    }
}

```
```java

public class Main {
    public static void main(String[] args) {
        Student stud1 = new Student("Messi", 12, 1);
        Student stud2 = new Student("Ronaldo", 15, 2);

        stud1.printDetails();
        stud2.printDetails();
    }
}
```
*Output:*
```
Roll: 1, Name: Messi, Age: 12
Roll: 2, Name: Ronaldo, Age: 15
```
Or this same result can be achieved by just passing the values to `printDetails` method as arguments.
```java
public class Student {

    public void printDetails(String name, int age, int classRoll){
        System.out.println("Roll: "+classRoll+", Name: "+name+", Age: "+age);
    }
}

```
```java
public class Main {
    public static void main(String[] args) {
        Student stud1 = new Student();
        Student stud2 = new Student();

        stud1.printDetails("Messi", 12, 1);
        stud2.printDetails("Ronaldo", 15, 2);
    }
}
```
*Output:*
```
Roll: 1, Name: Messi, Age: 12
Roll: 2, Name: Ronaldo, Age: 15
```
So it is clear that using objects provides us with the flexibility to accomplish tasks in various ways.

## Access Modifiers
Access modifiers control the visibility or accessibility of class members (fields, constructors, and methods).  

There are four access modifiers in Java
- `public`: Members are accessible from anywhere.
- `private`: Members are only accessible within the same class.
- `protected`: Members are accessible within the same class, 
- Default (no modifier mentioned): Members are accessible within the same package.

```java
public class Example {
    public int publicVariable;
    private int privateVariable;
    protected int protectedVariable;
    int defaultVariable;
    

    public void publicMethod() {
        // Code accessible from anywhere
    }
    
    private void privateMethod() {
        // Code accessible within the same class only
    }

    protected void protectedMethod() {
        // Code accessible within the same package and subclasses
    }

    void defaultMethod() {
        // Code accessible within the same package
    }
    
}

```
## Static Variables

**In Java, static variables belong to the class rather than to objects or instances of the class. They are also known as class variables because they are shared among all objects or instances of the class.**

**So the `static` keyword means that every object shares the same variable, any changes to the static variable will be reflected in all objects.**

*Let's consider an example where we write a code that lists the names of children in a family, along with their corresponding numbers.*

```java
public class children {
    private String firstName;
    private String lastName;
    private  static int childNumber;

    public children(String fname, String lname){
        firstName = fname;
        lastName = lname;
        childNumber++;

        System.out.println("Child No."+childNumber+" : "+firstName+" "+lastName);
    }
}

```
```java
public class Main {
    public static void main(String[] args) {
        children obj1 = new children("Boro", "Chele");
        children obj2 = new children("Mejo", "Chele");
        children obj3 = new children("Choto", "Chele");
    }
}
```

*Output:*

```
Child No.1 : Boro Chele
Child No.2 : Mejo Chele
Child No.3 : Choto Chele
```

Here, whenever a new object of the Children class is created, the childNumber variable is incremented and keeps track of the number of children that have been created.. This is because the `childNumber` variable is static. 

Why `static` is useful here?   
Here is what happends if we write `private int childNumber` instead of `private  static int childNumber`:   
- Initially `childNumber` is 0. For `Obj1` it becomes 1.
- On the second object the same thing happens. It starts from 0 and `Obj2` makes it 1.  
- It resets because it isn't static. Static fixes this issue. Without static every Child No. would show 1. 


## Static Methods
**In Java, similar to static variable a static method is a method that belongs to a class rather than an instance of a class. It can be accessed directly through the class name, without the need to create an object of that class.**

*For Example,*

```java
public class greetings {
    public static void morningGreeting(){
        System.out.println("Good Morning");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
       greetings.morningGreeting();
    }
}
```
*Output:*
```
Good Morning
```

## Encapsulation
Encapsulation means the combining of variables and code methods into a single unit. Encapsulation hides a class's variables from other classes and allows them to be accessed only by the methods of the class in which they are found.
<!-- ## Inheritence -->
## Polymorphism
## Final Keyword
## Method overloading
## Method overriding
## Abstract and Interface
## Exception Handling
## Thread
