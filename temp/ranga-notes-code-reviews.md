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
  - OOPS principles
    - Domain Models
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
  - Release practices
  - Broken Builds
  - Deployment Practices
  - Continuous Integration