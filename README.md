# Claude Code Sub-Agents Collection

A repository documenting custom sub-agents for Claude Code to enhance development workflows.

## Available Sub-Agents

### 1. doc-updater
Updates documentation files (CLAUDE.md, README.md, and other .md files) with latest context, then commits and pushes to GitHub.

**Use case**: After making code changes, automatically update all relevant documentation to reflect the current state of the project.

### 2. repo-contextualizer
Analyzes repository structure and creates/updates CLAUDE.md and README.md files in every folder to maintain comprehensive documentation and AI-friendly context.

**Use case**: When you need to document an entire codebase, making it self-documenting with context files that help both humans and AI assistants understand the project structure.

### 3. nn-audit
Audits codebase against non-negotiable coding rules to ensure simplicity, clarity, and maintainability. Focuses on beginner-friendly code, error handling, and clean coding practices.

**Use case**: Run periodic audits to ensure your codebase stays simple, readable, and maintainable. Great for enforcing team coding standards and teaching best practices.

## Installation

These agents are automatically available in Claude Code when placed in the `~/.claude/agents/` directory.

## Usage

To use a sub-agent in Claude Code, use the Task tool and specify the `subagent_type` parameter with the agent name.

## Contributing

To add a new sub-agent:
1. Create a new `.md` file in the `agents/` directory
2. Follow the existing format with frontmatter and instructions
3. Copy to `~/.claude/agents/` to make it available globally