# Simple Test for PHP

---
author: "Truc Huynh & Mohammed Alswairki"
---

## Keyword (*)

- JUnit: is a regression unit testing framework for Java programming languages
- unit test: is a testing method where the smallest testable parts of a software are tested
- xUnit: xUnit.net is a free, open source, community-focused unit testing tool for the .NET Framework (1)
- PHP: a server side scripting languages
- Eclipse IDE: Integrated development environment for Java development
- test case: is a document, which has a set of test data, preconditions, expected results and post-conditions, developed for a particular test scenario in order to verify compliance against a specific requirement (1)
- Test suite: grouping test cases into a test script that can run every test for the application (1)
- Test Driven Development (TDD): test cases for each functionality are created and tested first and if the test fails then the new code is written in order to pass the test and making code simple and bug-free (1)

## Introduction to SimpleTest

- SimpleTest is a regression testing framework that built around test cases
- Test PHP only (not Python, not anything else)
- Completed PHP developer test solution ( unit test, automation test, GUI test, mock object, TDD (*)...)

## SimpleTest Pre-requirement

- Understand of testing methods(in this case Unit Testing)
- Understand of PHP web development language
- Know how to program (design for developer and tester)

## SimpleTest Features

- Easy to use and extend
- Automation testing (schedule scripts)
- Completed PHP developer test solution
- xUnit (*) style test cases
- Support mock objects(*)
- Built in web browser (no need for selenium)
- Can Navigate websites, fill in form, authentication, web tester
- _**Retrieved from (1)**_

## Download Simple Test for PHP

