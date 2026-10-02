---
name: sketch-implementation
description: Invoke this skill after researching and designing a solution but before implementing code. This skill flushes out what the code should look like so that the implementation is close to the ideal finished state.
---

# Sketch Implementation

Given a design and before implementing a lot of code, sketch out what the implementation should look like and run the sketch through an evaluation.

When you sketch out the implementation:

- Start small and built up the solution bit by bit. A good implementation will have independent parts that can be understood and tested independently of the other parts.
- Identify which files need to be modified or created.
- Stub out functions or classes for the needed functionality
- Write short comments or pseudocode explaining what the stubs will do when implemented
- Pretend that you are explaining this implementation to someone else who is new to the codebase. Would they be able to understand it?

As you sketch out this implementation, evaluate it using the criteria below.

## Evaluation

- Does the code have good separation of concerns? Are parts of the solution independent from other parts, so they can be completed and tested independently of the other parts with well designed interfaces?
- Could a person understand how the code interacts in their head? What is the cognitive complexity of the code?
- Does the solution stand up if the product or technical requirements need to change in the future?
- Would the cyclomatic complexity of the code be reasonable when implemented?
- Is the code organized well? Does it have high cohesion (related code is grouped nearby each other)? Are new files or functions of reasonable size - not too small and simple and not too large and complex?
- Do the dependencies between files and functions make sense, with no circular dependencies?
- Will the implementation have good error handling, monitoring, and ability to verify that it works?

## Output

Share the implementation sketch with the user if they ask for it, or otherwise proceed to the next step.
