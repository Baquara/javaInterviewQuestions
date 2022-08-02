In a Java class, a static block is a set of instructions that is run only once when a class is loaded into memory. A static block is also called a static initialization block. This is because it is an option for initializing or setting up the class at run-time.
In Java, a static method is a method that belongs to a class rather than an instance of a class. The method is accessible to every instance of a class, but methods defined in an instance are only able to be accessed by that object of a class.

Multithreading is a Java feature that allows concurrent execution of two or more parts of a program for maximum utilization of CPU. Each part of such program is called a thread. So, threads are light-weight processes within a process.

# Abstract classses and interfaces

## Abstract Classes

An abstract class is a class that cannot be instantiated. Abstract classes can contain both abstract and concrete methods. An abstract method is a method that is declared, but not implemented in the code. A concrete method is a method that is declared and implemented in the code. Abstract classes must be subclassed in order to be used.

Abstract classes are used to provide a common base class for a group of classes. They are also used to provide default implementations of methods that can be overridden by subclasses.

Abstract classes are classes that cannot be instantiated, but can be subclassed. 

Abstract classes are typically used to define a base class from which other classes can inherit. For example, an abstract class might define a basic shape, with subclasses defining specific shapes like circles, squares, and triangles.

Final method is a method that is marked as final, i.e. it cannot be overridden anymore. Just like final class cannot be inherited anymore.

Abstract method, on the other hand, is an empty method that is ought to be overridden by the inherited class. Without overriding, you will quickly get compilation error.



## Interfaces

An interface is a type that can be implemented by a class. Interfaces define a set of methods that must be implemented by any class that implements the interface.

Interfaces are used to define a contract that must be followed by any class that implements the interface. They are also used to provide a level of abstraction between classes.

An interface is a contract between a class and its subclasses that specify what methods must be implemented by the subclasses.

Interfaces are typically used to define a set of methods that must be implemented by a class. For example, an interface might define a set of methods for sorting data. A class that implements the interface would then need to provide implementations for those methods.

Java 8 has introduced the concept of default methods which allow the interfaces to have methods with implementation without affecting the classes that implement the interface.

# Java Access Modifiers

Java has four access modifiers: public, protected, private, and default.

Public members are accessible from anywhere. Protected members are accessible from within the same package, as well as from subclasses. Private members are only accessible from within the same class. Default members are only accessible from within the same package.

Protected means that the member can only be accessed by classes in the same package or subclasses in a different package. Default means that the member can only be accessed by classes in the same package.

# OOP Paradigms

There are three major OOP paradigms:

1. Encapsulation: This is the most basic principle of OOP. It involves keeping data and code together in an object, and hiding the implementation details from the outside world. This allows for code reuse and makes code more maintainable.

2. Inheritance: This is a powerful feature of OOP that allows one object to inherit the properties of another. This can be used to create hierarchical class structures, and to reuse code.

3. Polymorphism: This is the ability of an object to take on different forms. This can be achieved through overloading or overriding methods, or by using interfaces.

#REST

GET - Used to request data from a specified resource

POST - Used to send data to a specified resource to be processed

PUT - Used to send data to a specified resource to be updated

DELETE - Used to request that a specified resource be deleted

## Annotations

There are four main annotations in Spring: @Component, @Repository, @Service, and @Controller. These annotations are used to mark classes as Spring beans, which are then managed by the Spring framework.

@Component - is the most general annotation and can be used for any type of class. 

@Repository - is used for classes that perform data access operations. 

@Service - is used for classes that provide business services. 

@Controller -  is used for classes that are part of the Spring MVC framework.

@Configuration - is used by Spring to designate a class as a configuration class. This class can be used to define beans and resolve dependencies.

Each of these annotations has a corresponding XML element that can be used for configuring Spring beans.


| Sr. No. | Key | @Bean | @Component |
| --- | --- | --- | --- |
| 1 | Auto detection | It is used to explicitly declare a single bean, rather than letting Spring do it automatically.  | If any class is annotated with @Component it will be automatically detect by using classpath scan. |
| 2 | Spring Container | Bean can be created even class is outside the spring container | We can’t create bean if class is outside spring container |
| 3 | Class/Method  Level Annotation | It is a method level annotation | It is a class level annotation |
| 4 | @Configuration | It works only when class is also annotated with @Configuration | It works without@Configuration annotation |
| 5 | Use Case | We should use @bean, if you want specific implementation based on dynamic condition. | We can’t write specific implementation based on dynamic condition |

## Spring bean

A Spring bean is a Java object that is managed by the Spring IoC container (Inversion of Control is a principle in software engineering which transfers the control of objects or portions of a program to a container or framework). It is created and initialized during the container startup, and can be injected into other beans that are managed by the container.

For example, the following bean definition will create a bean with the name "myBean" and the class "MyBean":

