---
name: pr-description
description: Best practices for writing good pull request descriptions. Use this when creating a pull request, updating a pull request, or reviewing a pull request. 
---

# Writing a good pull request description

Pull request descriptions communicate the overall change, including motivation/problem, core changes, and validation. The pull request's primary audience is a human looking at the pull request, such as for reviewing the code or understanding historical context.

## Structure

If a repository has a default pull request template, always use that. This structure can be used if a repository does not already have one.

- Start with a short (1-2 sentences) description of the overall point of the change.
- Explain the background or problem that motivated the change. Why is it important that the pull request is being made? Link any reference material if applicable.
- Explain the core behavior change from the pull request. Explain in high level terms. Include details only when it is important for the reader to know about, but do not repeat line for line diffs. Call out anything that the reviewer should pay extra attention to.
- Explain how to test the change or how the change is validated. Describe this as how an end user would validate it, not repeating the obvious CI tests.

## Tone and style

- Use prose as the default style. Avoid terse sentences, AI slop, and overly machine-like terms. Don't narrate your own process.
- Use bullet points when explaining enumerable things that prose would make it harder to read.
- Write as if the reader is relatively new to the codebase.
- Use section headers when it helps to divide the pull request description to make it easier to read.

## Rules

- Never repeat line for line changes that a reader can get by looking at the pull request.
- Never repeat validation that is obvious from CI. Don't include "Ran X tests" or "lint is clean". A reader will see that CI passes.
- Always include links to more information whenever possible.
- Include screenshots or example output when possible if it helps too explain the change.
- The length of the description should be proportional to the size and complexity of the change.
- Comment if the change is not complete. Mention previous pull requests that have added necessary functionality, or mention future work that will complete the feature.