---
name: generate-prompt
description: Generate a well-structured prompt with frontmatter and Jinja2 template for a specific task or goal.
category: meta
arguments:
  - name: goal
    required: true
    description: The task, goal, or purpose the prompt should accomplish
  - name: prompt_name
    required: false
    description: Kebab-case name for the prompt (e.g., "analyze-code-quality")
  - name: category
    required: false
    description: Category for the prompt (e.g., development, thinking, meta)
---
Create a prompt file in markdown format with YAML frontmatter and Jinja2 template content.

**Goal/Task**: {{ goal }}

## Output Format

Generate a complete prompt file following this exact structure:

```markdown
---
name: {% if prompt_name %}{{ prompt_name }}{% else %}<kebab-case-name>{% endif %}
description: <concise description of what the prompt does>
category: {% if category %}{{ category }}{% else %}<appropriate-category>{% endif %}
arguments:
  - name: <argument_name>
    required: true
    description: <what this argument is for>
  - name: <optional_argument>
    required: false
    description: <what this optional argument is for>
tags:
  - <relevant-tag-1>
  - <relevant-tag-2>
---
<Jinja2 template content here>

Use {{ variable }} for required arguments.

{%- if optional_variable %}

Use conditional blocks for optional arguments.
{%- endif %}
```

## Requirements

**Frontmatter:**
- `name`: Kebab-case identifier (e.g., "code-review", "explain-concept")
- `description`: One clear sentence describing what the prompt does
- `category`: Logical grouping (development, thinking, meta, writing, etc.)
- `arguments`: List of inputs with name, required (boolean), and description
- `tags`: 2-4 relevant keywords for discovery

**Template Content:**
- Write clear, actionable instructions
- Use `{{ variable }}` syntax for required arguments
- Use `{%- if variable %}...{%- endif %}` for optional arguments (the `-` strips adjacent whitespace to avoid extra blank lines when the condition is false)
- Be mindful of how whitespace is handled in Jinja2 templates (especially for optional arguments) and format accordingly
- Include specific guidance on expected output format
- Be comprehensive but not verbose
- Structure with markdown headings and formatting where helpful

**Best Practices:**
- Keep arguments to 2-4 maximum
- Make the prompt self-contained and clear
- Include examples within the template when helpful
- Specify output format expectations
- Write from the perspective of instructing an AI assistant

Generate the complete prompt file content only - no additional explanation needed.
