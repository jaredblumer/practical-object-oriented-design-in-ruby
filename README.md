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
- Our highest priority is to satisfy the cystomer through early and continuous delivery of valuable software.
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

## Writing Code That Embraces Changes
The goal is to model your application, using classes, such that it does what it is supposed to do right now and is also easy to change later.

- A class must have data and behavior and it should do the smallest possible useful thing; that is, it should have a single responsibility.
- Hide instance variables and data structures.
- Methods, like classes, should have a single responsibility. Methods with a single responsibility expose previously hidden qualities, avoid the need for comments, encourage reuse, and are easy to move to another class when refactoring.
- If you have a muddled class with too many responsibilities, separate those responsilities intop different classes.