```
<bean id="myBean" class="MyBean">
```

The following example shows how to inject a Spring bean into another bean:

```
<bean id="myDependency" class="MyDependency">

<bean id="myBean" class="MyBean">

<property name="myDependency" ref="myDependency"/>

</bean>
```

## Dependency Injection

Dependency injection is a technique for passing dependencies to a class through its constructor or setter methods. This allows the dependencies to be injected at runtime, rather than being hard-coded into the class.

Spring uses dependency injection to provide dependencies to its beans. When a Spring bean is created, its dependencies are injected into it. This allows the beans to be decoupled from their dependencies, and makes it easy to change the dependencies without changing the beans.

In case of Field-Based DI, we can inject the dependencies by marking them with an @Autowired annotation:

public class Store {
    @Autowired
    private Item item; 
}

## Spring Security

Spring Security is a framework for providing security to Java applications. It offers a number of features, including authentication, authorization, and access control. Spring Security can be used to secure web applications, REST services, and even individual methods.

Configuring Spring Security is typically done using XML or Java configuration. Spring Security can be configured to use a number of different authentication providers, including LDAP, database, and Active Directory.

## Spring MVC vs Spring Boot

Spring MVC is a framework for building web applications. It handles all of the request and response processing, and provides a number of features for building maintainable and extensible web applications.

Spring Boot is a framework for building production-ready applications. It provides a number of features, including an embedded Tomcat server and auto-configuration. Spring Boot is designed to be used in conjunction with an application server, such as WildFly or Tomcat.


## Design Patterns

There are four main design patterns in Java: Singleton, Factory, Decorator, and Observer.

The Singleton pattern is used to ensure that only one instance of a class is created. The Factory pattern is used to create objects without exposing the logic for creating them. The Decorator pattern is used to add new functionality to existing objects. The Observer pattern is used to notify objects of changes to another object.

On the Singleton pattern, in a multi-threaded environment, only one instance of the class created, and it is shared among all threads (it gets the instance from the first thread it is created). Since the instance of the other threads are not used, the memory occupied by those instances can be reclaimed by the garbage collector. Garbage collection is a process of reclaiming the memory occupied by objects that are no longer needed by the application.


Singleton:

public class Coin {

    private static final int ADD_MORE_COIN = 10;
    private int coin;
    private static Coin instance = new Coin(); // eagerly loads the singleton

    private Coin() {
        // private to prevent anyone else from instantiating
    }

    public static Coin getInstance() {
        return instance;
    }

    public int getCoin() {
        return coin;
    }

    public void addMoreCoin() {
        coin += ADD_MORE_COIN;
    }

    public void deductCoin() {
        coin--;
    }
}



The Factory Pattern:

    public class Factory {

       // An abstract factory has multiple methods that return
       // different abstract products

       public abstract Product1 createProduct1();

       public abstract Product2 createProduct2();

    }


The Observer Pattern:


public class Main {
  
    public static void main(String[] args) {
        
        // create subject
        MyTopic topic = new MyTopic();
 
        // create observers
        Observer obj1 = new MyTopicSubscriber("Obj1");
        Observer obj2 = new MyTopicSubscriber("Obj2");
        Observer obj3 = new MyTopicSubscriber("Obj3");
 
        // register observers to the subject
        topic.register(obj1);
        topic.register(obj2);
        topic.register(obj3);
 
        // attach observer to subject
        obj1.setSubject(topic);
        obj2.setSubject(topic);
        obj3.setSubject(topic);
 
        // check if any update is available
        obj1.update();
 
        // now send message to subject
        topic.postMessage("New Message");
    }
}


The Decorator pattern:



public class DecoratorPattern {
  
    public static void main(String[] args) {
        Car sportsCar = new SportsCar(new BasicCar());
        sportsCar.assemble();
        System.out.println("\n*****");
         
        Car sportsLuxuryCar = new SportsCar(new LuxuryCar(new BasicCar()));
        sportsLuxuryCar.assemble();
    }
  
}


## Java 8 vs Java 11

There are a number of significant changes between Java 8 and Java 11. Some of the most notable changes include:

- The removal of the Java EE and CORBA modules
- The addition of a new module, java.se.ee, which includes all the Java EE and CORBA modules
- The introduction of a new release cycle, where a new major release occurs every six months
- The introduction of a new tool, jlink, which can create a custom runtime image containing only the modules required for a particular application
- The addition of support for HTTP/2
- The addition of a new default garbage collector, Garbage First (G1)
- The addition of a new JVM, GraalVM, which can run applications written in a variety of languages
- The addition of support for the Java Platform Module System (JPMS)

### What Java 8 originally introduced?

Write the most important additions from Java 8.




- Lambda expressions
- Stream API
- Date and time API
- Default methods
- Optional class

Write an example of Java Lambda expressions.

(x, y) -> x + y

