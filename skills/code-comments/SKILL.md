---
name: code-comments
description: Guidelines for writing and reviewing inline code comments. Use when deciding when to add new comments, writing comments, editing existing comments, or reviewing a diff that touches comments.
---

# Writing good code comments

Code comments are needed 

**Comment when:**

- The _why_ behind a piece of code or decision isn't obvious.
- The code looks wrong but isn't, and the information is needed to communicate to the next reader or editor so that they don't undo the code.
- There's a constraint that is not immediately obvious to the code, such as a business constraint or performance optimization.
- You're working around a bug, spec quirk, or upstream issue. Link to more information about the issue.

**Do not comment when:**

- To restate what the code already does. Code structure and names should be self explanatory whenever possible
- To make up for a bad name

If you're not sure if a comment is needed, it probably does not. Agents generally err on the side of commenting too much.

## Tone and Style

The audience of code comments are the next humans that are reading or editing the code. Code comments require attention to understand, and bad comments make it harder to understand a piece of code. People can understand a lot by reading the code. Only include information in comments that is not obvious from reading the code.

Write like a human engineer leaving a note for the next person. Use complete sentences without semicolons or emdashes. Do not include any AI slop. Do not exaggerate or be sycophantic. Describe the issue matter of factly. Match the surrounding file's tone and style.

Write the comment as if the person reading it is new to the code base who doesn't have your context.

Don't include how you arrived at a decision unless the reasoning itself matters to a future reader.
