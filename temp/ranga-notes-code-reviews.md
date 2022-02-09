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

- Steps
  - Use static analysis tools - SONAR
    - components & their sizes & interactions with other components
    - Hotspots: Large Classes, Complex methods, Large Components, Lot of dependencies, Uncovered Code
  - Review Junits for  complex methods/classes
  - Check Readability of code
    - Most important of 4 principles of Simple Design
  - Check everything mentioned in what?

## What?

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
    - Web Layer
  -   - Business logic creeping in?
    - Assemblers
    - Business Layer
    - Access Layer
  - OOPS principles
    - Domain Models
  - Unit Tests
    - How easy is it to unit test?
- Cross Cutting
  - reuse
  - NFRs
    - scalability
    - performance
    - security
    - needs of operations team
  -   - logging etc
- Code
  - 4 principles of simple desing
  - Basics
    - Formatting
    - size
    - complexity
    - new language features
    - documentation
  -   - javadocs
  - Scalability
    - bottlenecks
  - Performance
    - no premature optimizations
    - object creation in loops
    - closing connections and other open stuff
    - session usage
    - caching?
    - Database related?
  - Operations
    - Proper Exception Handling
    - Transaction Management
  - Security
  - unit tests
    - readable
  - Langauge Specific
    - Object class methods
  -   - equals
  -   - hashcode
    - String
    - Generics
    - Enums
    - Creating and destroying objects
- Engineering Practices
  - how often is code committed
  - Release practices
  - Broken Builds
  - Deployment Practices
  - Continuous Integration