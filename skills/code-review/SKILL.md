---
name: code-review
description: Best practices when reviewing code diffs or pull requests. Use after finishing a diff to check that it's correct and that the code looks good, or when asked to review a pull request.
---

# Code Reviews

The goal of a code review is to apply judgment on the code whether it is correct and meets the criteria for the code base. It is not a linter pass or CI checker. The goal of a code review is to catch what a human reviewer would catch and machine checks would not.

Honor any user requests that they made to focus on something in particular.

Do not automatically respond to any comments or post any new comments no matter the findings.

## Output

Share code review findings back to the user in the chat session.

- Lead with what's good about the code change
- Include findings with a priority estimate (P0, P1, P2, P3)
- Include a recommended action, but don't be overly specific with replacement code
- If something is unclear, ask a follow-up question instead of assuming
- Say what you did not review
- End with a recommendation

## What to look for

### Correctness

- Does the change actually do what it claims?
- What are possible corner cases and are they covered?
- What errors could happen and are they handled? Does the code handle the errors appropriately, such as logging and alerting or whether the error should fail the request?
- Is the code concurrency safe, if applicable? Are there race conditions or deadlocks that could arise?
- Does the code need to be backwards or forwards compatible?
- Is data integrity preserved in the code, such as atomicity or partial errors?
- Are preconditions checked appropriately?

### Tests

- Are tests actually testing the functionality, or do they look like change detector tests?
- Do tests validate the outcome of the code, in as realistic of a setup as possible? Mocks or fakes can hide real issues when used too much.
- Are positive and negative cases tested? Are corner cases tested?
- Are tests isolated and are not affected by other test cases?
- Are tests flaky or non-deterministic?

### Performance

- Are there any obvious performance issues that would cause slow latency or excessive CPU or memory usage? Does the algorithmic complexity make sense?
- Can any code be run in parallel instead of in serial?
- Is there any synchronous I/O that will block other work?
- (if applicable) For high frequency code paths, has the code been load tested and/or profiled?
- (if applicable) Does the database query look like it will perform well?

### Security + Privacy

- Does the code appropriately check and/or sanitize user input?
- Is PII correctly handled and is not leaked or logged?
- Does the code use proper authentication, authorization, and access control?
- Are there any hardcoded secrets?
- Is data properly encrypted in transit and at rest?

### Maintainability

- Is the code well factored? Are files, classes, and functions at a good abstraction level? Look for overly long files, too complex pieces of code, or high cyclomatic complexity.
- Can a reader hold each part of the code in their head?
- Are there signs of AI slop in the code?
- Use the code-comments skill to check that the code is documented appropriately.