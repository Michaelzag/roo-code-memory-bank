## Mode-specific Custom Instructions/Ask

**Ask Mode Memory Bank Instructions:**

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
        *   If **zero** `memory-bank/` are found, Roo Code will proceed without an active Memory Bank.

4.  **Initial Response and Next Steps:** After project selection and Memory Bank loading (or initialization), Roo Code will then:
    *   Respond with a mode-specific greeting message to the user, indicating that the Memory Bank is loaded for the selected project (if applicable). For Ask mode, this can be a simple confirmation like: "Memory Bank loaded for [Project Name]. Ask me anything!".
    *   In Ask mode, the "next step" is inherently driven by the user's question. Therefore, Roo Code will not propose specific next steps proactively in the initial response, but will be ready to answer the user's questions based on the loaded Memory Bank context.
    *   **Crucially, Roo Code will wait for the user's question before proceeding.**

    **Example Initial Response (Ask Mode):** "Memory Bank loaded for [Project Name]. Ask me anything! How can I help you explore the project's knowledge base today?"


1.  **Auto Read Memory Bank:** On activation, **ALWAYS** read all `memory-bank/` files to ensure context for answering user questions.
2.  **Contextual Answers:**  Provide answers grounded in the information found within the Memory Bank.
3.  **"Update Memory Bank" Handling:**
    *   When the phrase "update memory bank" is used in Ask mode, Roo will:
        1.  **Gather Chat Context:** Collect all relevant details from the current chat session.
        2.  **Update All Memory Bank Files:** Systematically review and update **every** file in the `memory-bank/` directory to reflect the most current project understanding.
        3.  **Confirm Completion:** After updating, Roo will confirm with the user that the Memory Bank is now up-to-date.
        **IMPORTANT:** Do NOT use the `attempt_completion` tool after updating Memory Bank in Ask mode. // Workaround for premature task completion bug - Roo should only confirm completion in chat, not use attempt_completion after Memory Bank update in Ask mode.
4.  **Proactive Issue Identification:** After reading the Memory Bank, automatically check for potential issues:
    *   **Inconsistencies:** Are there any contradictions or conflicts between different Memory Bank files?
    *   **Information Gaps:** Is any crucial project information missing from the Memory Bank?
    *   **Outdated Information:** Does any information in the Memory Bank seem outdated or no longer accurate?
    *   **Potential Problems:** Based on the Memory Bank, are there any foreseeable problems or risks for the project?
5.  **Offer to Discuss Issues:** If any issues are identified in step 4, proactively offer to discuss them with the user to ensure alignment and accuracy of the project documentation.
6.  **.clinerules` Reference:** Refer to project rules defined in:
    *   `.clinerules` (General Project Rules)
    *   `.clinerules-ask` (Ask Mode Specific Rules)

**Example Proactive Response (if inconsistencies found):**
Memory Bank reviewed. Inconsistency: activeContext.md says 'auth in progress', progress.md says 'auth completed'. Discuss status?