High-quality applications are developed by making sure the code you are writing is flexible, maintainable, and easy to extend. Writing tests is extremely helpful when it comes to that. Furthermore, using the TDD approach comes with additional benefits and in that case, the tests you write assist in the implementation of features. To learn more about the TDD approach read our TDD blog.

Packages 

For testing purposes, we use the mockito package, which is a great shortcut for creating mocks, and the state_notifier_test library, which makes it easy to test StateNotifier. Testing library flutter_test uses a test package that provides the core functionality for writing tests in Dart as a foundation and exposes constructs by which projects may configure their tests, including initialization constructs like setUp() and setUpAll() methods.

Unit tests 

Unit testing is a type of software testing where an individual unit of code is tested under various conditions to verify its correctness. A unit may be a function, method, class, state, or just a variable.

A unit test has three phases:

Arrange – create the object of the unit that is being tested, prepare prerequisites, and arrange success or Failure for the case that is being tested
Act – call the methods, and assign the result variable with a value returned from the component being tested under the given conditions
Assert – verify whether the unit behaves as expected, and we may assert an outcome by checking if the result from the act part matches the one we expect and have prepared in arrange part using expect() function or expect a method to be called using a verify() function

Sometimes unit tests might depend on classes that fetch data from live web services or databases. Calling live services or databases slows down test execution, might return unexpected results, and make it difficult to test all possible scenarios. To avoid relying on such dependencies, they are being mocked out.

After mock and unit variables are created, we create instances of dependencies and the unit we are testing in a setUp() method. For example, we use a group of tests to create a group() method. Then we create variables that we need to act with or validate that the unit performs as expected.
 
Examples

State Notifier tests
https://gist.github.com/martaarep/7e0a253b7f7e99cba1b3167406808db2
Repository tests
https://gist.github.com/martaarep/6822d1fd0dbe24a11997948651531cae
Provider tests
https://gist.github.com/martaarep/9abd994ca8f1c63671cb2d8d3b898496
Extension tests
https://gist.github.com/martaarep/871f3b0d6ad0ed74244862d63bebc1a5

