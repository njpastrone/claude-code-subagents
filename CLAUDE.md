# CLAUDE.md - AI Assistant Context

Last Updated: 2024-12-04
Folder: Root
Purpose: Repository for storing and documenting custom Claude Code sub-agents

## Quick Context
- **Primary responsibility**: Documentation and version control for Claude Code sub-agents
- **Key dependencies**: None (documentation-only repository)
- **Used by**: Claude Code users who want to create and manage custom sub-agents
- **Technology stack**: Markdown documentation

## Detailed Overview

This repository serves as a centralized location for documenting custom sub-agents created for Claude Code. Sub-agents are specialized AI assistants that can be invoked through Claude Code's Task tool to perform specific, well-defined operations. Each sub-agent is defined as a markdown file with frontmatter metadata and detailed instructions.

The repository maintains both the documentation for these agents and copies of the agent files themselves, though the actual functional agents must be installed in `~/.claude/agents/` to be available in Claude Code. This dual approach allows for version control, sharing, and documentation of custom agent configurations.

## Important Files
- `README.md`: Main documentation listing all available sub-agents and usage instructions
- `CLAUDE.md`: This file - provides AI-friendly context about the repository
- `agents/doc-updater.md`: Sub-agent for updating project documentation and pushing to GitHub
- `agents/repo-contextualizer.md`: Sub-agent for creating comprehensive documentation throughout a codebase

## Repository Structure
```
claude-code-subagents/
├── README.md                     # Human-readable documentation
├── CLAUDE.md                     # AI-optimized context (this file)
└── agents/                       # Sub-agent definitions
    ├── doc-updater.md           # Documentation updater agent
    └── repo-contextualizer.md   # Repository contextualization agent
```

## Sub-Agent Format

Each sub-agent file follows this structure:
1. **Frontmatter**: YAML metadata defining name, description, tools, and model
2. **Mission Statement**: Clear description of the agent's purpose
3. **Workflow**: Step-by-step instructions for the agent to follow
4. **Guidelines**: Quality standards and best practices
5. **Error Handling**: Recovery strategies for common issues

## Common Tasks

- **To add a new sub-agent**:
  1. Create a new `.md` file in the `agents/` directory
  2. Include proper frontmatter (name, description, tools, model)
  3. Write detailed instructions for the agent's behavior
  4. Copy to `~/.claude/agents/` for global availability
  5. Update README.md with the new agent's information

- **To modify an existing agent**:
  1. Edit the agent file in `agents/`
  2. Copy the updated version to `~/.claude/agents/`
  3. Test the agent to ensure it works as expected

- **To use a sub-agent in Claude Code**:
  Use the Task tool with the appropriate `subagent_type` parameter

## Available Sub-Agents

### doc-updater
- **Purpose**: Automatically updates project documentation after code changes
- **Key features**: Analyzes git changes, updates multiple .md files, commits and pushes
- **Best for**: Keeping documentation synchronized with code changes

### repo-contextualizer
- **Purpose**: Creates comprehensive documentation throughout an entire codebase
- **Key features**: Recursive folder analysis, creates CLAUDE.md and README.md files everywhere
- **Best for**: Making large codebases self-documenting and AI-friendly

## Important Notes

- Sub-agents must be copied to `~/.claude/agents/` to be functional in Claude Code
- This repository serves as documentation and version control, not the execution location
- Agents defined here can use various Claude Code tools (Read, Write, Edit, Bash, Glob, Grep)
- The `model` field in frontmatter determines which AI model the agent uses (typically "sonnet")
- Sub-agents are invoked through Claude Code's Task tool, not directly

## Integration with Claude Code

When Claude Code invokes a sub-agent:
1. It reads the agent definition from `~/.claude/agents/[agent-name].md`
2. Creates a new context with the specified tools and model
3. Executes the agent's instructions autonomously
4. Returns results back to the main Claude Code session

## Future Enhancements

Potential areas for expansion:
- Additional specialized agents for specific workflows
- Agent templates for common patterns
- Automated testing frameworks for agents
- Agent composition and chaining capabilities
- Shared agent library for community contributions