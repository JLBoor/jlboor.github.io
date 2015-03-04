---
layout: post
title: "AngularJS best practices - Introduction"
excerpt: "This post is an introduction to a bunch of best practices in AngularJS 1.x"
categories: angularjs
tags: [angularjs, best practices, javascript, introduction, 1.x]

comments: true
share: true
---

This blog post is the first in a series about best practices in AngularJS.
The purpose of this introduction is to explain why defining the right standards for your project is so crucial.


## First, let's face it... Javascript sucks!

![Image showing the massive JS definition book, and just beside the tiny JS the good parts](/images/angularjs/javascript-sucks.jpg "Definition vs. The Good Parts")

- Lack of module system
- Weak-typing
- Finicky equality/automatic conversion
- The keyword this is ambiguous, confusing and misleading
- Semi colon insertion
- Implied global declaration
- And so on...


### Example 1: *hoisting in JavaScript*

{% highlight js linenos=table  %}
var x = 'Hello';
var y = 'World';

(function() {
    console.log(x);
    console.log(y);

    var y = '!';

    console.log(y);
})();
{% endhighlight %}

Surprisingly, the result isn't

{% highlight js %} Hello World ! {% endhighlight %}

nor
{% highlight js %} Hello !! {% endhighlight %}

but instead
{% highlight js %} Hello undefined ! {% endhighlight %}

The reason is that in Javascript, not only all the declarations are moved to the of the current scope, but the assignments are left in place. That's why the result is so bizarre.

What really happens at runtime is

{% highlight js linenos=table  %}
(function() {
    var y = undefined;
    console.log(x);
    console.log(y);

    y = '!';

    console.log(y);
})();
{% endhighlight %}



### Example 2: *Comparison craziness*

{% highlight js %}
var x = [0];
console.log(x == x) // true
console.log(x == !x) // true
{% endhighlight %}

{% highlight js %}
console.log(0.1 + 0.2 === 0.3) // false
{% endhighlight %}

{% highlight js %}
console.log(true + true) // 2
{% endhighlight %}

And we can keep going for hours...

With AngularJS being a Javascript framework, we obviously have to understand how the language works, but not only, we also have to understand what's AngularJS trying to achieve and how.


## The philosophy AngularJS

Before we start talking about best practices, let's step back a little and review what the essence of AngularJS is.
Below a selection of comments found on [https://docs.angularjs.org](https://docs.angularjs.org/guide/introduction).

- It's a very good idea to decouple DOM manipulation from app logic
- It's a really, **really** good idea to regard app testing as equal in importance to app writing
- Testing difficulty is dramatically affected by **the way the code is structured**
- It's always good to **make common tasks trivial** and difficult tasks possible

Buzzworthy, 2 items out of 4 are talking about testability... And that's going to be my first tip, no one shall approve a pull request that does not contain unit tests.

## What's next?

Well, first the good news! For the Javascript part, you can write safer code by using tools existing tools, and they should probably be already part of your build.
The bad news though, there's no such thing for AngularJS. That's why having standards & best practices is so important.


**Next:** [{{ page.next.title }}]({{ site.url }}{{ page.next.url }})