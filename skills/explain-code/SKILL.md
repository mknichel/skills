---
name: explain-code
description: Explain how code or a system works. Use when asked to explain a new piece of code, how a system works, ELI5, or to walk through a pull request.
---

# Explain Code

Explains code and technical systems in an easy to understand way. Start from the highest layers of abstraction and gradually work down to more details.

**NOTE**: The code is the source of truth. Documentation, Notion docs, Slack, and pull requests are hints, but the explanation should always be verified with the code.

## Audience

Before writing, figure out who the reader is and what they need to do with the explanation (review a PR, debug an issue, start working in the area). Infer it from the conversation or ask if it's unclear.

- Explain what the reader needs but doesn't already know. Watch for the curse of knowledge: don't skip steps that only feel obvious because you just read the code.
- Match depth to the reader. A newcomer needs the basics spelled out; an expert in the area wants the overview and the surprising parts.

## Explanation patterns

1. **Categorizations**: Divide one big complicated thing into a few smaller things, then explain how they interact or differ from each other.
2. **Life cycles**: Split a workflow into a few stages. When a diagram shows the real flow of calls or data, draw it as a Mermaid or ASCII sequence diagram.
3. **Worked example**: After the overview, trace one concrete input through the code (a single request, a single PR change), citing links to the file and line at each step. Show the concrete case before generalizing from it.
4. **Definitions**: Define new concepts that may be unfamiliar to the user. Bold the thing that you're defining and then explain its job: what it does and does not do, and compare it to similar or related things.
5. **Why it's built this way**: Explain the design decisions, constraints, and history behind the code, and the alternatives that were considered or rejected.
6. **New vs. old**: Contrast the legacy way of doing things with the new best practice way.
7. **Data provenance**: Always highlight who is the source of truth and who holds derived data.

## Style

1. **Build a balanced tree**: Start with large categories and then make them more granular. Group things into ~3-5 parts that follow the code's real seams; don't force a grouping that the code doesn't have.
2. **Lead with the tl;dr**: Start each paragraph with a 1-sentence tl;dr so readers can skim. The rest of the paragraph can expand on it in more detail. Keep paragraphs to 3-5 sentences.
3. **Use plain language**:
   - Use active voice: actor + verb + target ("the proxy writes the log", not "the log is written").
   - Put one idea in each sentence.
   - Define a term once, then use the same word for it every time. Don't switch between synonyms.
4. **Stay scoped**: Answer the question that was asked. Instead of covering nearby material, end with pointers for where to look next.

## Validation

After you finish the explanation, start a subagent to fact check the explanation to make sure it is correct with respect to the code. Correct anything before showing it to the user. A fresh subagent has not seen your reasoning so it can cleanly check the claims against the code.
