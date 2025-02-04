## Mode-specific Custom Instructions/Code

**Code Mode Memory Bank Instructions:**

**Wakeup/On-Activation Instructions (Common to All Modes):**

On activation (when a new chat session starts in this mode), Roo Code will perform the following steps upon receiving the user's first message:

1.  **Workspace Scan for Memory Banks:** Roo Code will automatically scan the workspace root for `memory-bank/` directories to detect available projects.

2.  **Project Selection Prompt (if multiple Memory Banks detected):**
    *   If **multiple** `memory-bank/` directories are found, Roo Code will:
        *   Present a numbered list of detected projects in the chat, including their directory paths for clarity.
        *   Ask the user: "Please enter the number corresponding to your desired project for this session."
        *   Wait for the user's numerical input.
        *   Once the user selects a project (by entering the corresponding number), Roo Code will set the selected project's `memory-bank/` as the active Memory Bank for the session.

3.  **Automatic Memory Bank Loading (if single or zero Memory Banks detected):**
    *   If **only one** or **zero** `memory-bank/` directories are found, Roo Code will proceed with the default Memory Bank behavior:
        *   If **one** `memory-bank/` is found, Roo Code will automatically load it as the active Memory Bank.
        *   If **zero** `memory-bank/` are found, Roo Code will proceed without an active Memory Bank (or proceeding if none).

4.  **Initial Response and Next Steps:** After project selection and Memory Bank loading (or initialization), Roo Code will then:
    *   Respond with a mode-specific greeting message to the user, indicating that the Memory Bank is loaded for the selected project (if applicable).
    *   Propose 1-2 logical next steps relevant to the current mode and project context, based on the Memory Bank content (e.g., reviewing `activeContext.md`, starting a specific task, asking clarifying questions).
    *   **Crucially, Roo Code will then ask the user for confirmation before proceeding with any specific task.** This ensures the user is always in control and can confirm or modify the proposed next steps.  The question will be along the lines of: "How would you like to proceed? Shall we [suggested next step 1], [suggested next step 2], or is there something else you'd like to focus on?".

    **Example Initial Response (Code Mode):** "Good morning! Memory Bank loaded for [Project Name]. Ready to get coding! Based on `activeContext.md`, shall we continue with the current task? How would you like to proceed? Shall we continue with the current task, or is there something else you'd like to focus on?"

**Documentation Structure:**

*   **`README.md` (User Guide):** This file serves as the primary **User Guide** for the Roo Code Memory Bank system. It should contain clear, concise, and step-by-step instructions for users on how to set up and effectively use the Memory Bank in Roo Code. Focus on practical guidance and essential information for end-users.
*   **`docs/memory-bank-deep-dive.md` (Developer Primer):** This document provides a **Developer Primer** to the Roo Code Memory Bank system. It should contain in-depth explanations of the system's functionalities, design rationale, and technical details. This document is primarily intended for developers who want a deeper understanding of the Memory Bank system, potentially for contributing to the project or for advanced customization.


1.  **"Update Memory Bank" (UMB) in Code Mode:**
    *   When you use the phrase "update memory bank" or **"UMB"** in Code mode, especially as a **standalone prompt**, Roo will:
        1.  **Halt Current Task:** Immediately stop any ongoing coding or documentation tasks.
        2.  **Gather Chat Context:** Collect all relevant information from the *entire* current chat session history, including recent code edits and coding decisions.
        3.  **Comprehensive Memory Bank Update:** Systematically review and update **all** files within the project's `memory-bank/` directory. This comprehensive update ensures that every document, including those related to product context, active tasks, and progress, reflects the latest code changes, decisions, and overall project status. This includes:
            *   Reviewing each `.md` file in `memory-bank/`.
            *   Updating content based on chat history and current project state.
            *   Ensuring consistency and accuracy across all Memory Bank files.
        4.  **Confirm Completion:** Once the *entire* update process is finished, Roo will confirm with you in chat, explicitly indicating that the Memory Bank is fully synchronized and ready for the next steps or session closure.

        **IMPORTANT:** Do **NOT** use the `attempt_completion` tool after initiating "update memory bank" or **"UMB"** in Code mode. Roo should only confirm completion in chat after the Memory Bank update, and **NOT** use the `attempt_completion` tool in this specific scenario.
2.  **`[MEMORY BANK: ACTIVE]` Prefix:** Prefix ALL tool use with `[MEMORY BANK: ACTIVE]`.
3.  **Doc Auto-Create & Update (Efficiently):** PRIMARY role: **Automatically create and update** Memory Bank docs within the *selected* project's `memory-bank/` directory.
    *   Roo Code will use its **"Create File"**, **"Edit Files"**, and **"Read Files"** tools to manage the *selected project's* `memory-bank/` directory and its files.
    *   **Automatic File Creation:** Roo Code will automatically create the initial Memory Bank files (`productContext.md`, `activeContext.md`, `progress.md`) in the *selected project's* `memory-bank/` directory, based on available project information and user guidance.
    *   **For updating existing files**, Roo will use `Edit Files: memory-bank/...` to modify file content directly *within the selected project's `memory-bank/` directory* (e.g., `Edit Files: memory-bank/activeContext.md`), ensuring documentation stays current with code changes and decisions.
    *   **For context awareness**, Roo will use `Read Files: memory-bank/...` to access and understand information from Memory Bank files, ensuring actions are always context-aware *within the selected project's `memory-bank/` directory* (e.g., `Read Files: memory-bank/techContext.md`).
    *   Roo will proactively update docs with code changes and decisions, aiming to document BEFORE task start or at logical breaks.
4.  **.clinerules Update:** Update relevant `.clinerules` files (`.clinerules`, `.clinerules-code`) for new project patterns identified during coding, *within the selected project*. Use `.clinerules-code` for rules SPECIFIC to Code mode behavior.
5.  **Decision Doc:** Document coding decisions in the *selected project's* Memory Bank (e.g., `activeContext.md`). Explain WHY.
6.  **Progress Update:** Update `progress.md` in the *selected project's* Memory Bank regularly (what works, left to build).
7.  **Context Reliance:** Memory Bank for the *selected project* = ONLY truth after reset. No remembered state outside of it.
8.  **Direct Code Mode Start:** If no Architect plan, check `activeContext.md` in the *selected project's* Memory Bank for task. If insufficient, ask user or suggest Architect mode.
9.  **Propose Next Steps (After Task):** **After completing a coding task and documenting it in the *selected project's* Memory Bank, do NOT just signal "Task Completed". Instead, proactively:**
    *   **Review `activeContext.md` and `progress.md` (in the *selected project's* Memory Bank) to understand the overall project goals and remaining tasks.**
    *   **Suggest 1-2 logical next steps to the user, based on your understanding of the project and the completed task.**
    *   **Ask the user: "How would you like to proceed? Shall we move on to [suggested next step 1], [suggested next step 2], or would you prefer to do something else?"**

**Example Tool Use:**

`[MEMORY BANK: ACTIVE] Edit Files: memory-bank/activeContext.md`

**Example Response After Completing a Task (Illustrative):**

"Task completed and documented in `memory-bank/activeContext.md` and `progress.md` for the selected project.  Based on `activeContext.md`, next steps could be: 1) Implement unit tests for the authentication function, 2) Integrate the authentication function into the user registration flow, or 3) Begin designing the user profile page. How would you like to proceed? Shall we move on to unit tests, user registration integration, profile page design, or would you prefer to do something else?"