Write an example of Java Stream API

list.stream()
    .filter(x -> x % 2 == 0)
    .map(x -> x * x)
    .forEach(System.out::println);


This code filters a list of numbers, keeping only the even numbers. It then squares each of the remaining numbers, and finally prints them out.

What Java 8 default method does?

Java 8 default methods are methods in interfaces that have a default implementation. This allows for new methods to be added to interfaces without breaking existing code that implements the interface.

What is an Optional class?


The Optional class is a container class that represents a value that may or may not be present. It is used to avoid NullPointerException errors.

Write an example of the Date and time API.


LocalDateTime dt = LocalDateTime.now();
System.out.println(dt);

This code creates a LocalDateTime object that represents the current date and time.

Write what is the Java Stream API.

The Java Stream API is a set of tools that allow developers to manipulate collections of data in a declarative way. This can be used to perform operations such as filtering, mapping, and reducing.

Write an example of an Optional class.


Optional<String> str = Optional.of("Hello");
System.out.println(str.isPresent());

This code creates an Optional object that contains the string "Hello". The isPresent() method is used to check if the Optional object contains a value.

Write a code using the default method.


public interface MyInterface {
    default void doSomething() {
        System.out.println("Doing something");
    }
}

public class MyClass implements MyInterface {
    public static void main(String[] args) {
        MyClass myClass = new MyClass();
        myClass.doSomething();
    }
}

This code implements an interface that has a default method. The MyClass class then calls the doSomething() method.
    
    
    
    
 what is event loop in js?
    
two sum  leetcode
    
**can constructor be private?**
    
**design a singleton**
    
**1. OOP: inheritance, polymorphism, abstraction**
    
**2. Spring and Hibernate**
    
**3. Singleton, observer, etc**
    
**What is CI/CD and DevOps?**
    
**Consider a program to remove duplicate characters**
    
**Questions on collection**
    
**throw vs throws**
    
**types of interface**
    
**How to delete all duplicate elements in a list and keep the list order unchanged.**
    
What is the purpose of static methods and variables?
    
What Is Factory Pattern?
    
What design pattern do you know? 
    
(1)oops concept
    
(2)Singleton
    
(3) Spring Framework
    
(4)Spring beans
    
(5)collection framework
    
Explain java collections, you can say as much as you want.
    
And concept of constructors and so on
    
How to sort data
    
What is Spring MVC
    
1)what is Singleton? and how can you implement
    
2)Hash Map?
    
3)Interface vs Abstract class?
    
4)Exception Handling?
    
Heap Memory
    
what is the difference between supervised learning and unsupervised learning
    
Java Core, Collection, Multithreading, Design Pattern, etc
    
Spring Framework concepts like IoC container, Annotations
    
Servlet concept, Database query concept, etc
    
Find all pairs in array that sum up to given number
    
Types of stlc, defect life cycle, debugging in JAVA, oops concept, applying different types of waits in selenium, type of models in SDLC. 
    
Hashmap, ArrayList vs LinkedList, static, singleton
    
In java, what is the difference between list and arraylist?
    
difference between comparator and comparable
    
Data Science: Case study , random forest, decision tree, logistic algorithm 
    
1) What are lambda expressions? Why are they used?
    
2) What is a functional interface?
    
3) What are the features of Java 7?
    
4) How is I18N implemented in spring boot?
    
5) How do you externalize properties in spring boot?
    
6) What will happen if you override equals but not hashcode?
    
7) Have you used Kafka?
    
8) Have you used ESB?
    
How to implement Singleton?
    
Final vs finally vs finalize
    
HashMap structure
    
What is HashCode?
    
Hashcode vs equals
    
Do you know JSP Hibernate etc?
    
Basic Java, OOPs,  LinkedList, HashMaps, etc.
    
overload vs override
    
what is an interface
    
Difference between Synchronized block and method?
    
What is the difference between abstraction class and interface.
    
What is static keyword.
    
1) What you mean by Inheritance?
    
2) What you mean by Abstract method?
    
3) Can we have a class without public?
    
4) Can we have a private class? How will you access the properties of that class?
    
5) How will you handle the exception without using try-catch block?
    
What is encapsulation?
    
What is arraylist?
    
Tell me the difference between method and constructor.
    
What's the difference between abstract class and interface?
    
What is exception?
    
What's the diff between override and overload?
    
what is different among private, public and protect? 
    
what is synchronized in Java?
    
What's the different between Object and Class?
    
What is the difference between errors and exceptions?
    
What is the difference between HashMap and HashTable?
    
Can you discribe collections in Java?
    
Can you discribe LinkedList in Java?
    
fibonacci series
    
Giving you an ArrayList that stores integer, find out the max and min value.
    
- Singleton, Facade and Factory design pattern
    
- What's dynamic binding?
    
In Java, what is an static variable?
