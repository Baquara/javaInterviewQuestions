# Spring Framework

## Annotations

There are four main annotations in Spring: @Component, @Repository, @Service, and @Controller. These annotations are used to mark classes as Spring beans, which are then managed by the Spring framework.

@Component is the most general annotation and can be used for any type of class. @Repository is used for classes that perform data access operations. @Service is used for classes that provide business services. @Controller is used for classes that are part of the Spring MVC framework.

Each of these annotations has a corresponding XML element that can be used for configuring Spring beans.

## Spring bean

A Spring bean is a Java object that is managed by the Spring IoC container. It is created and initialized during the container startup, and can be injected into other beans that are managed by the container.

For example, the following bean definition will create a bean with the name "myBean" and the class "MyBean":

<bean id="myBean" class="MyBean">

The following example shows how to inject a Spring bean into another bean:

<bean id="myDependency" class="MyDependency">

<bean id="myBean" class="MyBean">

<property name="myDependency" ref="myDependency"/>

</bean>

## Dependency Injection

Dependency injection is a technique for passing dependencies to a class through its constructor or setter methods. This allows the dependencies to be injected at runtime, rather than being hard-coded into the class.

Spring uses dependency injection to provide dependencies to its beans. When a Spring bean is created, its dependencies are injected into it. This allows the beans to be decoupled from their dependencies, and makes it easy to change the dependencies without changing the beans.

## Spring Security

Spring Security is a framework for providing security to Java applications. It offers a number of features, including authentication, authorization, and access control. Spring Security can be used to secure web applications, REST services, and even individual methods.

Configuring Spring Security is typically done using XML or Java configuration. Spring Security can be configured to use a number of different authentication providers, including LDAP, database, and Active Directory.

## Spring MVC vs Spring Boot

Spring MVC is a framework for building web applications. It handles all of the request and response processing, and provides a number of features for building maintainable and extensible web applications.

Spring Boot is a framework for building production-ready applications. It provides a number of features, including an embedded Tomcat server and auto-configuration. Spring Boot is designed to be used in conjunction with an application server, such as WildFly or Tomcat.

## Java Access Modifiers

Java has four access modifiers: public, protected, private, and default.

Public members are accessible from anywhere. Protected members are accessible from within the same package, as well as from subclasses. Private members are only accessible from within the same class. Default members are only accessible from within the same package.

## Abstract Classes

An abstract class is a class that cannot be instantiated. Abstract classes can contain both abstract and concrete methods. Abstract classes must be subclassed in order to be used.

Abstract classes are used to provide a common base class for a group of classes. They are also used to provide default implementations of methods that can be overridden by subclasses.

## Interfaces

An interface is a type that can be implemented by a class. Interfaces define a set of methods that must be implemented by any class that implements the interface.

Interfaces are used to define a contract that must be followed by any class that implements the interface. They are also used to provide a level of abstraction between classes.

## Design Patterns

There are four main design patterns in Java: Singleton, Factory, Decorator, and Observer.

The Singleton pattern is used to ensure that only one instance of a class is created. The Factory pattern is used to create objects without exposing the logic for creating them. The Decorator pattern is used to add new functionality to existing objects. The Observer pattern is used to notify objects of changes to another object.
