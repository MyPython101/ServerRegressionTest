# Simple Test for PHP

## Keyword(*)
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
