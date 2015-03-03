---
layout: post
title: "How to use promises in AngularJS"
excerpt: "In this post we are show how to use promises in AngularJS 1.x as well as the common pitfalls."
categories: angularjs
tags: [angularjs, promises, javascript, $q]

comments: true
share: true
---

[$http]: https://docs.angularjs.org/api/ng/service/$http
[$resource]: https://docs.angularjs.org/api/ngResource/service/$resource

In this blog post I'll show how to use promises with AngularJS. First, I'm going to describe a few anti-patterns I've seen and then I'll move on to the core ideas of promise.

## Anti-Patterns

So, what’s wrong with this code ?

{% highlight js linenos=table  %}
var getLatestNews = function () {
        var deferred = $q.defer();
        $http.post('http://echo.jsontest.com/news/intelliware').then(function(httpResponse){
            deferred.resolve(httpResponse);
        });
        return deferred.promise;
    },
    refreshNewsList = function (httpResponse) {
        var deferred = $q.defer();
        $scope.news = httpResponse.data.news;
        deferred.resolve($scope.news);
        return deferred.promise;
    },
    errorHandler = function(err) {
        alert(err);
    };
    getLatestNews(errorHandler)
        .then(refreshNewsList)
        .then(null, errorHandler);
{% endhighlight %}

Well, a few things:

**Line 2-6:** Creating a promise when using the [$http] API is pointless. The service is already returning a promise.

**Line 9-12:** Same problem, different reason. Here there's no need to create a promise because the *.then* function will always return a new promise (by definition)

**Line 19:** Instead of using the hack *.then(null, errorHandler)* to intercept an error, you should use *.catch(errorHandler)*. I used the word hack because it's getting around the transition rules.

## Definition

You have to understand that promises are about something much deeper than callback aggregation. Indeed, it's more about providing a direct correspondence between synchronous functions and asynchronous functions.

Essentially, the point of promises is to give functional composition and error bubbling in the asynchronous world. So, it leads me to 2 fundamental properties of the promises:

1. A promise will always return a new promise. It means that you can directly chain promises. You don't have to explicitly create a new promise every time you want to chain two calls.
2. A promise is rejected when an exception is thrown. Basically, if an exception is thrown the chain will be interrupted until the exception is caught. There's no need to define an error handler for every call.

By the way, it's also important to know that a promise can be in 3 different states only: *pending, fulfilled, rejected*. And that the transition rules are:

* When pending, it may transition to either the fulfilled or rejected state.
* When fulfilled or rejected, a promise can NOT transition to any other state.

#### Example:

Here, an example that illustrates the different points I just described.

{% highlight js linenos=table  %}
var singIn = function () {
       return $http.post('http://validate.jsontest.com/?json={"key":"value"}');
    },
    saveLocation = function () {
       return $http.post('http://validate.jsontest.com/?json={"key":"value"}');
    },
    getLatestNews = function () {
        return $http.get('http://echo.jsontest.com/news/intelliware');
    },
    refreshNewsList = function (httpResponse) {
       $scope.news = httpResponse.data.news;
        return $scope.news;
    },
    displayWelcomeMessage = function (news) {
       $scope.welcome = 'You have ' + news.length + ' new messages';
    },
    errorHandler = function(err) {
        alert(err);
    };
    singIn()
        .then(saveLocation)
        .then(getLatestNews)
        .then(refreshNewsList)
        .then(displayWelcomeMessage)
        .catch(errorHandler);
{% endhighlight %}

**Line 2, 5, 8:** No need to create a promise using $q.defer() because the [$http] service already returns a promise.

**Line 12, 23, 24:** Even though the refreshNewsList doesn't explicitly return a promise, based on the definition the then will do it. That's why we can still chain the calls.

**Line 25:** If an error occurs, it will execute errorHandler. There's no need to specify the handler for every every step!

## Conclusion

Using promises with Angular isn't really difficult. You just need to understand the real motivations. So keep in mind that a promise:

* has a **then** method that **returns a new promise**
* is **fulfilled** when the callback **is finished**
* goes to the **failed state when an exception is thrown**
* is about **functional composition** and **error bubbling**

To go further, I suggest you have a look at the [$http] and [$resource] services as they are based on the promise API but also offer specific methods.
