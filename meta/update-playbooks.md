---
name: update-playbooks
description: Update existing playbooks with new content, ensuring they remain accurate, relevant, and aligned with organizational/project knowledge.
category: meta
arguments:
  - name: path
    required: false
    description: The path of either a single playbook or a directory containing multiple playbooks to update.
  - name: content
    required: false
    description: The content, concept, or text to use to update the playbooks.
tags:
  - instructions
  - playbook
---
# Playbook Update Instructions

**Definition**: A playbook is a comprehensive reference guide that documents "how things work" - combining strategic context, technical details, and operational guidance in one accessible document.

**Purpose**:

- **Reference Manual**: Quick lookup for key concepts, architecture, and procedures
- **Onboarding Guide**: New team members can understand systems and responsibilities
- **Decision Support**: Provides context for technical and business choices
- **Integration Resource**: Teams know how to work with and connect to existing systems

**Think of it as**: The definitive "user manual" for each major system or capability that gets updated as things evolve.

---

## Instructions for Updating Playbooks

1. Examine the playbook path/directory to understand the current documentation landscape
2. Identify existing playbooks by reading file names and scanning content structure
3. Identify which playbooks need updates based on the new content provided
4. Integrate the new content into the relevant playbooks, ensuring it fits logically
5. Maintain the original playbook structure while enhancing it with the new information
6. Ensure that outdated or incorrect information is removed or corrected.
7. Any information that was changed or removed should be mentioned in the output in your response (not in the playbook itself).

{% if path %}**Playbook Path/Directory**: `{{ path }}`{% endif %}

{% if content %}**Content for Update**: {{ content }}{% endif %}
