---
sidebar_position: 1
---

# Welcome to Modular

Let's find out how to implement a Modular structure in your project.

## What is Modular?

Modular proposes to solve two problems:
- Modularized routes.
- Modularized Dependency Injection.

In a monolithic architecture, where we have our entire application as a single module, we design our software in a quick and
elegant way, taking advantage of all the amazing features of Flutterπ. However, producing a larger app in a "monolithic" way
can generate technical debt in both maintanance and scalability. With this in mind, developers adopted architectural strategies to better divide the code, minimizing the negative impacts on the project's maintainability and scalability..

By better dividing the scope of features, we gain:

- Improved understanding of features.
- Less breaking changes.
- Add new non-conflicting features.
- Less blind spots in the project's main business rule.
- Improved developer turnover.

With a more readable code, we extend the life of the project. See example of a standard MVC with 3 features(Auth, Home, Product):

### A typical MVC

    .
    βββ models                                  # All models      
    β   βββ auth_model.dart                     
    β   βββ home_model.dart                     
    β   βββ product_model.dart         
    βββ controller                              # All controllers
    β   βββ auth_controller.dart                     
    β   βββ home_controller.dart                     
    β   βββ product_controller.dart             
    βββ views                                   # All views
    β   βββ auth_page.dart                     
    β   βββ home_page.dart                     
    β   βββ product_page.dart                   
    βββ core                                    # Tools and utilities
    βββ app_widget.dart                         # Main Widget containing MaterialApp 
    βββ main.dart                               # runApp 


Here we have a default structure using MVC. This is incredibly useful in almost every application.

Let's see how the structure looks when we divide by scope: 


### Structure divided by scope

    .                  
    βββ features                                 # All features or Modules 
    β   ββ auth                                  # Auth's MVC       
    β   β  βββ auth_model.dart   
    β   β  βββ auth_controller.dart  
    β   β  βββ auth_page.dart                      
    β   ββ home                                  # Home's MVC       
    β   β  βββ home_model.dart   
    β   β  βββ home_controller.dart  
    β   β  βββ home_page.dart                        
    β   ββ product                               # Product's MVC     
    β      βββ product_model.dart   
    β      βββ product_controller.dart
    β      βββ product_page.dart                    
    βββ core                                     # Tools and utilities
    βββ app_widget.dart                          # Main Widget containing MaterialApp 
    βββ main.dart                                # runApp 



What we did in this structure was to continue using MVC, but this time in scope. This means that
each feature has its own MVC, and this simple approach solves many scalability and maintainability issues.
We call this approach "Smart Structure". But two things were still Global and clashed with the structure itself, so we created Modular to solve this impasse.

In short: Modular is a solution to modularize the route and dependency injection system, making each scope have
its own routes and injections independent of any other factor in the structure.
We create objects to group the Routes and Injections and call them **Modules**.



## Ready to get started?

Modular is not only ingenious for doing something amazing like componentizing Routes and Dependency Injections, it's amazing
for being able to do all this simply!

Go to the next topic and start your journey towards an intelligent structure.

## Common questions

- Does Modular work with any state management approach?
    - Yes, the dependency injection system is agnostic to any kind of class
     including the reactivity that makes up state management.

- Can I use dynamic routes or Wildcards?
    - Yes! The entire route tree responds as on the Web. Therefore, you can use dynamic parameters,
     query, fragments or simply include a wildcard to enable a redirect
     to a 404 page for example.

- Do I need to create a Module for all features?
    - No. You can create a module only when you think it's necessary or when the feature is no longer a part of
    the scope in which it is being worked on.


