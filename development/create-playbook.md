---
name: create-playbook
description: Generate a playbook for a project, detailing structure, standards, and workflows.
category: development
arguments:
  - name: repo_path
    required: true
    description: The path to the project repository where the playbook will be generated.
tags:
  - playbook
  - documentation
  - project
---
# Project Playbook Generation Prompt Template

## Instructions for AI Agent

You are tasked with creating a comprehensive `playbook.md` file for this project. This playbook will serve as the primary guide for AI coding agents and human developers to understand how to work with, maintain, and extend this codebase.

## Analysis Tasks

**Before writing the playbook, analyze systematically in this order:**

1. **Project Metadata & Build System** - Examine `pyproject.toml`, `package.json`, `requirements.txt`, `Makefile`, `composer.json`, etc.
2. **Core Architecture & Entry Points** - Identify main modules, design patterns, key abstractions
3. **Development Tooling** - Find linters, formatters, test runners, CI/CD configurations
4. **Code Patterns & Conventions** - Analyze import styles, error handling, naming, type usage
5. **Testing Strategy** - Test structure, fixtures, async patterns, coverage approach
6. **Examples & Usage** - Review `examples/`, `docs/`, demo files for real usage patterns
7. **Configuration & Environment** - Understand dotfiles, environment setup, deployment configs

## Code Pattern Discovery Checklist

When analyzing existing code, identify:
- **Type Hints**: Style and comprehensiveness (e.g., `list[str]` vs `List[str]`)
- **Error Handling**: Custom exceptions, message patterns, context preservation
- **Docstring Style**: Format (Google/NumPy/Sphinx), examples, completeness
- **Naming Conventions**: Files, classes, functions, variables
- **Architecture Patterns**: Registry, factory, async/sync, dependency injection, etc.
- **Configuration Handling**: Settings management, environment variables

## Playbook Structure

Create a `playbook.md` with the following sections:

### 1. Project Overview
- Brief description of what the project does
- Key technologies and frameworks used
- Architecture patterns and design philosophy

### 2. Project Structure
- Directory tree with key folders and files
- Purpose and description of each major directory
- Important configuration files and their roles
- File naming conventions and organization patterns
- Where different types of code/assets belong

### 3. Getting Started
- Prerequisites and system requirements
- Environment configuration

### 4. Development Workflow
- How to run the project locally
- Development server/environment commands
- Environment variables, dependency management, and configuration
- Code reload/hot-reload capabilities

### 5. Code Standards & Guidelines
- **Follow existing patterns** - Document what's already established, don't impose new standards
- Language-specific conventions discovered in the codebase
- Naming conventions
- Error handling philosophy and patterns

### 6. Code Quality & Maintenance
- Testing framework and configuration
- Test file organization and naming patterns
- Testing patterns and conventions used in the project
- Coverage tools and expectations
- Linting tools and their configuration
- Code formatting standards and automation
- Pre-commit hooks or CI quality gates
- How to run quality checks locally
- Build system and dependency management

### 7. Project-Specific Guidelines
- Domain-specific patterns and conventions
- Important architectural decisions and rationale
- Integration patterns between components

### 8. Command Reference
- **Essential Commands** - Setup, development, testing, quality checks
- **Package Management** - Adding dependencies, updating, environment management
- **Testing Commands** - Different test types, coverage, debugging
- **Build & Quality** - Linting, formatting, building, CI commands
- **Project-Specific Tools** - Any custom scripts or specialized commands

### 9. Safety Guidelines
- **NEVER DO** section with explicit prohibitions:
  - No version control operations (`git commit`, `git push`, branch operations)
  - No destructive file operations (`rm -rf`, system modifications)
  - No external service calls (production APIs, deployments, publishing)
  - No system-level changes (global installs, environment modifications)
  - No cost-incurring operations (cloud resources, paid API calls)

## Key Principles

**Follow, Don't Lead**: Document the project's existing patterns and conventions rather than imposing external standards. If the project uses a specific testing pattern, document that pattern rather than suggesting alternatives.

**Be Actionable**: Include specific commands, file paths, and examples from the codebase. Avoid generic advice in favor of project-specific guidance.

**AI Agent Optimized**:
- Prioritize "follow existing patterns" examples over abstract descriptions
- Include common error scenarios and their solutions
- Show integration between components with real code
- Provide decision trees for "when to use X vs Y"
- Place most critical reference information (commands and safety) at the end

**Focus on Patterns**: Help users understand not just what to do, but how to do it in a way that's consistent with the existing codebase.

---

## Usage Instructions

To use this template:
1. Use the analysis tasks above to understand the project thoroughly
2. Generate the playbook following the structure provided
3. Focus on documenting existing patterns rather than prescribing new ones
4. Save as `playbook.md` in the project root at `{{ repo_path }}`
5. Create a note in the playbook to specify that the AI Coding Agent should keep it updated as the project evolves.

**REPOSITORY PATH:**
```
{{ repo_path }}
```
