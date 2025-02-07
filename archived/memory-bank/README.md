# Roo Code Memory Bank - User Guide

## Overview
The Roo Code Memory Bank is a documentation-driven system that serves as the persistent memory for Roo, ensuring continuity and context preservation across chat sessions. This guide will help you understand how to effectively use and interact with the Memory Bank system.

## Core Concepts

### Memory Bank as Persistent Memory
- The Memory Bank (`memory-bank/`) directory is Roo's **only** persistent memory across sessions
- All decisions, context, and progress must be documented here to be preserved
- No documentation = no memory after reset

### Key Files
- `productContext.md`: Overall project context and goals
- `activeContext.md`: Current tasks and active development context
- `progress.md`: Project progress tracking and status updates

### Documentation Structure
- `README.md` (this file): User guide for Memory Bank usage
- `docs/memory-bank-deep-dive.md`: Technical documentation and developer primer
- Additional context-specific documentation in relevant subdirectories

## Using the Memory Bank

### Update Memory Bank (UMB) Command
- Use "update memory bank" or "UMB" as a standalone chat command
- Triggers comprehensive Memory Bank update
- Roo will:
  1. Gather all context from current session
  2. Update all Memory Bank files
  3. Confirm completion

### Best Practices
1. Keep Memory Bank updated regularly using UMB command
2. Document decisions and context as they occur
3. Reference Memory Bank files when starting new sessions
4. Use appropriate files for different types of information

## File Organization
- Root level: Core documentation files
- `/docs`: Technical documentation
- Additional subdirectories mirror project structure where relevant

## Getting Started
1. Ensure `memory-bank/` directory exists in project root
2. Review existing documentation before starting work
3. Use UMB command to update documentation after significant changes
4. Reference Memory Bank files when needed for context

## Tips for Success
- Document decisions and their rationale
- Keep progress updates current
- Use UMB command before ending sessions
- Ask Roo to clarify any unclear documentation

Remember: The Memory Bank is only as useful as the information it contains. Regular updates and comprehensive documentation ensure optimal functionality across sessions.