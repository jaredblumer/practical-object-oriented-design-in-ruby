# Notes from Sandi Metz's _Practical Object Oriented Design in Ruby_

## SOLID
- Single Responsibilty
- Open-Closed
- Liskov Substitution
- Interface Segregation
- Dependency Injection

## DRY, WET, and AHA
_Don't Repeat Yourself_ (DRY) is a principle of software development aimed at reducing repetition of information which is likely to change, replacing it with abstractions that are less likely to change.

The opposing view to DRY is called WET, a backcronym commonly taken to stand for _Write Everything Twice_,  or alternatively _Write Every time_, _We Enjoy Typing_, or _Waste Everyone's Time_.

AHA stands for avoid hasty abstractions, which prefers duplication over the wrong abstraction. AHA programming assumes that both WET and DRY solutions inevitibly create software that is rigid and difficult to maintain.

Each of these principles offers a unique perspective on code management, highlighting the importance of balancing abstraction and duplication to maintain flexible and maintainable software.

## Law of Demeter
The Law of Demeter recommends that objects should avoid accessing the internal data and methods of other objects. Instead, an object should only interact with its immediate dependencies.

## Software Dependencies
A software dependency is a relationship between software components where one component relies on another to function properly. For example, if a software application uses a library to query a database, the application depends on that library.

Software dependencies can be broadly classified into two categories: direct and transitive. Direct dependencies are explicitly defined and used by a software component. Transitive dependencies, on the other hand, are the libraries or modules that are indirectly used by a software component, such as when a library relies on other libraries to function.

## Manifesto for Agile Software Development
Agile Software Development values:
- **Individuals and interactions** over processes and tools
- **Working software** over comprehensive documentation
- **Customer collaboration** over contract negotiation
- **Responding to change** over following a plan

While there is value in the items on the right, Agile Software Development values items on the left more.

## Agile Principles
- Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
- Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.
- Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
- Business people and developers must work together daily throughout the project.
- Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
- The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
- Working software is the primary measure of progress.
- Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
- Continuous attention to technical excellence and good design enhances agility.
- Simplicity--the art of maximizing the amount of work not done--is essential.
- The best architectures, requirements, and designs emerge from self-organizing teams.
- At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

## BUFD: Big Up Front Design
Agile believes that your customers can't define the software they want before seeing it, so it's best to show them sooner rather than later.

There's no reason to do a Big Up Front Design (BUFD) because it cannot possibly be correct, and no one cannot predict when the application will be done, because no one knows in advance what it will eventually do.

## Technical Debt
Technical debt (also known as tech debt or code debt) describes what results when development teams take actions to expedite the delivery of a piece of functionality or a project which later needs to be refactored.

## Writing Code That Embraces Change
The goal is to model your application, using classes, such that it does what it is supposed to do right now and is also easy to change later.

- A class must have data and behavior and it should do the smallest possible useful thing; that is, it should have a single responsibility.
- Hide instance variables and data structures.
- Methods, like classes, should have a single responsibility. Methods with a single responsibility expose previously hidden qualities, avoid the need for comments, encourage reuse, and are easy to move to another class when refactoring.
- If you have a muddled class with too many responsibilities, separate those responsilities into different classes.

## Managing Dependencies
Because well designed objects have a single responsibility, their very nature requires that they collaborate to accomplsh complex tasks.

An object has a dependency when it knows:

- The name of another class.
- The name of a message that it intends to send to someone other than _self_.
- The arguments that a message requires.
- The order of those arguments.

The design challenge is to manage dependencies so that each class has the fewest possible; a class should know just enough to do its job and not one thing more.

## Dependency Injection
Dependency injection is a programming technique in which an object or function receives other objects or functions that it requires, as opposed to creating them internally. Dependency injection aims to separate the concerns of constructing objects and using them, leading to loosely coupled programs.

## Remove Argument-Order Dependencies
Utilize keyword arguments to avoid depending on positional arguments. Keyword arguments can be passed in any order and adds clarity.

## Explicitly Define Defaults
Keyword arguments allow you to set defaults in the arguments list. Adding a default renders the keyword argument optional.

## Using Modules
Modules, like classes, hold methods. However, modules can not be instantiated. In other words, it is not possible to create objects from a module. Furthermore, modules do not utilize the method `new`.

Modules are userful for sharing methods between classes. Methods can be included into classes, in order to make their methods available to the class. Modules are useful when we have methods that we want to reuse in certain classes, but also want to keep them in a central place to reduce duplication.
