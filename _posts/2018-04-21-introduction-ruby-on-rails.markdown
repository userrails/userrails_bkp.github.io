---
layout: post
title:  "Introduction - Ruby on Rails!"
date:   2018-04-21 09:23:58 +0545
categories: tutorials
---
Rails is a web development framework written in the Ruby programming language. It makes web application development more fun.

Rails Design Principles:
- MVC (Model, View, Controller)

  MVC pattern splits an application into three modules a Model, View and Controller. There is "separation of the concerns" among Models, Views and Controllers as each parts has it's own responsibility.

  Model

  Model is the layer which interact with the database to retrieve and store the data. You can define the classes in model layer which is used by the application. e.g: `Article` model is created when you want to create article for blog. It maintains the relationship between the objects and the database and handles validation, association, transaction and more.

  View

  View layer is the presentation layer which is used to return relevant HTML to be rendered on the users browser.

  Controller

  The controller interacts with the model to retrieve and store data. The retrived data from model will pass to the view. The view returns the resulting HTML to the controller and the controller send this back to the users browser. 

- DRY - Don't Repeat Yourself
  
  In this principle developer have to reduce repetition of codes so that code should be more maintainable, more extensible, less buggy.

- Convention over Configuration
  
  This principle allows developer to use default logics and rules used by the framework so that application can be developed in very less time using very few lines of code. For example: if model `Customer` is generated then corressponding database table generated would be `Customers` unless developer configure another name.