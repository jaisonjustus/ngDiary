##AngularJS Diary

##Best practices 
Based on Misko Hevery talk on video on youtube angular channel please check the references for links and more details.



####when you see the {{name}} on initial page render, how to tackle it?
use **ng-bind** instead of **{{ }}** in index.html. because in index.html the page get render first and the angular files get loaded after or before rendering the page. so what the problem is the user get exposed to angular template expressions.

    <span ng-bind="project.length || '?'">?</span>
    
Also its not required to use ng-bind in views except the home view.

####Do we need minification?
Basically why you go for minification is, when you write a web app based on toolbelts like jQuery most of the code is DOM manipulation related. But in case of Angular DOM manipulations that you write will be a 20% of what you write in applicaitons that mentioned above so the requirment of minification is less needed. But if you consider you code base is too big and required minification, its yes! you can minify your code, but certain things you need to consider while minifying. but better good to turn of variable/parameter renaming option. Because 

**Two Way Binding** is pro technique of AngularJS and its maintined by binding models between view and controller. when ever a change in an attribute in the model object in controller, which is not get updated in the view.. the two binding breaks. This can happen when you minify the js code with variable rename is enabled, it rename the model variable in controller but untouch the view so the binding breaks.

Also in the case of **Dependency Injection** minification affects. In Angular Dependency injection is done by injecting modules or services through the function parameters. When the function parameters get renamed depedency inject fails.

Consider you have controller to which we inject $scope

	function HomeController($scope)	{ … };
	
After minification the controller code will be like this
	
	function HomeController(renamed$scope)	{ … };
	
Right now we are injecting renamed$scope instead of $scope after minification. But there is a angular way to solve this problem is to use **$inject** to specify the right service to inject .

##Resources

###AngularJS Best Practice
####by Misko Hevery
Streamed live on 11 Dec 2012
[Video Url](http://www.youtube.com/watch?v=ZhfUv0spHCY)
[Presentation slides](http://goo.gl/CD0Is)

Live from the Mountain View, CA meetup, Miško Hevery discusses the advantages and disadvantages of various design choices when structuring an app in AngularJS, and some of the best practices that we use in our own development.

Some of the topics we'll cover:

- Style best practices that we use in our own projects at Google
- Handling different browsers when writing directives (e.g. IE)
- Comparisons between different ways of structuring your application: + using controller vs scope + using directive prefix vs namespace + using element name vs attribute name vs class

----