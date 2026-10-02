---
name: plan-implementation
description: Plan how to implement a feature and whether work should be broken down into multiple steps.
---

# Plan Implementation

Plan the implementation before executing any code. The goal of this step is to understand everything that needs to be done to implement this feature and break it down into small steps that can be understood and tested independently.

## Questions

- Does the work need to touch multiple repositories?
- Is there a release dependency between different parts of the design, where a service needs to roll out before another part can be tested or merged?
- In what order does the code need to be merged and released?
- Use the `sketch-implementation` skill to get a sense of how the feature would be done.
- Should the code in a single repository be broken up into multiple parts?
  - Can a user understand in their head everything in the one PR?
  - Does it have modular parts with enough complexity that multiple PRs would be easier to understand?
  - Are parts of the code high risk and should be tested before the entire feature is implemented?
