---
name: create-pr-description
description: Generate a comprehensive pull request description based on the changes made.
category: development
arguments:
  - name: url_or_changes
    required: true
    description: Either the exact changes made, or a URL to the pull request for changes.
tags:
  - git
---
# PR Description Prompt

You are writing a pull request description and title in markdown. Create a clear, concise description that helps reviewers understand the changes without speculation or unnecessary detail.

## Guidelines

**✅ Do:**
- State what was changed and why
- Include relevant technical details that affect review
- Mention breaking changes, new dependencies, or deployment considerations
- Reference related issues/tickets with links if provided/available
- Note testing approach and any areas needing special attention
- Alert the reader to any leaked information, tokens, secrets, or sensitive data.

**❌ Don't:**
- Speculate about future improvements or alternative approaches
- Include verbose explanations of obvious changes
- Add motivational language or unnecessary context
- List every single file changed
- Include implementation details visible in the code

## Format

Use this structure (skip sections that don't apply):

```markdown
## PR Title

[Concise, descriptive title summarizing the changes]

## Summary

[Brief description of what this PR does]

## Changes

- [Key change 1]
- [Key change 2]
- [Key change 3]

## Testing

[How was this tested?]

## Impact

[Breaking changes, new dependencies, deployment considerations, or "No breaking changes"]
```

Keep it scannable and focused on what reviewers need to know to do their job effectively.

---

# Changes

**Note:** If the following contains a URL, file path, or instructions to fetch information, use the appropriate tool to retrieve the content before writing the PR description.

```
{{ url_or_changes }}
```
