---
layout: post
title: "Changing the web with Web Components"
excerpt: ""
categories: frontend
tags: []

comments: true
share: true
---


*This article is an introduction of a series of posts related to the Web Components and Polymer. In the following posts, we'll dive into Polymer specifically.*

To help companies build great User Experience (UX) and consistent User Interfaces (UI), we traditionally provide branding, style guides and wireframes. But that does not scale and rapidly hits certain limitations. 

Today, it seems that the cost of consistency, unfortunately, is re-building the same piece of UI for each platform. This obviously creates more technical and design debt.

This post will introduce a technology that has been on the developers' radar for quite some time and that addresses these consistency and reusability challenges: Web Components.

## What are Web Components?

The idea of Web Components is that you no longer depend on the browser to provide you with native elements. You can build you own! And that's very exciting. This idea of components isn't new, but this new attempt is very promising as it's already been adopted by major actors of the web.

Web Components are a collection of W3C standards that allow us to create reusable HTML elements and to fully encapsulate all of their JavaScript, HTML and CSS. In a nutshell, that means the styles always render as we intended, and the HTML is safe from the external JavaScript.

These W3C standards are:

**Template:** Think of a template as a content fragment that is being stored for subsequent use in the document.

**Custom Element:** It lets authors define their own HTML elements that can be used in HTML documents. It can have its own scripted behavior and CSS styling.

**Shadow DOM:** Provides encapsulation for the JavaScript, CSS, and templating, which are separated from the main document.

**HTML Import:** Provide a way to include and **reuse** HTML documents in other HTML documents. It is intended to be the packaging mechanism.


# Componentize your application

Today, client-side web applications are much more complex. Perhaps, even more complex than server-side applications. 

We already know that good isolation makes reusability  and serviceability a lot easier; and to some extent, we're already building components with Angular (directives) and React. 

Unfortunately, some limitations still remain: 

-  we rely on specific frameworks
-  there's no way to componentize CSS (SASS helps though)
-  Interoperability is still an issue

Enter Polymer...

## Polymer

Polymer is library built on top of the Web Components standard designed to make it easier to extend the vocabulary of HTML. And to make it faster for developers  to create **reusable components**. It also comes with modern features such as  two-way binding and property observation to help with sophisticated UI.

Because the libary is built on top of Web Components, all the components created will be compatible with other web components. For instance, components built with [Bosonic](http://bosonic.github.io/) or [X-Tag](http://www.x-tags.org/).

Polymer V1.0, the production-ready release was published in May, along with a collection of custom elements that you can already use in your own applications. They are available on the [Element Catalog](https://elements.polymer-project.org/).

As an example, to add a Google map with a marker pointing to Intelliware, we only need the following lines:

<script src="https://gist.github.com/JLBoor/51cad348d7d83ad4b159.js"></script>

# Conclusion

In a world where we have no idea what we'll build our future products with, being framework agnostic and future proof would be very beneficial. That's the kind of freedom we are striving for with the Web Components!

Also, with UX driving user adoption, companies understand better than ever the importance of consistency and quality when building a new UI. It is essential to change the way we build our applications to accomodate those needs.

Finally, it's worth noting that Google is looking at plugging Web Components into Angular 2.0 using Polymer 1.0. Stay tuned!

---
Resources: 

- [Polymer Project](https://polymer-project.org/)
- [Mozilla Developer](https://developer.mozilla.org/)
- [Mozilla Hacks](https://hacks.mozilla.org)
- [WebComponents.org](http://webcomponents.org/)



	
