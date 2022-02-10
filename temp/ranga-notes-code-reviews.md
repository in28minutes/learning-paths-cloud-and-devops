# Code Reviews

## GOAL
- Correctness
- Add value to System: Maintainability,Operations, Scalability, Performance
- Add value to People: Help them learn new things
- Add to Best Practices: Identify common mistakes/patterns

## When
- High Focus Time
  - New developer joins the team?
  - New methodology or technology change is being implemented?
  - Vertical Slice is being built
- Normal Focus
  - Peer Reviews during the sprint
- As early as possible

## How
- Static Analysis Results (Including Security Analysis)
- Ideally Pair Programming Reviews
  - Fixing comments directly discussing with developers
- Right attitude

## WHAT

- FIRST STEPS
  - Use static analysis tools - SONAR
    - components & their sizes & interactions with other components
    - Hotspots: Large Classes, Complex methods, Large Components, Lot of dependencies, Uncovered Code
  - Review Junits for  complex methods/classes
  - Check Readability of code
    - Most important of 4 principles of Simple Design
- Architecture
  - frameworks choice
  - communication with other sytems
  - testability
  - components
    - relative size
  - reuse
    - existing components
    - creating new components
- Design
  - Interactions between classes
    - Coupling
    - Cohesion
  - Layer Responsibilities
  - Unit Tests
    - How easy is it to unit test?
- Code
  - 4 principles of simple design
  - Unit tests
  - Programming Approach related things: Functional/OOPS/..
  - Language specific things
  	- Effective Java ..
  	- New language features
  	- Exception handling
    - Transaction Management
  - NFRs (Performance/Security)
- Engineering Practices
  - how often is code committed
  - Broken Builds
  - Release practices
  - Deployment Practices
  - Continuous Integration

## Quick Things
- Standards vs Principles
- Role of Static Analysis in Code Reviews
- Java Tips : minimum scope for variables, exception handling,functional programming?
- Code quality is an attitude. Either, the team has it or not. 
  - Attitude to refactor. To be boy scout. 
  - As an architect, it is important to create an environment where such an attitude is appreciated.
  - Have a good static analysis tool(and is part of Continuous Integration). 
- Static Analysis is not a magic wand. For me, results from Static Analysis are a signal: It helps me decide where I should look during peer or architect reviews?
- Have good peer review practices in place.
