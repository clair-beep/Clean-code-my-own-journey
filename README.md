## Table of Contents

- [Clean-code-my-own-journey](#clean-code-my-own-journey)
  - [What is this project?](#what-is-this-project)
  - [Sources](#sources)
    - [Books](#books)
    - [Websites](#websites)
    - [Videos](#videos)
  - [Introduction](#introduction)
  - [Chapter 1](#chapter-1)
  - [Chapter 2](#chapter-2)
  - [Chapter 3](#chapter-3)
    - [Function arguments (2 or fewer ideally)](#function-arguments-2-or-fewer-ideally)
    - [Functions should do one thing](#functions-should-do-one-thing)
    - [Function names should say what they do](#function-names-should-say-what-they-do)
    - [Don't use flags as function parameters](#dont-use-flags-as-function-parameters)
    - [Favor functional programming over imperative programming](#favor-functional-programming-over-imperative-programming)
    - [Avoid conditionals](#avoid-conditionals)
  - [Chapter 4](#chapter-4)
  - [Chapter 5](#chapter-5)
  - [Chapter 6](#chapter-6)
  - [Chapter 7](#chapter-7)
  - [Chapter 8](#chapter-8)
    - [Using third party code](#using-third-party-code)
  - [Chapter 9](#chapter-9)
    - [The Three Rules of TDD](#the-three-rules-of-tdd)
    - [Clean tests](#clean-tests)
    - [F.I.R.S.T](#first)
  - [Chapter 10](#chapter-10)

# Clean-code-my-own-journey

Get the key ideas from Clean Code by Robert C. Martin

## What is this project?

I read the book and carefully went through the case studies in the second part, but I still had trouble grasping the concepts. To better understand, I decided to summarize each chapter, compare my understanding with others, and put myself in the author's shoes. By thinking along the same paths as the author, I was able to gain a richer understanding of the principles, patterns, practices, and heuristics.

## Sources

### Books

Software engineering principles, from Robert C. Martin's book
[_Clean Code_](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

### Websites

3 "ilities" of software architecturere from Ryan McDermott repository
[3Rs of Software Architecture](https://github.com/ryanmcdermott/3rs-of-software-architecture)

clean-code-javascript from Ryan McDermott repository [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript)

Naming convention (programming) [naming-convention-programing](<https://en.wikipedia.org/wiki/Naming_convention_(programming)>)

Clean Code: Formatting (Source code structure)
[clean-code-formatting](https://medium.com/nerd-for-tech/clean-code-formatting-source-code-structure-f3021575d79)

Clean code — Classes
[Clean code — Classes](https://medium.com/javarevisited/clean-code-classes-dae3cb44eb90)

JavaScript Classes – How They Work with Use Case Example
[JavaScript Classes – How They Work with Use Case Example](https://www.freecodecamp.org/news/javascript-classes-how-they-work-with-use-case/)

JavaScript Classes – How They Work with Use Case Example
[JavaScript Classes – How They Work with Use Case Example](https://www.freecodecamp.org/news/javascript-classes-how-they-work-with-use-case/)

### Videos

Liskov: The Liskov Substitution Principle 
[Liskov: The Liskov Substitution Principle](https://www.youtube.com/watch?v=-Z-17h3jG0A&t=184s)

## Introduction

Learning to write clean code is hard work. It requires more than just the knowledge of
principles and patterns. You must sweat over it. You must practice it yourself, and watch
yourself fail. You must watch others practice it and fail. You must see them stumble and
retrace their steps. You must see them agonize over decisions and see the price they pay for
making those decisions the wrong way.

Not every principle herein has to be strictly followed, and even fewer will be
universally agreed upon. These are guidelines and nothing more, but they are
ones codified over many years of collective experience by the authors of
_Clean Code_.

## Chapter 1

Let's dive into Chapter 1 of "Clean Code" by Uncle Bob (Robert C. Martin). Now, Uncle Bob isn't just throwing around buzzwords; he's giving us some serious wisdom on writing code that doesn't make you want to tear your hair out.

So, picture this: you're not just writing code for the compiler; you're crafting a message for your fellow developers. It's a conversation, not a monologue. Uncle Bob's all about that communication game, urging us to treat our code like a love letter, not a breakup text.

Now, being self-taught in the coding realm has its perks, but let's face it – it's a bit like navigating a labyrinth blindfolded. I've spent countless hours experimenting, learning from trial and error, and, of course, Googling my way through problems. But, and it's a big "but," the theoretical foundation was often missing.

This chapter gives me hope, like a revelation to the following questions: Why do we structure things a certain way? Why do we choose one approach over another? It's about understanding the soul of the code, not just the syntax.

He breaks down the importance of clean, readable code, emphasizing that it's read way more than it's written. And hey, let's be real - we've all had that moment where we look at some code and go, "What on earth was I thinking when I wrote this?" Uncle Bob is basically saying, "Let's avoid those facepalm moments, shall we?"

In a nutshell, Chapter 1 is all about the responsibility we carry as coders to make our code a joy to read, not a puzzle to solve. Because in the end, a well-written codebase is a work of art, and we're the artists shaping the future of tech. Cheers to clean code and the adventure it brings!

## Chapter 2

In this chapter, Martin explores the concept of naming, which is the foundation of clean code. He emphasizes that the names we choose for our variables, functions, classes, and modules should be clear, concise, and descriptive.

Martin starts by discussing the importance of choosing good names. He argues that a good name is the first step in making your code understandable. It's the first thing a reader will see, and it sets the tone for the rest of the code. He points out that a good name can make the difference between a piece of code that is easy to understand and one that is a puzzle.

One of the key points Martin makes is that names should be descriptive. He advises against using vague names like `a` or `DtaRcrd102` and instead encourages developers to use names that describe the purpose or the role of the variable or function. For example:

**Bad:**

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```

**Good:**

```javascript
getUser();
```

Martin also talks about the importance of using names that reveal intent. He suggests that a good name should tell you why something is done, not just what is done. For example:

**Bad:**

```javascript
let a = 50;
```

**Good:**

```javascript
let maxNumberOfItems = 50;
```

And let's not forget about readers shouldn't have to mentally translate names into what they mean. Be explicit and avoid ambiguity, for example:

**Bad:**

```javascript
const fruits = ['apple', 'banana', 'orange'];
fruits.forEach((f) => {
  process();
  transform();
  // ...
  // ...
  // ...
  // Wait, what does `f` stand for in this context?
  analyze(f);
});
```

**Good:**

```javascript
const fruits = ['apple', 'banana', 'orange'];
fruits.forEach((fruit) => {
  process();
  transform();
  // ...
  // ...
  // ...
  analyze(fruit);
});
```

The chapter also covers the concept of naming conventions. Martin discusses the importance of being consistent with naming conventions within a project. For example the built-in JavaScript libraries use the same naming conventions as Java. Data types and constructor functions use upper camel case (RegExp, TypeError, XMLHttpRequest, DOMObject) and methods use lower camel case (getElementById, getElementsByTagNameNS, createCDATASection). In order to be consistent most JavaScript developers follow these conventions

Finally proper naming of variables, functions, and classes is very important. Class names should succinctly convey their purpose, avoiding unnecessary complexity or ambiguity.

For method names, adopt a verb-centric approach. Methods represent actions or behaviors, so use verbs to clearly articulate what each method does.

**Bad:**

```javascript
class AnimalProcessor {
  handleData(animal) {
    // ...
  }
}

const processor = new AnimalProcessor();
processor.handleData(myPet);
```

**Good:**

```javascript
class PetDatabase {
  retrievePetData(pet) {
    // ...
  }
}

const database = new PetDatabase();
database.retrievePetData(myPet);
```

The principles outlined here are not mere suggestions but rather a manifesto for the conscientious developer seeking to elevate their code to the realm of clean, readable, and maintainable software.

## Chapter 3

In Chapter 3 of "Clean Code" by Robert Martin, the author delves into the importance of functions and how they contribute to writing clean code. He's not a fan of those long, complex functions that resemble a tangled spaghetti mess. Instead, he encourages us to keep our functions short and sweet, with a clear and meaningful name. Picture your function like a newspaper article headline - it should convey the essence of what it does without requiring a PhD in code deciphering. Basiccaly advocating for functions to be brief, explaining their purpose clearly, and adhering to the Single Responsibility Principle.

Central to Martin's message is the importance of choosing clear and meaningful names for functions. By doing so, code becomes self-documenting, providing a straightforward understanding of its functionality. Moreover, this aligns with the Single Responsibility Principle, promoting functions with well-defined purposes.

Moving on to the principle of avoiding side effects, the chapter underscores the significance of functions that operate predictably without causing unintended changes in the system. By adhering to this guideline, code becomes more reliable, reducing the likelihood of hidden behaviors that can lead to confusion or bugs. Each function is encouraged to perform its designated task without introducing unexpected consequences.

In essence, Chapter 3 serves as a rallying cry for developers to embrace concise, well-named functions, fostering a codebase that is not only functional but also a joy to work with.

### Function arguments (2 or fewer ideally)

**Bad:**

```javascript
// Bad Practice: Unclear and inconsistent function arguments
function calculateTotal(price, quantity, discount, tax, shippingCost) {
  // Function implementation
  // ...
}
```

**Good:**

```javascript
// Good Practice: Use an options object for clearer function arguments
function calculateTotal(options) {
    const {
        price = 0,
        quantity = 1,
        discount = 0,
        tax = 0,
        shippingCost = 0
    } = options;

    // Function implementation
    // ...

    const total = /* calculate total based on options */;

    return total;
}

```

### Functions should do one thing

**Bad:**

```javascript
// Bad Practice: Function doing multiple things
function processUserData(user) {
  // Validate user data
  if (!user || !user.name || !user.email) {
    console.error('Invalid user data');
    return;
  }

  // Save user to the database
  database.save(user);

  // Send a welcome email
  emailService.sendWelcomeEmail(user.email);
}
```

**Good:**

```javascript
// Good Practice: Separate responsibilities into distinct functions
function validateUserData(user) {
  if (!user || !user.name || !user.email) {
    console.error('Invalid user data');
    return false;
  }
  return true;
}

function saveUserToDatabase(user) {
  // Save user to the database
  database.save(user);
}

function sendWelcomeEmail(email) {
  // Send a welcome email
  emailService.sendWelcomeEmail(email);
}

// Main function orchestrating the process
function processUserData(user) {
  if (validateUserData(user)) {
    saveUserToDatabase(user);
    sendWelcomeEmail(user.email);
  }
}
```

### Function names should say what they do

**Bad:**

```javascript
// Bad Practice: Unclear function name
function xyz(a, b) {
  // Implementation details
  // ...
}
```

**Good:**

```javascript
// Good Practice: Descriptive function name
function calculateSum(a, b) {
  return a + b;
}
```

### Don't use flags as function parameters

**Bad:**

```javascript
// Bad Practice: Using a flag as a function parameter
function fetchData(url, useCache) {
  if (useCache) {
    // Retrieve data from cache
    return cache.get(url);
  } else {
    // Fetch data from the server
    return server.fetch(url);
  }
}
```

**Good:**

```javascript
// Good Practice: Separate functions for different behaviors
function fetchDataFromCache(url) {
  return cache.get(url);
}

function fetchDataFromServer(url) {
  return server.fetch(url);
}
```

### Favor functional programming over imperative programming

**Bad:**

```javascript
// Bad Practice: Imperative programming with mutability
function calculateTotalPrice(cart) {
  let totalPrice = 0;

  for (let i = 0; i < cart.length; i++) {
    const item = cart[i];
    totalPrice += item.price * item.quantity;
  }

  return totalPrice;
}
```

**Good:**

```javascript
// Good Practice: Functional programming with immutability
function calculateTotalPrice(cart) {
  return cart.reduce((total, item) => total + item.price * item.quantity, 0);
}
```

### Avoid conditionals

**Bad:**

```javascript
class Airplane {
  // ...
  getCruisingAltitude() {
    switch (this.type) {
      case '777':
        return this.getMaxAltitude() - this.getPassengerCount();
      case 'Air Force One':
        return this.getMaxAltitude();
      case 'Cessna':
        return this.getMaxAltitude() - this.getFuelExpenditure();
    }
  }
}
```

**Good:**

```javascript
class Airplane {
  // ...
}

class Boeing777 extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude() - this.getPassengerCount();
  }
}

class AirForceOne extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude();
  }
}

class Cessna extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude() - this.getFuelExpenditure();
  }
}
```

## Chapter 4

We're diving deep into the world of comments. Now, here's the deal: comments are like spices in cooking. Just a pinch can enhance the flavor, but too much can ruin the dish.

First off, let's talk about why we need comments. They're not just there to fill up space; they serve a purposeJust as a chef carefully seasons a dish, Martin reminds us that comments should enhance, not overpower, the code. He emphasizes the importance of clarity and conciseness, urging developers to wield comments with precision, much like a skilled artisan crafting a masterpiece.

Through a series of illustrative examples, Martin showcases the spectrum of comment craftsmanship, from the sublime to the downright confounding. Each case study serves as a lesson in communication, highlighting the transformative power of well-placed comments to elucidate the developer's intent.
Moreover, Martin's narrative style invites readers to reconsider their approach to code documentation. He advocates for a strategic balance. Comments should provide context and insight, guiding the reader through the code without overshadowing its inherent elegance.

Here are some key points from the book regarding comments:

1. **Comments Should Be Necessary**: Martin advises against writing comments for the sake of having comments. Comments should provide valuable information that cannot be expressed through well-written code alone.

2. **Explain Intent, Not Mechanics**: Comments should focus on explaining the intent behind the code, rather than reiterating what the code does mechanically. The code itself should be clear enough to understand the mechanics.

3. **Avoid Redundant Comments**: Comments that simply repeat what the code already expresses are redundant and should be avoided. This includes comments that merely describe what a method or variable name already makes clear.

4. **Keep Comments Updated**: If code changes, comments should be updated accordingly. Stale comments can mislead readers and lead to confusion.

5. **Prefer Self-Documenting Code**: Strive to write code that is self-explanatory and doesn't require extensive commenting to be understood. Clear and descriptive names for variables, methods, and classes can go a long way in making the code more readable.

6. **Explain "Why", Not "What"**: Comments should focus on explaining why certain decisions were made or why the code behaves a certain way, rather than describing what the code does.

7. **Use Comments to Clarify Complex Logic**: Comments can be valuable for explaining complex algorithms or business rules that might not be immediately obvious from the code itself.

8. **Be Mindful of Formatting**: Comments should be properly formatted and aligned with the code they describe.

9. **Avoid Obsolete Comments**: Comments that no longer apply to the current state of the code should be removed.

10. **Consider Documentation Tools**: For documenting APIs or larger systems, consider using documentation tools like Swagger.

## Chapter 5

In this chapter we're diving deep into the art of formatting, where every space, every indentation, and every line break matters mode than one would like to think.

> First of all, let's be clear. Code formatting is important. It is too important to ignore and it is too important to treat religiously. Code formatting is about communication, and communication is the professional developer-s first order of business.
>
> — Robert Cecil Martin

1. **Separate concepts vertically:** horizontal space is also possible but, keep in mind that horizontal and verical space contribute -- as much as silence in music -- to add structure and to communicate intent. The visual structure helpos to browser quicker through large chuncks of code.
   public function getName() {return 'webauthn';}

**Good:**

```javascript
let num = 1;
let value = 2;
```

**Bad:**

<!-- prettier-ignore -->
```javascript
let num    = 1;
let value  = 2;

```

2. **Density:** Code that is tightly related should appear vertically dense. Using space between different concepts can help separate them.

**Good:**

```javascript
public class PropertyConfig {
  private String m_className;
  private List<Property> m_properties = new ArrayList<Property>();public void addProperty(Property property) {
  m_properties.add(property);
}
```

**Bad:**

<!-- prettier-ignore -->
```javascript
public class PropertyConfig {  /**
  * The class name of the reporter listener */private String m_className;  /**
  * The properties of the reporter listener */private List<Property> m_properties = new ArrayList<Property>();  public void addProperty(Property property) {
    m_properties.add(property);}
```

3. **Distance:** concepts that are closely related should be kept vertically close to each other. However, this rule does not apply to different files.

4. **Variable declaration:** variables should be declared as close to their usage as possible.

5. **Dependent functions should be grouped together:** with the child's function preferred for the function name. This helps to read the code quickly without navigating too far around various places within the code.

6. **Similar functions should be close by:** Code bits that are conceptually related tend to get close to other bits. The more affinity there is between them, the less vertical space required.

**Good:**

```javascript
public class Assert { static public void assertTrue(String message, boolean condition) {
   if (!condition) fail(message);
}static public void assertTrue(boolean condition) {
  assertTrue(null, condition);
}static public void assertFalse(String message, boolean condition) {
  assertTrue(message, !condition);
}static public void assertFalse(boolean condition) {
  assertFalse(null, condition);
}
```

7. **From top to bottom:** Function call dependencies should point in the downward direction. A function that is called should be below a function that does the calling. This creates a nice flow down the source code. As in newspaper articles, the most important concepts should come first, expressed with the least amount of polluting detail.
8. **Don't break indentation.** It is essential to respect a regular indentation in all your code, even if you want to break this standard occasionally. Following this rule makes it easy to detect the actions done by a FOR or IF clause, etc.

**Good:**

<!-- prettier-ignore -->
```javascript
const loop = ()=>{if(true){for(let x of [1,2,3]){console.log(x)}}};
```

**Bad:**

```javascript
const loop = () => {
  if (true) {
    for (let x of [1, 2, 3]) {
      console.log(x);
    }
  }
};
```

In conclusion, code formatting is crucial for communication, and it should be viewed as such. Following the above principles can help you create clean, readable, and maintainable code.

## Chapter 6

The discussion begins with Martin talking about data abstractions, which are vital for managing complexity in software. He highlights how objects conceal their data behind abstractions and provide functions that operate on that data, making it easier to maintain a clean and adaptable codebase.

He also raises concerns about exposing internal data structures directly, calling them "data structures with functions tacked on." This approach goes against the principle of information hiding and can lead to messy, tightly coupled code.

To address this issue, he recommends using data structures as data containers, which can be kept hidden within well-defined interfaces. This approach allows for manipulation of the data without revealing its internal structure, leading to increased flexibility and maintainability.

He acknowledges that there is often a tension between objects and data structures, and he believes that finding the right balance between the two is crucial. He emphasizes that object-oriented code focuses on objects managing their own data, while procedural code operates on data that is exposed.

The author stresses the importance of creating clean interfaces that abstract away implementation details to avoid confusion and make code more adaptable and maintainable. He believes that a balanced approach to using objects and data structures can lead to a flexible and efficient codebase.

Through the application of clean code principles to these components, we enhance the readability, maintainability, and flexibility of our codebase. In this chapter, we delved into practices such as encapsulating data, steering clear of getter and setter methods, prioritizing composition over inheritance, reducing mutable state, and upholding the Single Responsibility Principle (SRP). By embracing these guidelines and tailoring them to our project's needs, we foster the creation of cleaner and more resilient code.

**Encapsulating Data:**

```javascript

class Car {
  private brand: string;
  private model: string;

  constructor(brand: string, model: string) {
    this.brand = brand;
    this.model = model;
  }

  public getBrand(): string {
    return this.brand;
  }

  public getModel(): string {
    return this.model;
  }
}

```

**Avoiding Getter and Setter Methods:**

```javascript

class Rectangle {
  private width: number;
  private height: number;

  constructor(width: number, height: number) {
    this.width = width;
    this.height = height;
  }

  public get area(): number {
    return this.width * this.height;
  }

  public setDimensions(width: number, height: number): void {
    this.width = width;
    this.height = height;
  }
}

```

**Favoring Composition over Inheritance:**

```javascript

class Engine {
  public start(): void {
    console.log('Engine started');
  }
}

class Car {
  private engine: Engine;

  constructor() {
    this.engine = new Engine();
  }

  public startEngine(): void {
    this.engine.start();
  }
}

```

**Minimizing Mutable State:**

```javascript
function calculateTotalPrice(prices) {
  let totalPrice = 0;

  for (const price of prices) {
    totalPrice += price;
  }

  return totalPrice;
}

const prices = [10, 20, 30, 40];
const total = calculateTotalPrice(prices);
```

**Following the Single Responsibility Principle (SRP):**

```javascript

class Logger {
  public logError(message: string): void {
    // Log the error message to a file or console
  }

  public logMetric(metric: string, value: number): void {
    // Log the metric and its value to a monitoring system
  }
}

class PaymentProcessor {
  private logger: Logger;

  constructor(logger: Logger) {
    this.logger = logger;
  }

  public processPayment(amount: number): void {
    try {
      // Process the payment logic
    } catch (error) {
      this.logger.logError('Payment processing failed');
    }
  }
}
```

## Chapter 7

In this chapter the author emphasizes that good error handling is what separates professional software developers from amateurs.

> Error handling is important, but if it obscures logic, it's wrong.
>
> — Robert Cecil Martin

**Exceptions**
When a function encounters an obstacle, the ideal response is to halt the current operation and return to a designated location that can manage the issue. Merely logging errors to the console with console.log isn't significantly improved, as these messages can easily become lost among the multitude of outputs to the console. When you enclose a portion of code in a try/catch block, it signifies that you anticipate a potential error at that point. This is the purpose of exception handling.

Exceptions serve as a tool for code to signal a problem by "raising" or "throwing" an exception, essentially a specific value. Raising an exception is akin to a powerful version of returning from a function: it exits not only the current function but also its parent functions, all the way up to the initial call that initiated the current execution.

**Good:**

```javascript
try {
  functionThatMightThrow();
} catch (error) {
  console.log(error);
}
```

**Bad:**

```javascript
try {
  functionThatMightThrow();
} catch (error) {
  // One option (more noisy than console.log):
  console.error(error);
  // Another option:
  notifyUserOfError(error);
  // Another option:
  reportErrorToService(error);
  // OR do all three!
}
```

**Don't forget rejected promises**
For the same reason you shouldn't ignore caught errors from try/catch.

**Bad:**

```javascript
getdata()
  .then(data => {
    functionThatMightThrow(data);
  })
  .catch(error => {
    console.log(error);
  });
}
```

**Good:**

```javascript
getdata()
  .then((data) => {
    functionThatMightThrow(data);
  })
  .catch((error) => {
    // One option (more noisy than console.log):
    console.error(error);
    // Another option:
    notifyUserOfError(error);
    // Another option:
    reportErrorToService(error);
    // OR do all three!
  });
```

Mistakes and bad input are facts of life. Bugs in programs need to be found and fixed. They can become easier to notice by having automated test suites and adding assertions to your programs.

Problems caused by factors outside the program’s control should usually be handled gracefully. Sometimes, when the problem can be handled locally, special return values are a sane way to track them. Otherwise, exceptions are preferable.

## Chapter 8

Here the discussion is about the different ways to keep the boundaries of our code clean. Where Boundaries are the interfaces where diffferent parts of asystem interactL: external system libraries or databases.

### Using third party code

We don't want to have third-party APIs referenced everywhere in our application because if the APIs change; you have to modify code everywhere it's referenced.
The best way to get to know an api is writting test this allows you to:

- Document how you intend to use the library
- Test-Driven Development (TDD): Writing tests for third-party APIs documents their usage and aids in detecting breaking changes during dependency upgrades.
- Easily catch breaking changes in the library when you upgrade dependencies

It's a good practice to wrap third-party APIs, and only use your wrapper, this way:

- Create your own interface
- Simplify mocking in tests by interacting only with the custom wrapper, enhancing testability and flexibility.
- Easily adapt to changes in the third-party library's API
- Mitigating Development Bottlenecks: Frontend developers can proceed independently, unblocked by backend API development, by utilizing wrapper interfaces.

## Chapter 9

In this chapter, we will be discussing the significance of unit testing in maintaining code quality. Writing clean and effective unit tests is crucial as it helps in identifying bugs and issues early on, and also improves the maintainability and reliability of the codebase.

### The Three Rules of TDD

There are three rules that should be followed while using Test Driven Development (TDD): 

1. Write production code only to pass a failing unit test.
2. Write no more of a unit test than what is required to fail. Compilation failures are considered failures as well.
3. Write no more production code than necessary to pass the one failing unit test.

### Clean tests

When writing tests, it is essential to describe the feature and test case in a simple and clear way. Tests usually require a setup prior to invoking, and an expected result for the assertion. However, this can make the test code long, not clear, and full of details, which can make it hard to read and maintain.

We also want our tests to be isolated so that there are no dependencies between the tests. One test should not affect the outcome of another test.

Key principles for keeping tests clean include:

1. Readability: Tests should be easy to read and understand, acting as documentation for both current and future developers.
2. Expressiveness: Tests should clearly convey the intent of the code being tested, using descriptive names and well-structured assertions.
3. Maintainability: Tests should be written with maintainability in mind, allowing for easy modifications and updates as the code evolves.
4. Minimize Test Data: Tests should use minimal test data to focus on the essential behavior being tested.

### F.I.R.S.T

Clean tests follow five rules that together form the above acronym:

1. Fast: Tests should be fast to encourage frequent execution.
2. Independent: Tests should not depend on each other.
3. Repeatable: Tests should produce the same result every time they are run.
4. Self-Validating: Tests should either pass or fail clearly, without human interpretation.
5. Timely: Tests should be written before the production code and should be run frequently.

## Chapter 10

In Chapter 10, it's all about classes, what they are and how you should construct them. 
> In object-oriented programming, a class is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods).
>
> — Wikipedia

JavaScript still uses a prototype-based inheritance model. However, classes in JavaScript are a simpler way to implement OOP concepts on top of this model. The introduction of classes in JS has made it easier for developers to build software around OOP concepts. It has also brought in similarities to other OOP-based programming languages such as C++ and Java.

It is emphasized that keeping classes clean and organized is crucial. To maintain clean classes, it is imperative to follow certain rules:

1. The Single Responsibility Principle:
   - Organize code for easy navigation and understanding.
   - Utilize small, focused classes.
   - Design classes to change for one reason only.
   - Name classes according to their responsibility.
   - Minimize collaboration between classes.
  
2. Cohesion: classes should have a small number of instance variables. Each of the methods of a class should manipulate one or more of those variables. In general the more variables a method manipulates the more cohesive that method is to its class. When cohesion is high, it means that the methods and variables of the class are codependent and hang tohether as a logical whole.

3. Open-Closed Principle (OCP)

>In object-oriented programming, the open–closed principle (OCP) states "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification";[1] that is, such an entity can allow its behaviour to be extended without modifying its source code.
>
> Wikipedia

The main idea of the open/closed principle is that every class,function,module or section of your code should be open for extension and closed for modification. This means that a class,function, or module should be able to be extended in functionality without having to go into the class and change it. Essentially you shouldn't need to change existing code to add new functionality and instead should only have to add new code.

**Bad:**

```javascript

function printQuiz(questions) {
  questions.forEach((question) => {
    console.log(question.description);
    switch (question.type) {
      case "boolean":
        console.log("1. true");
        console.log("2. false");
        break;
      case "multipleChoice":
        question.options.forEach((option, index) => {
          console.log(`${index + 1}. ${option}`);
        });
        break;
      case "text":
        console.log(`Answer: _________________`);
        break;
      case "range":
        console.log(`Minimum: _________________`);
        console.log(`Maximum: _________________`);
        break;
    }
    console.log("");
  });
}

const questions = [
  {
    type: "boolean",
    description: "Is JavaScript the coolest programming language in the world?",
  },
  {
    type: "multipleChoise",
    description: 'What is the best programming language in the world?"',
    options: ["Javascript", "Python", "C++", "Java"],
  },
  {
    type: "text",
    description: "What is your favorite programming language?",
  },
  {
    type: "range",
    description: "How much do you like Javascript",
  },
];

printQuiz(questions);


```

**Good:**

```javascript
class BooleanQuestion {
  constructor(description) {
    this.description = description;
  }

  printQuestionChoices() {
    console.log("1. true");
    console.log("2. false");
  }
}

class MultipleChoiceQuestion {
  constructor(description, options) {
    this.description = description;
    this.options = options;
  }

  printQuestionChoices() {
    this.options.forEach((option, index) => {
      console.log(`${index + 1}. ${option}`);
    });
  }
}


class TextQuestion {
  constructor(description){
    this.description = description;
  }

  printQuestionChoices() {
    console.log("Answer: _____________");
 
  }
}

class RangeQuestion {
  constructor(description){
    this.description = description;
  }

  printQuestionChoices() {
    console.log("Minimum:: _____________");
    console.log("maximum:: _____________");

  }
}

function printQuiz(questions){
  questions.forEach(question => {
    console.log(question.description);
    question.printQuestionChoices();
    console.log('')
  })
}

const questions = [
  new BooleanQuestion("Is Javascript the coolest language in the world?"),
  new MultipleChoiceQuestion("What is the best programming language in the world?", ["Javascript", "Python", "C++", "Java"]),
  new TextQuestion("What is your favorite programming language?"),
  new RangeQuestion("How much do you like Javascript?")
]

printQuiz(questions)

```
  
4. Dependency Inversion Principle (DIP):

>In object-oriented design, the dependency inversion principle is a specific methodology for loosely coupled software modules. When following this principle, the conventional dependency relationships established from high-level, policy-setting modules to low-level, dependency modules are reversed, thus rendering high-level modules independent of the low-level module implementation details.
>
> Wikipedia

The Dependency Inversion principle states that our classes should depend upon interfaces or abstract classes instead of concrete classes and functions.

Implementing the Dependency Inversion Principle in projects can yield several benefits:

- Loose Coupling: By introducing abstractions, high-level modules are no longer directly dependent on low-level modules. This loose coupling allows for independent development, modification, and replacement of individual components.
  
- Testability: Abstractions make it easier to write unit tests by enabling the use of mock objects or test doubles. With dependencies abstracted away, I can isolate and test individual modules more effectively.
- Maintainability: The DIP reduces the impact of changes in low-level modules on high-level modules. This modular structure makes it simpler to update or replace components without affecting the entire system, leading to improved maintainability.
- Scalability: The use of abstractions allows for the addition of new implementations without modifying existing code. This scalability makes it easier to extend the system’s functionality while preserving the existing codebase.

**Bad:**

```javascript
class Store {
  constructor(user) {
    this.paypal = new Paypal()
    this.user = user
    this.stripe = new Stripe(user)
  }

  purchaseBike(quantity) {
    this.stripe.makePayment(200 * quantity * 100)
    this.paypal.makePaymentP(this.user, 200 * quantity)

  }

  purchaseHelmet(quantity){
    this.stripe.makePayment(15 * quantity * 100)
    this.paypal.makePaymentP(this.user, 15 * quantity)

  }
}

class Stripe {
  constructor(user) {
    this.user = user
  }

  makePayment(amountInCents){
    console.log(`${this.user} made payment of $${amountInCents / 100} with Stripe`)
  }
}

class Paypal {
  makePaymentP(user, amountInDollars){
  console.log(`${user} made payment of $${amountInDollars / 100} with Paypal`)
}
}

const store = new Store('Jhon')
store.purchaseBike(2)
store.purchaseHelmet(2)
```

**Good:**

```javascript
class Store {
  constructor(paymentProcessor) {
    this.paymentProcessor = paymentProcessor;
  }

  purchaseBike(quantity) {
    this.paymentProcessor.pay(200 * quantity);
  }

  purchaseHelmet(quantity) {
    this.paymentProcessor.pay(15 * quantity);
  }
}

class StripePaymentProcessor {
  constructor(user) {
    this.user = user;
    this.stripe = new Stripe(user);
  }

  pay(amountInDollars) {
    this.stripe.makePayment(amountInDollars * 100);
  }
}

class Stripe {
  constructor(user) {
    this.user = user;
  }

  makePayment(amountInCents) {
    console.log(
      `${this.user} made payment of $${amountInCents / 100} with Stripe`,
    );
  }
}

class PaypalPaymentProcessor {
  constructor(user) {
    this.user = user;
    this.paypal = new Paypal();
  }

  pay(amountInDollars) {
    this.paypal.makePayment(this.user, amountInDollars);
  }
}
class Paypal {
  makePayment(user, amountInDollars) {
    console.log(`${user} made payment of $${amountInDollars} with Paypal`);
  }
}

const storeWithPayPal = new Store(new PaypalPaymentProcessor("Jhon"));
storeWithPayPal.purchaseBike(2);
storeWithPayPal.purchaseHelmet(2);

const storeWithStripe = new Store(new StripePaymentProcessor("Jhon"));
storeWithStripe.purchaseBike(2);
storeWithStripe.purchaseHelmet(2);
```
