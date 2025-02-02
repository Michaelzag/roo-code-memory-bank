# Roo Code Memory Bank: User Guide and Instruction Modules

**Maintain Project Context Across Sessions and Memory Resets**

This guide will walk you through using the Roo Code Memory Bank system, enhanced by Roo Code's built-in context-preserving features. This combination provides a robust solution for managing project context across sessions and handling Roo's periodic memory resets.

## Getting Started

Follow these steps to set up and start using the Memory Bank system effectively:

### Prerequisites
- VS Code with Roo Code extension installed (v1.2.0 or newer)
- Basic understanding of Markdown syntax
- Project folder setup in VS Code workspace

### First-Time Setup Checklist
1. Create project directory in VS Code
2. Install Roo Code extension from VS Code Marketplace
3. Configure custom instructions through Roo Code settings
4. Initialize Memory Bank by switching to Architect mode and sending a message like 'Initialize Memory Bank'. See the [Starting a New Project Session](#starting-a-new-project-session) section for detailed steps.
> **Pro Tip:** Use our [Quick Start Template](#quick-start-template) to jumpstart your configuration.

### Quick Start Template

For users who want to get started quickly, here's a template to copy and paste into your project:

```markdown
# memory-bank/productContext.md

## Project Overview
[Briefly describe the project's purpose and goals]

## Key Technologies
- [List the main technologies and frameworks used]

## Target Audience
[Describe the intended users of the project]

---

# memory-bank/activeContext.md

## Current Task
[Describe the current task or feature being worked on]

## Next Steps
- [List the immediate next steps to move forward]

## Open Questions
- [Record any open questions or unresolved issues]

---

# memory-bank/progress.md

## Work Done
- [List completed tasks and features]

## To Do
- [List remaining tasks]

## Current Status
[Summarize the project's current status - e.g., "In development", "Testing", "Ready for review"]
```

**Instructions:**

1. **Create `memory-bank/` folder:** If you haven't already, create a folder named `memory-bank` at the root of your project in your VS Code workspace.
2. **Create files:** Inside the `memory-bank/` folder, create three new files named exactly: `productContext.md`, `activeContext.md`, and `progress.md`.
3. **Copy and Paste:** Copy the code block under "Quick Start Template" above. Paste the first section (starting with `## Project Overview`) into `productContext.md`, the second section (starting with `## Current Task`) into `activeContext.md`, and the third section (starting with `## Work Done`) into `progress.md`.
4. **Customize:** Replace the bracketed placeholders in each file with your project-specific information.

This template provides a basic structure to get you started with documenting your project in the Memory Bank. Remember to update these files regularly as your project evolves.

## Troubleshooting

This section provides solutions to common issues you might encounter while using the Roo Code Memory Bank system.

**Issue:** `[MEMORY BANK: ACTIVE]` prefix not working in Code mode.

**Solution:**
1. **Verify Custom Instructions:** Double-check that you have correctly pasted all custom instruction modules into the Roo Code "Prompts" settings in VS Code, especially the "Mode-specific Custom Instructions/Code" module. See the [Setting up Roo Code Custom Instructions](#setting-up-roo-code-custom-instructions) section for detailed instructions.
2. **Setting Save:** Ensure you have saved the VS Code settings after pasting the instructions. Sometimes settings might not apply immediately until saved.
3. **Mode Confirmation:** Make sure you are indeed in "Code" mode when using the `[MEMORY BANK: ACTIVE]` prefix. The mode is displayed in the Roo Code chat interface.
4. **Prefix Case & Spacing:** The prefix is case-sensitive and requires exact spacing: `[MEMORY BANK: ACTIVE]`. Any variations will not be recognized.

**Issue:** Roo Code does not seem to remember project context after VS Code restart.

**Solution:**
1. **Memory Bank Initialization:** Ensure you have correctly initialized the Memory Bank by following the "Starting a New Project Session" steps in this guide. The `memory-bank/` folder and required files (`productContext.md`, `activeContext.md`, etc.) must be present in your project root.
2. **Mode Switch (Ask/Architect):** After restarting VS Code, switch to either "Ask" or "Architect" mode *first*. This triggers Roo Code to automatically read and load the Memory Bank context. Switching directly to "Code" mode might bypass this loading process.
3. **`update memory bank` Command:** As a best practice, use the `update memory bank` command at the end of your sessions to ensure the Memory Bank is explicitly saved and prepared for the next session.
4. **File Paths:** Double-check that the `memory-bank/` folder is indeed located at the root of your VS Code workspace/project folder. Incorrect file paths will prevent Roo Code from finding the Memory Bank.

**Issue:** `.clinerules` are not being applied.

**Solution:**
1. **File Location:** `.clinerules` files (`.clinerules` and mode-specific variants like `.clinerules-code`) must be located at the root of your project, alongside the `memory-bank/` folder.
2. **Syntax Check:** Verify the syntax of your `.clinerules` file. Incorrectly formatted rules might be ignored. Refer to the `.clinerules` documentation for syntax guidelines.
3. **Mode Relevance:** Remember that `.clinerules-code`, `.clinerules-architect`, and `.clinerules-ask` are mode-specific. Rules in `.clinerules-code` will only apply when you are in "Code" mode, etc.
4. **Roo Code Restart (Rare):** In rare cases, restart Roo Code within VS Code after significant `.clinerules` changes to ensure rules are fully reloaded.

**Issue:** Memory Bank files are not being updated or saved.

**Solution:**
1. **File Permissions:** Ensure you have write permissions for the `memory-bank/` folder and its files.
2. **VS Code Errors:** Check the VS Code console for any file saving errors.
3. **Conflicting Extensions:** Temporarily disable any extensions that might interfere with file saving.
4. **Disk Space:** Verify that there is enough free disk space available.

If issues persist, consult the Roo Code documentation or community support channels for further assistance.

## Understanding Memory Bank Files

When you initialize the Memory Bank, you create a `memory-bank/` folder with three key files to start: `productContext.md`, `activeContext.md`, and `progress.md`. Here's a breakdown of each file's purpose:

### `memory-bank/productContext.md`

**Purpose:** Document the **stable, long-term project context.** Captures foundational knowledge consistent throughout the project.

**Content Examples:**
* **Project Vision/Goals:** Overall project aims and objectives.
* **Target Audience:** Intended user base.
* **Key Technologies:** Primary technologies, frameworks, libraries.
* **High-Level Architecture:** Project's architectural design, main components.
* **Domain-Specific Knowledge:** Relevant background info, domain expertise.

**Update Frequency:** Infrequent. Update on significant shifts in project direction, target audience, or core tech stack.

**Think of it as:** Project's "North Star" document. Provides enduring context.

### `memory-bank/activeContext.md`

**Purpose:** Tracks **dynamic, short-term context** of your *current work & next steps*. Daily scratchpad for Roo Code.

**Content Examples:**
* **Current Task/Feature:** Specific feature, bug fix, or task you're actively working on *now*.
* **Immediate Next Steps:** Very next actions to progress on current task.
* **Open Questions/Decisions:** Pending questions, decisions, roadblocks.
* **Technical Details (Short-Term):** Temporary notes, code snippets, commands for current task.
* **Session-Specific Notes:** Anything for Roo to remember *this session*.

**Update Frequency:** Very frequent. Update at session start/end, and when focus shifts.

**Think of it as:** Your "Daily Task Log" for Roo. Keeps Roo focused on immediate priorities.

### `memory-bank/progress.md`

**Purpose:** Provides **high-level project progress & status overview.** Tracks accomplishments and remaining tasks.

**Content Examples:**
* **Work Done:** Completed features, tasks, milestones (bullet points, short descriptions).
* **To Do:** Concise list of remaining tasks/features.
* **Current Status Summary:** Project's overall stage (e.g., "Alpha", "Beta", "Ready for release").
* **Completion Metrics (Optional):** Simple metrics to track progress (e.g., "% core features complete").
* **Milestones/Deadlines (Optional):** Key project milestones, target deadlines.

**Update Frequency:** Regular. Update weekly or after significant progress.

**Think of it as:** Project's "Executive Summary". Quick snapshot of project status.

239 |     *   Continue working seamlessly in any mode.
240 | 
241 | **Revised Guidance on "Update Memory Bank" Command:**
242 | 
243 | The `update memory bank` command is now even more of a **best practice for session management and long-term project context preservation**, rather than being strictly *required* for every single break due to Roo Code's chat history persistence.
244 | 
245 | **Think of it as:**
246 | *   **`[MEMORY BANK: ACTIVE]` prefix in Code Mode:** Ensures Roo operates within the *documented, reliable* project context during coding tasks, especially important for handling potential internal memory resets.
247 | *   **`update memory bank` command:** Your "save project knowledge" command. Use it to:
248 |     *   Ensure the Memory Bank is up-to-date at the end of work sessions or before breaks.
249 |     *   Prepare for VS Code closure or workspace switching.
250 |     *   Create explicit checkpoints in your project's documented history.
251 | 
252 | **Key Takeaway:**
253 | 
254 | Roo Code's new context features are a welcome enhancement. However, the Memory Bank system remains the cornerstone of persistent, structured project knowledge management for Roo. By using both effectively – leveraging Roo Code's features for in-session convenience and the Memory Bank for long-term reliability and structured documentation – you create a powerful and robust development workflow with Roo. Continue to prioritize maintaining your Memory Bank as your project's long-term memory and use `update memory bank` strategically to ensure its accuracy and completeness across sessions.