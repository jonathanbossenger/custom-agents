# Copilot Instructions for WordPress Custom Agents Repository

This repository contains custom agent definitions for GitHub Copilot, specifically designed for WordPress development tasks. These agents provide specialized expertise in various WordPress development domains.

## Repository Purpose

This repository defines custom agents that extend GitHub Copilot's capabilities with deep WordPress expertise. Each agent is a specialized assistant for specific WordPress development workflows including:

- Plugin development
- Theme customization
- Technical documentation
- Content creation for developers
- Documentation review and improvement

## File Structure and Conventions

### File Naming
- All agent definition files use kebab-case naming: `wordpress-{domain}-{role}.md`
- Files are placed in the repository root directory
- Examples: `wordpress-plugin-developer.md`, `wordpress-content-creator.md`

### File Format
Each agent definition file follows this structure:

1. **YAML Frontmatter** - Configuration metadata enclosed in `---` delimiters
2. **Agent Instructions** - Detailed prompt defining the agent's expertise, responsibilities, and behavior

## YAML Frontmatter Structure

All custom agent files MUST include a YAML frontmatter section at the beginning with these required fields:

```yaml
---
name: agent-identifier-name
description: "Detailed description of when to use this agent..."
model: inherit
color: colorname
---
```

### Frontmatter Fields

- **name**: Unique identifier in kebab-case matching the filename (without .md extension)
- **description**: Comprehensive explanation of the agent's purpose with examples showing when to use it
- **model**: Always set to `inherit` to use the default model configuration
- **color**: Visual identifier for the agent (options: `green`, `blue`, `pink`, `cyan`, etc.)

### Description Field Best Practices

The description field should:
- Start with a clear, concise statement of when to use the agent
- Include multiple `<example>` blocks demonstrating different use cases
- Each example should contain:
  - `Context:` - Situational background
  - `user:` - Sample user input
  - `assistant:` - How Copilot should respond
  - `<commentary>` - Explanation of why this agent was chosen

Example structure:
```
description: Use this agent when [condition]. Examples:

<example>
Context: [Situational background]
user: "[User request]"
assistant: "[Copilot response using Task tool to launch agent]"
<commentary>[Explanation of agent selection]</commentary>
</example>
```

## Agent Instructions Content

After the YAML frontmatter, provide detailed instructions that define:

### 1. Agent Identity and Expertise
- Clear statement of the agent's role and experience level
- Specific domains of expertise
- WordPress version knowledge and ecosystem familiarity

### 2. Core Responsibilities
- Primary tasks the agent handles
- Key workflows and processes
- Expected deliverables

### 3. Technical Guidelines
When relevant for development-focused agents, include:
- WordPress coding standards (WPCS)
- Security best practices (sanitization, escaping, nonces, capabilities)
- Performance considerations
- Database interaction patterns
- Hook and filter usage
- JavaScript and asset management

### 4. Quality Standards
- Documentation requirements (PHPDoc, code comments)
- Naming conventions
- Error handling approaches
- Testing strategies
- Backwards compatibility considerations

### 5. Workflow Approach
- Step-by-step process for handling requests
- When to ask clarifying questions
- How to structure output
- Review and refinement procedures

### 6. WordPress-Specific Context
- Current WordPress ecosystem state (Block Editor, FSE, REST API, etc.)
- Version compatibility considerations
- Integration with WordPress.org standards
- Community best practices

## WordPress Development Standards

All agents in this repository should adhere to:

### Security
- Always sanitize input data
- Always escape output data
- Use nonces for form submissions and AJAX requests
- Check user capabilities before privileged operations
- Use prepared statements for database queries

### Code Quality
- Follow WordPress Coding Standards for PHP, JavaScript, HTML, CSS
- Use WordPress core functions instead of custom implementations
- Implement proper error handling with WP_Error
- Include comprehensive PHPDoc comments
- Use meaningful, prefixed function/variable names

### Best Practices
- Leverage WordPress APIs (HTTP API, Options API, Transients API, etc.)
- Implement internationalization (i18n) for all user-facing strings
- Use WordPress hook system (actions and filters) appropriately
- Optimize for performance (caching, conditional loading, query optimization)
- Ensure accessibility compliance where relevant

## Contributing Guidelines

When adding or modifying custom agents:

1. **Maintain Consistency**: Follow the established format and structure
2. **Be Comprehensive**: Provide detailed examples and clear instructions
3. **Focus on Expertise**: Each agent should have a well-defined specialty
4. **Update Examples**: Ensure examples reflect current WordPress practices
5. **Test Descriptions**: Verify that description examples clearly show agent usage
6. **Use Current Standards**: Reference the latest WordPress coding standards and best practices

## Agent Types in This Repository

### Development Agents
- **wordpress-plugin-developer**: Plugin architecture, development, debugging, and optimization
- **wordpress-docs-architect**: Technical documentation for WordPress projects

### Content and Documentation Agents
- **wordpress-content-creator**: Educational content (blog posts, tutorials, video scripts)
- **wordpress-technical-writer**: Technical documentation creation
- **wordpress-docs-reviewer**: Documentation review and improvement

## Interaction Patterns

Agents should:
- Ask clarifying questions when requirements are ambiguous
- Provide context and reasoning for recommendations
- Suggest best practices proactively
- Identify potential issues before they become problems
- Reference official WordPress documentation when relevant

## Version Compatibility

All agents should be aware of:
- Current minimum WordPress version requirements
- PHP version compatibility (7.4+ as of WordPress 6.x)
- Modern development practices (Block Editor, FSE, React integration)
- Deprecated functions and migration paths

## Quality Assurance

Before finalizing any agent:
- Verify all code examples are syntactically correct
- Ensure WordPress function names and signatures are accurate
- Confirm hook and filter names are correct
- Test that examples follow current WordPress standards
- Check that security best practices are included
- Validate that documentation references are current

---

These instructions help GitHub Copilot understand the structure, conventions, and quality standards for this repository. When working with these files, maintain consistency with existing patterns while ensuring all content reflects current WordPress development best practices.
