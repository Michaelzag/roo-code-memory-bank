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

1.  **Create `memory-bank/` folder:** If you haven't already, create a folder named `memory-bank` at the root of your project in your VS Code workspace.
2.  **Create files:** Inside the `memory-bank/` folder, create three new files named exactly: `productContext.md`, `activeContext.md`, and `progress.md`.
3.  **Copy and Paste:** Copy the code block under "Quick Start Template" above. Paste the first section (starting with `## Project Overview` in `productContext.md`, the second section (starting with `## Current Task`) into `activeContext.md`, and the third section (starting with `## Work Done`) into `progress.md`.
4.  **Customize:**  Replace the bracketed placeholders in each file with your project-specific information.

This template provides a basic structure to get you started with documenting your project in the Memory Bank. Remember to update these files regularly as your project evolves.

## Troubleshooting

This section provides solutions to common issues you might encounter while using the Roo Code Memory Bank system.

**Issue:** `[MEMORY BANK: ACTIVE]` prefix not working in Code mode.

**Solution:**
1.  **Verify Custom Instructions:** Double-check that you have correctly pasted all custom instruction modules into the Roo Code "Prompts" settings in VS Code, especially the "Mode-specific Custom Instructions/Code" module. See the [Setting up Roo Code Custom Instructions](#setting-up-roo-code-custom-instructions) section for detailed instructions.
2.  **Setting Save:** Ensure you have saved the VS Code settings after pasting the instructions. Sometimes settings might not apply immediately until saved.
3.  **Mode Confirmation:** Make sure you are indeed in "Code" mode when using the `[MEMORY BANK: ACTIVE]` prefix. The mode is displayed in the Roo Code chat interface.
4.  **Prefix Case & Spacing:**  The prefix is case-sensitive and requires exact spacing: `[MEMORY BANK: ACTIVE]`. Any variations will not be recognized.

**Issue:** Roo Code does not seem to remember project context after VS Code restart.

**Solution:**
1.  **Memory Bank Initialization:** Ensure you have correctly initialized the Memory Bank by following the "Starting a New Project Session" steps in this guide. The `memory-bank/` folder and required files (`productContext.md`, `activeContext.md`, etc.) must be present in your project root.
2.  **Mode Switch (Ask/Architect):** After restarting VS Code, switch to either "Ask" or "Architect" mode *first*. This triggers Roo Code to automatically read and load the Memory Bank context. Switching directly to "Code" mode might bypass this loading process.
3.  **`update memory bank` Command:** As a best practice, use the `update memory bank` command at the end of your sessions to ensure the Memory Bank is explicitly saved and prepared for the next session.
4.  **File Paths:** Double-check that the `memory-bank/` folder is indeed located at the root of your VS Code workspace/project folder. Incorrect file paths will prevent Roo Code from finding the Memory Bank.

**Issue:** `.clinerules` are not being applied.

**Solution:**
1.  **File Location:**  `.clinerules` files (`.clinerules` and mode-specific variants like `.clinerules-code`) must be located at the root of your project, alongside the `memory-bank/` folder.
2.  **Syntax Check:** Verify the syntax of your `.clinerules` file. Incorrectly formatted rules might be ignored. Refer to the `.clinerules` documentation for syntax guidelines.
3.  **Mode Relevance:**  Remember that `.clinerules-code`, `.clinerules-architect`, and `.clinerules-ask` are mode-specific. Rules in `.clinerules-code` will only apply when you are in "Code" mode, etc.
4.  **Roo Code Restart (Rare):** In rare cases, if you've made significant changes to `.clinerules`, restarting Roo Code within VS Code might be necessary to ensure the rules are fully reloaded.
103 | 
104 | **Issue:**  Memory Bank files are not being updated or saved.
105 | 
106 | **Solution:**
107 | 1.  **File Permissions:** Check if you have write permissions to the `memory-bank/` folder and the files within it. File permission issues can prevent Roo Code from saving changes.
108 | 2.  **VS Code Errors:** Look for any error messages in the VS Code console or notification area that might indicate file saving problems.
109 | 3.  **Conflicting Extensions:**  In rare cases, other VS Code extensions might interfere with file saving. Try disabling other extensions temporarily to see if there's a conflict.
110 | 4.  **Disk Space:** Ensure you have sufficient free disk space. Lack of disk space can prevent files from being saved correctly.
111 | 
112 | If you continue to experience issues, please consult the Roo Code documentation or community support channels for further assistance.
113 | 
114 | ## Understanding Memory Bank Files
115 | 
116 | When you initialize the Memory Bank, you create a `memory-bank/` folder with three key files to start: `productContext.md`, `activeContext.md`, and `progress.md`.  Here's a breakdown of each file's purpose:
117 | 
118 | ### `memory-bank/productContext.md`
119 | 
120 | **Purpose:** Document the **stable, long-term project context.** Captures foundational knowledge consistent throughout the project.
121 | 
122 | **Content Examples:**
123 | *   **Project Vision/Goals:** Overall project aims and objectives.
124 | *   **Target Audience:** Intended user base.
125 | *   **Key Technologies:** Primary technologies, frameworks, libraries.
126 | *   **High-Level Architecture:** Project's architectural design, main components.
127 | *   **Domain-Specific Knowledge:** Relevant background info, domain expertise.
128 | 
129 | **Update Frequency:** Infrequent. Update on significant shifts in project direction, target audience, or core tech stack.
130 | 
131 | **Think of it as:** Project's "North Star" document. Provides enduring context.
132 | 
133 | ### `memory-bank/activeContext.md`
134 | 
135 | **Purpose:** Tracks **dynamic, short-term context** of your *current work & next steps*. Daily scratchpad for Roo Code.
136 | 
137 | **Content Examples:**
138 | *   **Current Task/Feature:** Specific feature, bug fix, or task you're actively working on *now*.
139 | *   **Immediate Next Steps:** Very next actions to progress on current task.
140 | *   **Open Questions/Decisions:** Pending questions, decisions, roadblocks.
141 | *   **Technical Details (Short-Term):** Temporary notes, code snippets, commands for current task.
142 | *   **Session-Specific Notes:** Anything for Roo to remember *this session*.
143 | 
144 | **Update Frequency:** Very frequent. Update at session start/end, and when focus shifts.
145 | 
146 | **Think of it as:** Your "Daily Task Log" for Roo. Keeps Roo focused on immediate priorities.
147 | 
148 | ### `memory-bank/progress.md`
149 | 
150 | **Purpose:** Provides **high-level project progress & status overview.** Tracks accomplishments and remaining tasks.
151 | 
152 | **Content Examples:**
153 | *   **Work Done:** Completed features, tasks, milestones (bullet points, short descriptions).
154 | *   **To Do:** Concise list of remaining tasks/features.
155 | *   **Current Status Summary:** Project's overall stage (e.g., "Alpha", "Beta", "Ready for release").
156 | *   **Completion Metrics (Optional):** Simple metrics to track progress (e.g., "% core features complete").
157 | *   **Milestones/Deadlines (Optional):** Key project milestones, target deadlines.
158 | 
159 | **Update Frequency:** Regular. Update weekly or after significant progress.
160 | 
161 | **Think of it as:** Project's "Executive Summary". Quick snapshot of project status.
162 | 
163 | By consistently updating these three core Memory Bank files, you provide Roo Code with a comprehensive and evolving understanding of your project, enabling more effective collaboration and context-aware assistance throughout the development process.
164 | 
165 | ## Understanding Roo Code's Context Features
166 | 
167 | Recent updates to Roo Code include built-in features that help preserve context *within a VS Code workspace session*. These features are valuable and enhance your workflow:
168 | *   **Chat History Persistence:** Roo Code now remembers your chat history within a VS Code workspace. If you close and reopen VS Code (within the same project folder/workspace), your chat conversations will be restored.
169 | *   **Workspace Awareness:** Roo Code is aware of your VS Code workspace, including open files and project structure. This allows it to understand the codebase better and provide more context-aware responses within a session.
170 | 
171 | **Key Point:** While these features improve *in-session* context, they **do not replace** the need for the Memory Bank. Roo still experiences periodic internal memory resets. The Memory Bank remains crucial for:
172 | *   **Persistence Across Roo's Memory Resets:** Roo's internal memory can reset even within an active VS Code session. The Memory Bank ensures context survives these resets.
173 | *   **Long-Term Project Knowledge:** The Memory Bank provides a structured, documented repository for project understanding, architectural decisions, technical context, and progress tracking – beyond just chat history.
174 | *   **Explicit Mode-Based Workflow:** The Memory Bank system defines specific workflows for Architect, Code, and Ask modes to actively manage and utilize project knowledge.
175 | *   **`.clinerules` for Project Rules:** The Memory Bank system includes `.clinerules` for defining and enforcing project-specific rules, which Roo Code's built-in features do not address.
176 | 
177 | **The Memory Bank and Roo Code Features: Working Together**
178 | 
179 | Think of it this way:
180 | *   **Roo Code's built-in features:** Provide *short-term* and *workspace-level* context. They enhance the immediate conversational experience and help Roo understand the codebase *during a VS Code session*.
181 | *   **Memory Bank System:** Provides *long-term* and *structured* project context that persists across Roo's memory resets and VS Code sessions. It's your external, reliable "brain" for Roo.
182 | 
183 | ## Setting up Roo Code Custom Instructions
184 | 
185 | To enable the Memory Bank system, you need to configure Roo Code with custom instructions. These instructions are pasted into the Roo Code "Prompts" settings within VS Code.
186 | 
187 | 1.  **Open Roo Code Settings:** Access your VS Code settings and find the Roo Code extension settings. Look for sections related to "Prompts" or "Custom Instructions."
188 | 2.  **Instruction Modules:** Paste the following instruction modules into the corresponding sections in Roo Code settings ("Prompts" or "Custom Instructions"):
189 |     *   **Custom Instructions for All Modes**
190 |     *   **Role Definition/Code**
191 |     *   **Role Definition/Architect**
192 |     *   **Role Definition/Ask**
193 |     *   **Mode-specific Custom Instructions/Architect**
194 |     *   **Mode-specific Custom Instructions/Ask**
195 | 3.  **Save Settings.**
196 | 
197 | ## Using the Roo Code Memory Bank System: Workflow Guide
198 | 
199 | This section outlines the workflow for using the Memory Bank in your daily development with Roo Code.
200 | 
201 | ### Starting a New Project Session (Memory Bank Initialization)
202 | 
203 | 1.  **Create a Project Folder:** Start with a new or existing project folder in VS Code.
204 | 2.  **Initial Interaction (Architect Mode):** Switch Roo Code to **Architect mode**.
205 | 3.  **First Message (Optional `projectBrief.md`):** In Architect mode, Roo will automatically check for `projectBrief.md` in your project root. If `projectBrief.md` is present, Roo will read it to understand your project. If not, Roo will proceed with the Memory Bank initialization process.
206 | 4.  **Missing Memory Bank Detection:** Roo will recognize that the `memory-bank/` folder and required files are missing (on the first session).
207 | 5.  **Roo's Plan:** Roo will respond with a plan to create the initial Memory Bank documentation. It will outline the necessary files (`productContext.md`, `activeContext.md`, etc.) that need to be created in Code mode.
208 | 
209 | **Example Roo's Plan:**
210 | 
211 | "Memory Bank setup required. I will create these files for you in Code mode:
212 | 
213 | 1.  `memory-bank/productContext.md`: File for project overview and long-term context.
214 | 2.  `memory-bank/activeContext.md`: File for current tasks and next steps.
215 | 3.  `memory-bank/progress.md`: File for tracking project progress.
216 | 
217 | Switch to Code mode to create these files using the 'write_to_file' tool."
218 | 
219 | 6.  **Switch to Code Mode:** Follow Roo's plan and switch to **Code mode**.
220 | 7.  **Create Memory Bank Files (Code Mode):** In Code mode, use the `write_to_file` tool to create the `memory-bank/` directory and the required Markdown files as outlined in Roo's Architect mode plan. Place the `memory-bank/` directory at the **root of your VS Code workspace**.
221 | 8.  **Initial Documentation (Code Mode):** Begin populating the Memory Bank files with initial project information based on your `projectBrief.md` and your project understanding. Focus on `productContext.md` and `activeContext.md` to start.
222 | 9.  **Memory Bank Active:** Once the basic `memory-bank/` structure is created, Roo is ready to use the Memory Bank. You can now start working in Architect or Code mode, and Roo will utilize the Memory Bank for context.
223 | 
224 | ### Working in a Session
225 | 
226 | 1.  **Mode Switching:** Use Architect, Code, and Ask modes as needed for planning, coding, and asking questions.
227 | 2.  **Code Mode & `[MEMORY BANK: ACTIVE]` (Crucial for Memory Reset Persistence):** In Code mode, remember to **always** prefix tool use commands (like `write_to_file`, `apply_diff`, etc.) with `[MEMORY BANK: ACTIVE]`. This prefix is **crucial** to ensure Roo operates within the documented Memory Bank context, especially after internal memory resets. Example: `[MEMORY BANK: ACTIVE] Edit Files: memory-bank/activeContext.md`
228 | 3.  **Documentation Updates:** Actively update the Memory Bank files (`activeContext.md`, `progress.md`, etc.) as you make progress, decisions, and learn new things about the project. Update documentation **before** starting a new code task or immediately after completing a logical chunk of work. Use Roo Code's "Edit Files" tool for efficient updates.
229 | 4.  **`.clinerules` Management (Architect & Code):** Use Architect mode to plan and update `.clinerules` for project-wide rules. Code mode can also update `.clinerules` when new patterns emerge during coding. Architect mode can directly edit the `.clinerules` file using the "Edit Files" tool.
230 | 
231 | ### Ending and Resuming a Session
232 | 
233 | 1.  **Ending a Session - "Update Memory Bank" Command:** When you want to end a session and ensure Roo can resume correctly later, type: `update memory bank` in the chat. This is especially recommended at the end of a workday, before closing VS Code, or switching projects.
234 | 2.  **Memory Bank Update Process:** Roo will document the current project state in the Memory Bank files, clarify next steps in `activeContext.md`, and prepare for its memory reset.
235 | 3.  **Resuming a Session (After Memory Reset/VS Code Restart):**
236 |     *   Start Roo Code in your project.
237 |     *   When you switch to **Ask** or **Architect** mode, Roo will **automatically read** all files in the `memory-bank/` directory, regaining project context.
238 |     *   Roo will use `activeContext.md` as its primary source to understand where you left off and what the next steps are.
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