---
name: engineer
description: This skill describes a workflow for a software engineer. Use when asked to research and implement a new feature.
---

# Engineer

## Implement a new feature

When asked to implement a new feature, follow these steps to ensure the feature will be built correctly and will correctly implement the requested feature. The goal is to make sure that the outcome will be ideal, but also not to put a burden on the user to constantly answer or oversee the implementation.

1. Identify the right outcome
   - Make sure that you understand what to build. Often, people will suggest something in loose or vague terms. If it's not clear, use the `identify-outcome` skill to be sure. Do this up front to avoid interrupts or course corrections along the rest of the way that require a human to intervene.
2. Use the `research-design` skill to identify the best approach to the feature
3. Use the `propose-design` skill to suggest how the feature should be implemented.
   - If there's one clear solution, proceed. If there are any questions in which design to choose, ask the user for input.
4. Use the `plan-implementation` skill to identify how to implement the design.

Once a plan is established, follow these steps for each step in the design:

1. Use the `sketch-implementation` skill to sketch out a design. 
2. Implement the proposed solution.
3. Run the `code-review` skill. Continue to implement fixes and run the `code-review` skill until all issues are fixed.
4. Validate the solution through a combination of CI checks, tests, and codebase specific manual verification.
