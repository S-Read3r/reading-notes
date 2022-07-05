# Component Based Architecture

Welcome to the Component Based Architecture (CBA) course.

What is a Component Based Architecture?

A component based architecture is a software architecture that is built around the concept of components. To further simplify the concept, a component is a piece of code, for example a class, that solves some of the application's functional requirements.
    * The work done by a component is called the **service** of the component.
    * The work done by a component is application specific.
The container is a framework that solves some of the application's non-functional requirements.
    * The work done by a container is independent of the application.
    * The same container can be used to solve multiple applications.

# Why component Architecture?

* Not using an existing framework means writing new code which means introducing new bugs.
* Decrease of the need for in-house development means less time spent on in-house development.
* Also, non-functional requirements are difficult to code.
    * The container can be used to solve these non-functional requirements.
    * The container can be used to solve multiple applications.
    * The container can be used to solve multiple non-functional requirements.
    * The container can be used to solve multiple applications and multiple non-functional requirements.

The component when used outside the container(framework) has to know the flow of the code. 
This is different from the component when used inside the container(framework).
Since it will be the container calling the component, the component will not know the flow of the code. The container (being a framework) must know when to perform a security check etc, unlike the component without the container which will be calling an API and will have to know when to perform a security check etc.

## How does CBA work?

* Component: A piece of code that solves some of the application's functional requirements.
           - a program building vlock for an application.
           - presents a manageble, discrete chunk of logic (functionality) to the application.
            - Example: a class that implements the `Vlock` interface, which is the interface that the application uses to interact with the vlock.
            - Example 2: pricing component that calculates the price of a product.
            - Example 3: billing component that calculates the bill of a customer.

* Container: A framework that solves some of the application's non-functional requirements.
            - an application program or a subsystem in which the components lives;
            - Component's context;
            - creates, manages and "glues" components together by calling the appropriate components at the appropriate times.
            - Provides life cycle management, security, deployment, and runtinme services for components it contains (components contact).
            - It is the container that manages the life cycle of the components.

## Where do containers live?

* Application Server: A server that runs the application.
                - Container live in an application server.
                - The application server provides the runtime environment for the container.
                - Provides containers and services for applications made of componentsl. 
                    * Services: management, thread pools, network communication, etc.
                - Commonly Used Application Servers: Tomcat, JBoss, Glassfish, Node.js(JavaScript), Apache, NGIX(PHP), Zope, Django(Python) etc.

## Development and Deployment (IDE)

* Development tools: A tool that allows you to develop and deploy your application.
                    - A development tool is a software tool that allows you to develop and deploy your application.
                    - Commonly Used Development Tools: Visual Studio, Eclipse, Netbeans, IntelliJ IDEA, etc.

* Deployment: A process that allows you to deploy your application.
              - A deployment process is a process that allows you to deploy your application.
              - for configuration and deploying components.
                * Application server's management tools.
                * Contanerization (docker, kubernetes, etc).

### Views of a Component

A component can have three different views - object oriented view, conventional view and process related view.

1. Object-oriented view

A component is viewed as a set of one or more cooperating classes. Each problem domain class (analysis) and infrastructure class(design) are explained to identify all attributes and operations that apply to its implementation. It also involves defining the interfaces that enable the classes to interact with each other.


2. Conventional view

It is viewed as a functional element or a module of a program that integrates the processing logic, the internal data structures that are required to implement the processing logic and an interface that enable the component to be invoked and data to be passed to it.

3. Process related view

In this view, instead of creating each component from scratch, the system is building from existing components maintained in a library. As the software architecture is formulated, componets are selects from the library and are used to build the system.

    - A UI component includes grids, buttons referred as controls, and utility components expose a specific subset of functions used in other components.
    - other common type of componets are those that are resouce intensive, not frequiently accessed, and must be activated only when needed or using the just-in-time (JIT) approch.
    - Many components are invisible which are distributed in enterprose busines applications and internet web applications such Enterprise JavaBean (EJB), .NET components, anf COBRA components.


## What are the Characteristics of a Component?

* Reusability: Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task. 
* Replaceability: Components may be freely substitued with other similar components.
* Modularity: Components may be used in different applications.
* Extensibility: Components may be extended to support new functionality.
* Encapsulation: Components may be used to hide the implementation details of the functionality.
* Security: Components may be used to protect the integrity of the application.
* Independence: Components are designed to have minimal dependencies on other components.