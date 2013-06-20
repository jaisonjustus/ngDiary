##Features of AngularJS

There are mainly 5 main features in AngularJS.

- Two way Data-Binding
- Templates
- MVC Architecture
- Dependency Injection
- Directives


###Two way Data-Binding
Data binding is a coolest feature in AngularJS. This helps developer to write less amount of code regarding the DOM. This help to maintian your focus on building solid application rather than spending time in swimming across DOM.

The basic theory behind data-binding in angualar is **single source of truth** in your application. the data across an application view is said to be **Model**. You perform you data read/write on model and with help of certain directive your able to provide a data presentation in your view.

In normal application we attach the data to a DOM and on a later point, the data get update the developer required to write code block to reproduce the changes happen in the data in DOM. For a smaller app writing such code blocks are okay. but when your application grows bigger and bigger, It will be a serious pain to manage code blocks for data mirror. But angular save us from this head ache by its beautiful feature called two way data-binding. Angular will take care of the synchronization between DOM and Model in both direction.

###Dependency Injection
Dependecy Injection is the other cool feature of angular. This help the developer to ask for his dependecies rather that search and making it. The developer is only required to specify the dependencies he want and angular will take care of creating and providing it. This help developers while doing tests.

###Directives
Directives is a very very good feature help the developer to write their own custom html reusable widget/components.

###Templates
In angular the template is HTML itself. Angular helps to extend the HTML vocabulary for data binding to DOM. The process of templating is first the browser parse the HTML template into DOM. Then angular takes the DOM to render the template. but before that it process the direcitves attached to the DOM, which are responsible for the data-binding. Angular manipulate the template as DOM itself rather than as HTML string.

###MVC Architecture
Angular is built with the basic principle of Model-View-Controller (MVC) design pattern, but its more similar to Model-View-ViewModel (MVVM) pattern.