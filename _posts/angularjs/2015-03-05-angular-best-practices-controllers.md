---
layout: post
title: "AngularJS best practices - Controllers"
excerpt: "This post explains what are the best practices when you are writing controllers in AngularJS 1.x"
categories: angularjs
tags: [angularjs, best practices, javascript, controllers, 1.x]

comments: true
share: true
draft: true
---

What is a controller?

- a JavaScript constructor that is used to augment the Angular Scope.
- shouldn't try to do too much. It should contain only the business logic needed for a single view
- Set up the initial state of the $scope
- Add behavior to the $scope


Angular Scope: the glue between application controller and the view.

- Don't Manipulate DOM
- Don't Format input
- Don't Filter output
- Don't Share code or state across controllers
- Don't Manage the life-cycle of other components