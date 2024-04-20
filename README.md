## Table of Contents

- [Clean-code-my-own-journey](#clean-code-my-own-journey)
  - [What is this project?](#what-is-this-project)
  - [Sources](#sources)
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

# Clean-code-my-own-journey

Get the key ideas from Clean Code by Robert C. Martin

## What is this project?

I read the book and carefully went through the case studies in the second part, but I still had trouble grasping the concepts. To better understand, I decided to summarize each chapter, compare my understanding with others, and put myself in the author's shoes. By thinking along the same paths as the author, I was able to gain a richer understanding of the principles, patterns, practices, and heuristics.

## Sources

Software engineering principles, from Robert C. Martin's book
[_Clean Code_](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

3 "ilities" of software architecturere from Ryan McDermott repository
[3Rs of Software Architecture](https://github.com/ryanmcdermott/3rs-of-software-architecture)

clean-code-javascript from Ryan McDermott repository [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript)

Naming convention (programming) [naming-convention-programing](<https://en.wikipedia.org/wiki/Naming_convention_(programming)>)

Clean Code: Formatting (Source code structure)
[clean-code-formatting](https://medium.com/nerd-for-tech/clean-code-formatting-source-code-structure-f3021575d79)

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