- Download from SourceForge.net
- Download as a plugin  for [Eclipse IDE (*) ](https://sourceforge.net/projects/simpletest/files/eclipse%20plugin/) also from SourceForge.net
- _**Retrieved from (1)**_

## How to Use Simple Test for PHP

- Use as PHP script, develop along with the source code
- Use Simple Test to develop test case, test suite (*)
- _**Retrieved from (1)**_


## What is Unit Testing

- Unit Testing: Not only test if a unit (collection of statements: statements, function, block, object) is working but what happen when it is not working.
- Usually perform by developer


## What is PHP

- PHP is an acronym for "PHP: Hypertext Pre-processor"
- PHP is a widely-used, open source scripting language
- PHP scripts are executed on the server
- PHP is free to download and use
- _**Retrieved from (5)**_

## What is PHP files

- PHP files can contain text, HTML, CSS, JavaScript, and PHP code
- PHP code is executed on the server, and the result is returned to the browser as plain HTML
- PHP files have extension ".php"
- _**Retrieved from (5)**_

## SimpleTest classes

- use _**extend**_ keyword to implement any class in SimpleTest framework
- Most use package:
  - 'simpletest/autorun.php': include for all kind of simple test
  - 'simpletest/web_tester.php': web test (GUI testing)
  - 'simpletest/mock_objects.php': generate mock object
  
  
- Most use class/interface:
  - extends TestSuite: test suites
  - extends UnitTestCase: unit test case
  - Mock : generate mock object


## Unit Test cases
- The simplest type of all test case is the unit test
- implement SimpleTest framework by extend the UnitTestCase. 
- This class of test case includes standard tests for equality, references and pattern matching

## UnitTestCase Class
Some function of UnitTestCase class, the default for SimpleTest
```php
assertTrue($x)	                // Fail if $x is false
assertFalse($x)                 // Fail if $x is true
assertNull($x)                  // Fail if $x is set
assertNotNull($x)               // Fail if $x not set
assertIsA($x, $t)               // Fail if $x is not the class or type $t
assertNotA($x, $t)	            // Fail if $x is of the class or type $t
assertEqual($x, $y)	            // Fail if $x == $y is false
assertNotEqual($x, $y)	        // Fail if $x == $y is true
assertWithinMargin($x, $y, $m)  // Fail if abs($x - $y) < $m is false
assertOutsideMargin($x, $y, $m)	// Fail if abs($x - $y) < $m is true
// see more at http://simpletest.sourceforge.net/en/unit_test_documentation.html

```

## Convenience Methods (UnitTestCase Class)
- The test cases also have some convenience methods for debugging code or extending the suite...
```php
setUp()	                // Runs this before each test method
tearDown()	            // Runs this after each test method
pass()	                // Sends a test pass
fail()	                // Sends a test failure
error()	                // Sends an exception event
signal($type, $payload) // Sends a user defined message to the test reporter
dump($var)	            // Does a formatted print_r() for quick and dirty debugging

```

## Simple Use Case (Unit Test)

- Simple test case that check a file has been created by the Writer object
```php
<?php
// The "autorun.php" file does more than just include the SimpleTest files, it also runs our test for us
require_once('simpletest/autorun.php');
require_once('../classes/writer.php');
// use extends UnitTestCase to implement simple test
class FileTestCase extends UnitTestCase {
    function FileTestCase() {
        $this->UnitTestCase('File test');}    // Constructor
    //run just before each and every test method
    function setUp() {
        @unlink('../temp/test.txt');}
    //run just before each and every test method
    function tearDown() {
        @unlink('../temp/test.txt');}
    // When a test case runs, it will search for any method that starts with the string "test" and execute that method.
    function testCreation() {
        $writer = &new FileWriter('../temp/test.txt');
        $writer->write('Hello');
        // using assertTrue function validate if the test.txt is exit, if true print 'File created'
        $this->assertTrue(file_exists('../temp/test.txt'), 'File created');
}}?>
```

## Group Test

- Group test cases to create a test suites
- Template of test suite, 'log_test.php' content
```php

<?php
// when list as abstract MyFileTestCase will not execute
abstract class MyFileTestCase extends UnitTestCase { 
 //Do sometest
 }

class FileTester extends MyFileTestCase { 
 //Do sometest
 }

class SocketTester extends UnitTestCase { 
 //Do sometest
 }
?>
```

## Group Test (cont.)

- Script 2: Test Suite 'all-test.php'
```php
<?php
require_once('simpletest/autorun.php');

// Note that allTest extends TestSuite
class AllTests extends TestSuite {
    function AllTests() {
        $this->TestSuite('All tests');
        $this->addFile('log_test.php');
    }
}
?>
```

## What is Mock Objects

- Technique for improving the design of code within Test-Driven Development
- Simulated Object that simulate the behavior of a testable unit
- Mock objects help isolate the component being tested from the components it depends on (2)

## Use case 1 (Mock Objects)

- Pre condition:
  - We test a web app
  - Our app make HTTP requests to an external services
  - External services always perform as expected but what if the services fail?
  - Temporary change in the behavior of these external services can cause immediate failures within our test suite.
- Benefit of using Mock Objects:
  - We test our app in a controlled environment
  - Replacing actual request with a mock object (simulated object)
  - Successfully simulate external services outage and design a response (in a predicted way)

## Use Case 2 (Mock Objects)

- Technology
  - PHP
  - SimpleTest
- Scenario:
  - Test database connection, simulate database being down without creating new real broken database(s)
- Step
  - Create DatabaseConnection class store in script 'database_connection.php':

```php
<?php
// database_connection.php
class DatabaseConnection {
    function DatabaseConnection() { // do some}
    
    function query() { // do some query}
    
    function selectQuery() { // do some searches}
}
?>
```

## Use Case 2 (Mock Objects) (cont.)

- run the generator to create mock version of DatabaseConnection

```php
<?php
require_once('simpletest/unit_tester.php');
require_once('simpletest/mock_objects.php');    //include the mock object library
require_once('database_connection.php');

Mock::generate('DatabaseConnection');           // run the generator to create a mock version of DatabaseConnection
?>
```

- This generates a clone class called MockDatabaseConnection. 
- We can now create instances of the new class within our test case

```php
<?php
class MyTestCase extends UnitTestCase {
    function testSomething() {
        $connection = &new MockDatabaseConnection();
    }
}
?>
```

## Python Unit Test

- The unittest unit testing framework was originally inspired by JUnit (*) and has a similar flavor as major unit testing frameworks in other languages
- It supports test automation 
- Sharing of setup and shutdown code for tests
- Aggregation of tests into collections, and independence of the tests from the reporting framework(4)

## Python Mock Object

- Python with json

```python
import json

# a Python object (dict):
x = {  "name": "John","age": 30,"city": "New York"}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string:
print(y)
```

## Python Mock Object (cont.)

- Using Python Mock Object of unittest package

```bash
>>> from unittest.mock import Mock
>>> import json
>>> json = Mock()
>>> json.dumps()
<Mock name='mock.dumps()' id='4392249776'>
```
- Unlike the real dumps(), this mocked method requires no arguments. In fact, it will accept any arguments that you pass to it.
- The return value of dumps() is also a Mock object. The capability of Mock to recursively define other mocks allows for you to use mocks in complex situations.

## Reference

- [Simple Test for PHP](http://simpletest.sourceforge.net/en/start-testing.html) (1)
- [mock object](https://searchsoftwarequality.techtarget.com/definition/mock-object) (2)
- [Understanding the Python Mock Object Library](https://realpython.com/python-mock-library/) (3)
- [Python Unit test](https://docs.python.org/3/library/unittest.html) (4)
- [PHP Introduction](https://www.w3schools.com/PHP/php_intro.asp#:~:text=What%20is%20PHP%3F%201%20PHP%20is%20an%20acronym,4%20PHP%20is%20free%20to%20download%20and%20use) (5)

## Technology

- markdown file
- using R Studio to create presentation
- file host at [Simple Test ](https://github.com/jackyhuynh/complete-solutions-for-php-testing-using-simpletest)


## Technology
List of technology
- R Studio
- Data Visualization

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Data:
Information about the data

### Prerequisites
What things you need to install the software and how to install them:
- R CRAN Project: R is a free software environment for statistical computing and graphics. It compiles and runs on a wide variety of UNIX platforms, Windows and MacOS
- RStudio IDE: RStudio is an integrated development environment (IDE) for R. It includes a console, syntax-highlighting editor that supports direct code execution, as well as tools for plotting, history, debugging and workspace management. Click here to see more RStudio features. RStudio is available in open source and commercial editions and runs on the desktop (Windows, Mac, and Linux) or in a browser connected to RStudio Server or RStudio Server Pro (Debian/Ubuntu, Red Hat/CentOS, and SUSE Linux)

### Installing
A step by step series of examples that tell you how to get a development enviroment running:
* [Install R](https://www.r-project.org/) - If you haven't downloaded and installed R, here's how to get started.
* [R Studio IDE](https://rstudio.com/products/rstudio/#:~:text=RStudio%20Take%20control%20of%20your%20R%20code%20RStudio,tools%20for%20plotting,%20history,%20debugging%20and%20workspace%20management.) - After that choose R Studio Desktop, and the free version (unless you have the Pro install). R free version is pretty good IDE.

## Running the tests
Explain how to run the automated tests for this system:
- Start R Studio.
- Create new a project.
- Copy the data and markdown file (.rmd) into the source file. For examaple:
```
~/salePredictionSystem/markdown.rmd
~/salePredictionSystem/WholesaleCustomersData.csv
```
- you can store the WholesaleCustomersData.csv in the same folder, but it is recommeded to store in a data as below (coding standard):
```
~/salePredictionSystem/data/WholesaleCustomersData.csv
```
- Make sure to change the import code on top if you want move your data anywhere. Depend on where you download the code. Your path will definately be different from mine. Please replace the path below with your own path:
```
WholesaleData <- read.csv("~/R/DataMining/WholeSale/data/WholesaleCustomersData.csv")
# path:("~/R/DataMining/WholeSale/data/WholesaleCustomersData.csv")
```
- Please take a quick view of [import data in R](https://support.rstudio.com/hc/en-us/articles/218611977-Importing-Data-with-RStudio?mobile_site=true) if you fail to change the import code.

## Deployment
How to deploy the app. 
I will not guarantee that this aplication will work "Big data set". If you are interested in "Big(or Large) data set" please join here for [an argue](https://www.researchgate.net/post/How-much-data-is-considered-to-be-small-data-Large-data-in-data-mining) on what data set is consider a large data set in data mining.

## Built With
* [R Studio IDE](https://rstudio.com/products/rstudio/#:~:text=RStudio%20Take%20control%20of%20your%20R%20code%20RStudio,tools%20for%20plotting,%20history,%20debugging%20and%20workspace%20management.) 
* [R CRAN Project](https://www.r-project.org/) 

## Contributing
Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](). 

## Authors

* **Truc Huynh** - *Initial work* - [TrucDev](https://github.com/jackyhuynh)

## Format
my README.md format was retrieved from
* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments
* Any acknowledgments go here
