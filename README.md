# Claude Knowledge Base

A personal documentation repository for Claude Code training materials, configuration, and best practices.

## Overview

This repository serves as a comprehensive knowledge base for working with Claude Code (claude.ai/code), containing installation guides, workflow tips, configuration examples, and integration patterns.

## Contents

### Documentation
- **[docs/overview.md](docs/overview.md)** - Main documentation file with:
  - Installation and setup instructions
  - Platform-specific requirements (macOS, Linux, WSL2)
  - MCP server configurations
  - Workflow tips and best practices
  - Troubleshooting guides

### Configuration
- **CLAUDE.md** - Project-specific instructions for Claude Code
- **.claude/** - Local Claude configuration directory
- Slack integration cache files for MCP tool usage

## Key Topics Covered

- **Installation & Setup** - Platform requirements and initial configuration
- **MCP Integrations** - Setting up Context7, Atlassian, and Slack MCP servers
- **Development Workflows** - Best practices for using Claude Code effectively
- **WSL2 Guidelines** - Performance optimization for Windows users
- **Slack Integration** - Accessing FHIR channels and discussions via MCP tools

## Quick Start

1. Ensure you have a Unix-like environment (macOS, Linux, or WSL2 on Windows)
2. Install Claude Code following the instructions in [docs/overview.md](docs/overview.md)
3. Configure MCP servers as needed:
   ```bash
   # Context7 for library documentation
   claude mcp add --scope user --transport sse context7 https://mcp.context7.com/sse
   
   # Atlassian for Jira/Confluence
   claude mcp add atlassian https://mcp.atlassian.com/v1/sse --scope user --transport sse
   ```

## Purpose

This repository serves as a centralized reference for:
- Personal Claude Code configurations and preferences
- Team-specific integration patterns
- Quick reference guides for common tasks
- Documentation of working MCP server setups

## Contributing

This is a personal knowledge base repository. Updates should focus on:
- Practical, real-world usage patterns
- Concise, scannable information (TL;DR style)
- Specific command examples over abstract descriptions
- Verified working configurations

## License

Personal documentation repository - use at your own discretion.