# OOP in Java
> Collection of Java code examples and explanations covering OOP concepts.

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
