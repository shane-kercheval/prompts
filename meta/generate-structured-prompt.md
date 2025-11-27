---
name: generate-structured-prompt
description: Creates a well-structured YAML prompt template for a specific task or domain, with proper arguments and clear instructions
category: meta
arguments:
  - name: task_description
    required: true
    description: Clear description of what the prompt should accomplish
  - name: prompt_name
    required: false
    description: Kebab-case name for the prompt (e.g., "analyze-code-quality")
  - name: requirements
    required: false
    description: Any specific constraints, formats, or special considerations
tags:
  - prompt
  - template
  - meta
---
Create a structured prompt in YAML format for the following task: {{ task_description }}

Follow this exact structure:

```yaml
prompts:
  {% if prompt_name %}{{ prompt_name }}{% else %}create-prompt-a-name{% endif %}:
    description: <clear, concise description of what this prompt does>
    template: |
      <comprehensive prompt template with clear instructions>

      <include context and guidelines>

      <show how to use required arguments: {{argument_name}}>

      {%#if optional_arg%}
      <show conditional sections for optional arguments>
      {%/if%}

      <specify output format and requirements>
    arguments:
      argument_name:
        description: <what this argument is for>
        required: true
      optional_arg:
        description: <what this optional argument is for>
        required: false
```

Requirements for the generated prompt:
- Use kebab-case for the prompt name
- Include 2-4 relevant arguments maximum
- Use `{%#if argument_name%}` conditionals for optional arguments
- Write the template to be self-contained and clear
- Include specific instructions about output format
- Add examples within the template when helpful
- Make the description concise but informative
- Ensure arguments have clear, helpful descriptions
- Show both required arguments directly and optional ones with conditionals

**Task**: {{ task_description }}
{% if prompt_name %}**Prompt Name**: {{ prompt_name }}{% endif %}
{% if requirements %}**Specific Requirements**: {{ requirements }}{% endif %}

Generate only the YAML structure - no additional explanation needed.
