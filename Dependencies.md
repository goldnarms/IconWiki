A description of libraries and plugins used in the app, and where to get more information.

## Client App
### [Twitter Bootstrap](http://twitter.github.com/bootstrap/)
* Twitter Bootstrap is used to style the client app. It provides several CSS styles and components as well as a Javascript library of components with extended functionality.
### [Font Awesome](http://fortawesome.github.com/Font-Awesome/)
* Font awesome replaces the icons used by Bootstrap with a webfont so that you may resize icons, change their colors and so on.

## AdminPortal
### Acceptance tests
* For acceptance test we use SpecFlow to write test in BDD style. You set up a new feature for each area(conference, venue, etc.). See the Features folder under WebTests project, when you compile a test is generated, run the test and you will get see how to implement the test in the test output window. [Read more about SpecFlow...](http://www.specflow.org/specflownew/)
* To run the tests in the browser we use WatiN. It enables us to test against the user interface. To see the implementation, look at Browser class under StepDefinitions. [Read more about WatiN](http://watin.org/)

### Automapper
Automapper does all the binding between your models and viewmodels for you, given that the properties align. To set up a map between a model and a viewmodel, set it up in AutomapperConfig under App_Start. [Read more about Automapper](http://automapper.org/)