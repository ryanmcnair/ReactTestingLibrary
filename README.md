# React Testing Library/Jest


## Jest & Jest DOM Assertions

`expect(linkElement).toBeInTheDocument()`

* expect: 
	* Jest global, starts the assertion
* expect argument: 
	* subject of the assertion
* matcher:
	* Type of assertion
	* This matcher comes from Jest-DOM
* matcher argument: 
	* Refines matcher

More assertion examples
* expect(element.textContent).toBe(‘hello’);
* expect(elementsArray).toHaveLength(7);

Jest-dom:
* Comes with ‘create-react-app’
* src/setupTests.js imports it before each test, makes matchers available

* DOM-based matchers
	* Examples: toBeVisible() or toBeChecked()

## Jest

* React Testing Library helps with
	* Rendering components into virtual DOM
	* Searching virtual DOM
	* Interacting with virtual DOM
* Needs a test runner
	* Finds tests, run them, make assertions
* Jest
	* Is recommended by Testing Library
	* comes with ‘create-react-app’
* npm test runs an npm script that runs Jest in watch mode

* **Jest Watch Mode**

	* Watch for changes in files since last commit
	* Only run tests related to these files
	* No changes? No tests
		* Type ‘a’ to run tests
* How does Jest work? 
	* global test method has 2 arguments: 
		* string description
		* test function
	* test fails if error is thrown when running function
		* assertions throw errors when expectation fails
	* No error -> tests pass
		* Empty test passes

**_## TDD  (Test Driven Development)_****## 
**

* Write tests before writing code
	* the write code according to “spec’ set by tests
* Sometimes called ‘red-green’ testing
	* Tests fail before code is written
* Write ‘shell’ function
* Write tests
* Tests fail
* Write code
* Tests pass!

* Why TDD? 
	* Makes a huge difference in how it feels to write tests
		* part of the coding process, not a ‘chore’ to do at the end
	* More efficient
		* Re-run tests ‘for free’ after changes

**_What does React Testing Library Do?_****
**
**
**
* Creates virtual DOM for testing
	* and utilities for interacting with DOM
* Allows testing without a browser

**_Types of Tests_****
**
**
**
* Unit tests
	* Tests one unit of code in isolation
* Integration tests
	* How multiple units work together
* Functional Tests
	* Tests a particular function (behavior) of software
* Acceptance / End-to-end (E2E) Tests
	* Use actual browser and server (Cypress, Selenium)

**_Functional Testing vs Unit Testing_**
**_
_**
Functional testing:
* different mindset from unit testing

Unit Testing:
* Isolated: mock dependencies, test internals
	* ⭐️ Very easy to pinpoint failures 
	* 👎Further from how users interact with software
	* 👎More likely to break with refactoring

Functional Testing:
* Include all relevant units, test behavior
	* ⭐️Close to how users interact with software
	* ⭐️Robust tests
	* 👎More difficult to debug failing tests

**_Test Driven Development (TDD) vs Behavior Driven Development (BDD)_**

Testing library encourages testing *behavior* over *implementation*
* BDD is very explicitly defined
	* involves collaboration between lots of roles
		* developers, QA, business partners, etc
	* defines process for different groups to interact

**_Testing library & accessibility_**

* Testing Library recommends finding elements by accessibility handles
	* https://testing-library.com/docs/queries/about/#priority

* create-react-app’s example test uses ‘getByText’
	* ok for non-interactive elements
	* better: ‘getByRole’
* Roles documentation: https://www.w3.org/TR/wai-aria/#role_definitions

	* some elements have built-in roles: *button*, *a*
* Can’t find an element like a screen reader would?
	* Then the app isn’t friendly to screen readers

