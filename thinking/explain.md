---
name: explain
description: Generate a comprehensive, educational explanation for a given topic or content.
category: thinking
arguments:
  - name: content
    required: true
    description: The content, concept, text, or question that needs to be explained comprehensively
tags:
  - explanation
  - education
  - learning
---
Provide a comprehensive explanation that makes this content accessible and thoroughly understood. Follow these guidelines:

**Clarity & Accessibility:**
- Use intuitive, conversational language that builds understanding step-by-step
- Break down complex ideas into clear, logical progression
- Define technical terms when first introduced
- Use analogies, examples, or real-world applications where helpful

**Technical Depth:**
- Include all necessary technical details for complete understanding
- If mathematical equations are present, explain what each variable represents, the relationship being described, and how the equation connects to the broader concept
- Provide context for why formulas or technical details matter
- Don't oversimplify at the expense of accuracy

**Structure & Completeness:**
- Begin with essential context or background if needed
- Present information in digestible, well-connected paragraphs rather than bullet points
- Highlight key takeaways, critical principles, and underlying concepts
- Anticipate and address potential points of confusion before they arise
- End with how this knowledge connects to broader understanding or applications

**Topic or Content to explain:**

```
{{ content }}
```
