---
name: generate-playbook
description: Create a comprehensive playbook for a specific project or topic to guide LLMs in understanding and working effectively within that domain.
category: meta
arguments:
  - name: topic
    required: true
    description: The specific topic or project for which the playbook is being created
  - name: instructions
    required: false
    description: Additional instructions or context for the playbook
tags:
  - playbook
  - documentation
  - meta
---
A playbook extracts key insights and principles from the topic/content AND provides actionable guidance for applying those concepts. It should work both as a reference document for humans and as context/guidance for LLMs tackling similar tasks.

The structure should follow what makes most sense for the specific domain - this might mirror the original content organization, follow a workflow, or use whatever logical flow best serves the user's needs.

Consider including both:
- **Understanding**: Core concepts, terminology, context, constraints
- **Application**: How to implement, when to use what approach, decision frameworks, success indicators

These two considerations should not necessarily be separate sections, but rather integrated into a cohesive narrative that flows logically.

**Important**: Be concise but comprehensive - include all important details from the source material, but don't extrapolate beyond what's actually provided. Stick to insights and guidance that can be directly drawn from the content rather than adding generic examples or advice.

The goal is creating a practical working document that can guide actual work, whether being referenced by a human or used to brief an AI assistant.

Create a playbook for: `{{ topic }}`
{% if instructions %}**Instructions or Additional Context**: {{ instructions }}{% endif %}
