# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a documentation repository for Claude Code training and guidance materials. The main content is in `docs/overview.md` which serves as a comprehensive cheat sheet and guide for using Claude Code effectively.

## Repository Structure

- `docs/overview.md` - Main documentation file containing installation instructions, workflow tips, and best practices for Claude Code
- `.channels_cache.json` and `.users_cache.json` - Cache files from Slack MCP integration (do not edit)

## Key Information from Overview

### Platform Requirements
- Unix-like environment required (macOS, Linux, or WSL2 on Windows)
- Windows users must use WSL2 and work within WSL filesystems for performance

### MCP Server Configuration
The documentation recommends setting up:
- Context7 MCP for library documentation: `claude mcp add --scope user --transport sse context7 https://mcp.context7.com/sse`
- Atlassian MCP for Jira/Confluence: `claude mcp add atlassian https://mcp.atlassian.com/v1/sse --scope user --transport sse`

## Documentation Guidelines

When updating documentation in this repository:
- Keep examples concise and practical
- Focus on real-world usage patterns
- Maintain the TL;DR style - information should be scannable and actionable
- Include specific command examples rather than abstract descriptions