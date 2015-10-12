# Marketing title

To help companies build great User Experience (UX) and consistent User Interfaces (UI), we traditonnaly provide design branding, style guides and high fidelity wireframes. But that does not scale very well and rapidly hits certain limitations. 

Today, it seems that the cost of consistency unfortunately... is re-building the same piece of UI for each platform or application. This obviously creates more technical and design debt.

In this post, we'll explore a technology that has been on the developers' radar for quite some time and addresses specifically these consistency and reuse challenges: Web Components.

## What are Web Components?

The idea of Web Components is that you no longer depend on the browser to provide you with native elements. You can build you own! And that's very exciting. This idea of components ain't new, but this new try is very promising as it's already been adopted by major actors of the web.

Web Components are a collection of W3C standards that allow us to create reusable HTML elements and to fully encapsulate all of their JavaScript, HTML and CSS. In a nutshell, that means the styles always render as we intended, and the HTML is safe from the external JavaScript.

These W3C standards are:

**Templates:** Think of a template as a content fragment that is being stored for subsequent use in the document. While the parser does process the contents of the **\<template\>** element while loading the page, it does so only to ensure that those contents are valid; the element's contents are not rendered, however.

**Custom Elements:** which let authors define their own elements, including new presentation and API, that can be used in HTML documents; and
Custom Elements is a capability for creating your own custom HTML tags and elements. They can have their own scripted behavior and CSS styling.

**Shadow DOM:** which provides encapsulation for the JavaScript, CSS, and templating. They remain separate from the DOM of the main document.

**HTML Imports:** provide a way to include and reuse HTML documents in other HTML documents. It is intended to be the packaging mechanism.
You import an HTML file by simply using a **\<link\>** tag in an HTML document.


As an example, 

<script src="https://gist.github.com/JLBoor/51cad348d7d83ad4b159.js"></script>


# Componentize your applications the web today

## Why today?
Github
## How? Polymer
radar in 2013 when Google released its Web-Components based framwork: **Polymer**. 


Sometimes there is some confusion regarding Web Components and Google Polymer. Polymer is a framework that is based on Web Components technologies. You can make and use Web Components without Polymer.


iframe, embed, jquery...

To some extent, it's very close to a Angular directive or a React Component. The   difference is that is relies on the browser's API

Web applications are now as complex as any other software applications. It is essential to find the right way to divide up the development work with minimal overlap between people and systems in order to be more efficient. 

Componentization (in general) is how this is done. Any component system should reduce overall complexity by providing isolation, or a natural barrier that hides the complexity of one system from another. Good isolation also makes reusability and serviceability easier.

Initially, web application complexity was managed mostly on the server by isolating the application into separate pages, each requiring the user to navigate their browser from page to page. 

Client-side web application logic may be much more complex, perhaps even rivaling that of the server side. A possible solution to help solve this complexity is to further componentize and isolate logic within a single web page or document.

The goal of web components is to reduce complexity by isolating a related group of HTML, CSS, and JavaScript to perform a common function within the context of a single page.

CSS style isolation

There is no great way to componentize CSS natively in the platform today (though tools like Sass can certainly help). A component model must support a way to isolate some set of CSS from another such that the rules defined in one don’t interfere with the other. Additionally, component styles should apply only to the necessary parts of the component and nothing else. Easier said than done!

Sometimes there is some confusion regarding Web Components and Google Polymer. Polymer is a framework that is based on Web Components technologies. You can make and use Web Components without Polymer.



Catalog of components

- [Repository of custom elements](https://customelements.io/)
- [Polymer Catalog](https://elements.polymer-project.org/)



# Conclusion

In We have no idea what we will build our future products with

We see a proliferation of projects trying to solve the component problem in slightly different ways, using various languages. When we build on top of one of these technologies, it is at the cost of opting into a non-standard world, offering no guarantees of lasting value.

With Angular 1.x, using directives, or with React, we already started building components. The difference is that we're doing so by relying on the framework and not on the browser.

It's also worth noting that Google is looking at plugging Web Components into Angular 2.0 using Polymer 1.0. Stay tuned!

In the past few years, the complexity of the UI has increa,

We have no idea what we will build our future products with


With User Experience driving the adoption of applications, companies understand better than ever the importance consistency and quality. 
  
Nowadays, the importance of consistency is colossal, customers want to have confidence that we’ll deliver on our promises every time.

Nowadays, companies understand better than ever the importance of consistency to build a relationship of quality with their users.


Especially in a agile world where everything is constantly changing and where high quality promotes the adpotion.

Nowadays, companies understand better than ever the importance of consistency to build a relationship of quality with their users.



Resources: Mozilla

	
