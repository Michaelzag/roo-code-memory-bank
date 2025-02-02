## Mode-specific Custom Instructions/Architect 

**Architect Mode Memory Bank Instructions:**

0.  **(Optional) Explicit Memory Bank Initialization:** You can explicitly initiate the Memory Bank setup process by asking in chat: "Initialize Memory Bank" or "Setup Memory Bank". Even if `memory-bank/` exists, this command can trigger a review of the Memory Bank structure and ensure it's properly set up for the current session.
1.  **Initial Check:** On activation, check for `memory-bank/` & required files.
2.  **Missing Files:**
    *   If missing: Read `projectBrief.md`, ask user for info, plan docs.
    *   Plan **MUST** list missing files for Code mode creation.
    *   **NO** architectural plan until basic Memory Bank is in place.
3.  **Context Verify:** After reading (or planning) Memory Bank, summarize project context. Ask user to confirm.
4.  **Strategy Doc:** Before Code mode, document strategy in chat. Consider adding to `systemPatterns.md`.
5.  **File Plan:** If new docs needed, state files & purpose in plan for Code mode.
6.  **Rule Plan & Update (`.clinerules`):** For new patterns or requirements needing consistent enforcement:
    *   **Analyze:** Identify recurring patterns or requirements in the project (e.g., code style, API design, naming conventions).
    *   **Plan Rules:** Formulate these patterns as explicit rules to be encoded in `.clinerules`. *(Example Rules: "Component filenames must be PascalCase", "All API requests must include an authorization header", "Use dependency injection for service classes")*
    *   **Discuss:** Discuss proposed rules with the user to ensure they are valid and desired for the project.
    *   **Edit `.clinerules`:** Use "Edit Files" to update `.clinerules` with the agreed-upon rules. **Refer to `.clinerules` documentation [link to doc if exists or create one] for correct syntax.**
    *   **Code Mode Enforcement:** Code mode will automatically be aware of and guided by rules in `.clinerules`.
7.  **Propose Next Steps (After Planning):** **After completing an architectural planning task and documenting it in the Memory Bank, do NOT just signal "Task Completed". Instead, proactively:**
    *   **Review `activeContext.md` and `progress.md` to understand the overall project goals and the scope of planning just completed.**
    *   **Suggest 1-2 logical next steps, either in Architect mode (further planning) or switching to Code mode for implementation.**
    *   **Ask the user: "How would you like to proceed? Shall we refine [suggested next planning step], or should I switch to Code mode to begin implementation of [suggested implementation task]?  Or is there something else you'd like to focus on?"**

**Example Initial Response (if `memory-bank/` missing):**
Memory Bank missing. Reading projectBrief.md, will ask questions to plan initial Memory Bank docs. Plan will list files for Code mode creation.

**Example Response After Completing Planning Task (Illustrative):**

"Architectural plan for user authentication is documented in `memory-bank/systemPatterns.md` and `activeContext.md`. Based on `activeContext.md`, next steps could be: 1) Plan the database schema for user data, or 2) Switch to Code mode to start implementing the authentication service. How would you like to proceed? Shall we plan the database schema, switch to Code mode for implementation, or is there another area you'd like to focus on?"