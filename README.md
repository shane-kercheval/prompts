# Prompts

A collection of reusable prompt templates for AI assistants. Each prompt is a markdown file with YAML frontmatter for metadata and Jinja2 templating for dynamic content.

## Format

Prompts follow this structure:

```markdown
---
name: prompt-name
description: What the prompt does
category: category-name
arguments:
  - name: arg_name
    required: true
    description: What this argument is for
tags:
  - relevant-tag
---
Template content with {{ arg_name }} placeholders.

{%- if optional_arg %}
Conditional content for optional arguments.
{%- endif %}
```

**Frontmatter fields:**
- `name`: Kebab-case identifier
- `description`: One-sentence summary
- `category`: Logical grouping (e.g., development, thinking, meta)
- `arguments`: List of inputs with `name`, `required`, and `description`
- `tags`: Optional keywords for discovery

**Template syntax:**
- `{{ variable }}` for required arguments
- `{%- if variable %}...{%- endif %}` for optional content

## Usage

Use the `meta/generate-prompt.md` prompt to create new prompts, or copy `prompt-template.md.example` as a starting point
