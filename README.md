# Simple Test for PHP Unit Test and Mock Object

## Table of Contents
- [Online Presentation](#online-presentation)
- [Keywords](#keywords)
- [Introduction to SimpleTest](#introduction-to-simpletest)
- [Pre-requisites](#pre-requisites)
- [Features](#features)
- [Installation](#installation)
- [How to Use SimpleTest](#how-to-use-simpletest)
- [Understanding Unit Testing](#understanding-unit-testing)
- [PHP Overview](#php-overview)
- [SimpleTest Classes](#simpletest-classes)
- [Unit Test Cases](#unit-test-cases)
- [Convenience Methods (UnitTestCase)](#convenience-methods-unittestcase)
- [Use Cases](#use-cases)
- [Mock Objects](#mock-objects)
- [Python Unit Testing and Mocking](#python-unit-testing-and-mocking)
- [References](#references)
- [Technology](#technology)

---

## Online Presentation
View the [online presentation here](https://jackyhuynh.github.io/completed-testing-solutions-for-php-using-simpletest/#(1)).

## Keywords
- **JUnit**: Regression unit testing framework for Java.
- **Unit Test**: Testing individual components or units of software.
- **xUnit**: A unit testing tool for .NET Framework.
- **PHP**: Server-side scripting language.
- **Eclipse IDE**: Integrated development environment for Java.
- **Test Case**: A document with test data, preconditions, and expected results for a specific scenario.
- **Test Suite**: A collection of test cases executed together.
- **Test-Driven Development (TDD)**: Write tests before writing the actual code.

---

## Introduction to SimpleTest
**SimpleTest** is a PHP testing framework primarily used for unit tests, automation tests, and mock object support. It is designed for testing PHP applications and includes a built-in browser for web testing without needing external tools like Selenium.

---

## Pre-requisites
Before using SimpleTest, you should:
- Have a good understanding of **Unit Testing**.
- Be familiar with **PHP web development**.
- Be able to program as a **developer or tester**.

---

## Features
- Easy to use and extend.
- Supports **unit tests**, **automation tests**, and **mock objects**.
- Follows **xUnit** style.
- Provides a built-in web browser for **GUI testing**.
- Allows navigation, form filling, and authentication testing for websites.

---

## Installation
You can download SimpleTest:
- From [SourceForge](https://sourceforge.net/projects/simpletest/files/) for standalone use.
- As a plugin for [Eclipse IDE](https://sourceforge.net/projects/simpletest/files/eclipse%20plugin/).

---

## How to Use SimpleTest
- Use SimpleTest as a PHP script, integrated with your source code.
- Develop **test cases** and **test suites** for each part of your application.

---

## Understanding Unit Testing
**Unit Testing** involves testing individual units of software to ensure that each part functions correctly, even when something breaks.

---

## PHP Overview
- **PHP**: A widely-used, open-source server-side scripting language.
- **PHP files**: These files can contain HTML, CSS, JavaScript, and PHP code. They are executed on the server, and the output is returned as plain HTML.

---

## SimpleTest Classes
To use SimpleTest, include the following packages:
- `simpletest/autorun.php` for running tests.
- `simpletest/web_tester.php` for GUI testing.
- `simpletest/mock_objects.php` for mock object generation.

---

## Unit Test Cases
The simplest form of testing in SimpleTest is the **unit test**. Use `UnitTestCase` to implement unit tests:
```php
assertTrue($x)    // Checks if $x is true
assertEqual($x, $y) // Verifies $x equals $y
```

---

## Convenience Methods (UnitTestCase)
Some useful methods provided by the `UnitTestCase` class:
```php
setUp()      // Runs before each test method
tearDown()   // Runs after each test method
pass()       // Marks a test as passed
fail()       // Marks a test as failed
```

---

## Use Cases

### Simple Use Case (Unit Test)
A simple test case to verify file creation by a `Writer` object:
```php
<?php
require_once('simpletest/autorun.php');
require_once('../classes/writer.php');

class FileTestCase extends UnitTestCase {
    function testCreation() {
        $writer = &new FileWriter('../temp/test.txt');
        $writer->write('Hello');
        $this->assertTrue(file_exists('../temp/test.txt'), 'File created');
    }
}
?>
```

### Group Test (Test Suite)
Combine multiple tests into a **test suite**:
```php
class AllTests extends TestSuite {
    function AllTests() {
        $this->TestSuite('All tests');
        $this->addFile('log_test.php');
    }
}
```

---

## Mock Objects
Mock objects simulate the behavior of real objects, allowing you to test a component in isolation. This is useful when dealing with external services or unreliable resources.

### Use Case 1: Mocking External Services
Instead of relying on real HTTP requests, mock objects simulate the behavior of external services to ensure predictable test results.

### Use Case 2: Mock Database Connection
```php
Mock::generate('DatabaseConnection');
class MyTestCase extends UnitTestCase {
    function testDatabase() {
        $mockDb = &new MockDatabaseConnection();
        // Use mockDb for testing
    }
}
```

---

## Python Unit Testing and Mocking
The Python `unittest` framework is similar to JUnit and supports **test automation** and **mock objects**:
```python
from unittest.mock import Mock
mock_json = Mock()
mock_json.dumps()
```

---

## References
1. [Mock Object](https://searchsoftwarequality.techtarget.com/definition/mock-object)
2. [Understanding Python Mock Object](https://realpython.com/python-mock-library/)
3. [Python Unit Test](https://docs.python.org/3/library/unittest.html)
4. [PHP Introduction](https://www.w3schools.com/PHP/php_intro.asp)

---

## Technology
- Markdown
- R Studio for presentations
- Hosted on [GitHub](https://github.com/jackyhuynh/complete-solutions-for-php-testing-using-simpletest)