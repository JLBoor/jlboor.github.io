---
layout: post
title: "AngularJS best practices - Controllers"
excerpt: "This post explains what are the best practices when you are writing controllers in AngularJS 1.x"
categories: angularjs
tags: [angularjs, best practices, javascript, controllers, 1.x]

comments: true
share: true
---

Second post in this AngularJS best practices series; this article will .. bla bla bla...

Although, before we even start talking about best practices, it's important to understand what is a controller in the AngularJS world.

## What is a controller?

> A controller is constructor used to augment the *$scope* and that contains the business logic for a single view.

And that's it! Here are almost all our best practices.

### Do
- set up the initial state of the *$scope* for a **single view**
- add behavior to the *$scope* for a **single view**
- add the business logic needed for a **single view**


### Don't
- don't try to do too much.
- don't manipulate DOM
- don't format input
- don't filter output
- don't share code or state across controllers
- don't manage the life-cycle of other components



Angular Scope: the glue between application controller and the view.


**Next:** [{{ page.next.title }}]({{ site.url }}{{ page.next.url }})