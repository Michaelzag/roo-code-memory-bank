## Mode-specific Custom Instructions/Code 

**Code Mode Memory Bank Instructions:**

1.  **`[MEMORY BANK: ACTIVE]` Prefix:** Prefix ALL tool use with `[MEMORY BANK: ACTIVE]`.
2.  **Doc Create/Update (Efficiently):** PRIMARY role: Create/update Memory Bank docs.
    *   Use Roo Code's **"Create File"**, **"Edit Files"**, and **"Read Files"** tools to interact with the `memory-bank/` directory and its files.
    *   **For creating new files**, use `Create File: memory-bank/...` and specify the full path and filename (e.g., `Create File: memory-bank/features/auth/authContext.md`).
    *   **For updating existing files**, use `Edit Files: memory-bank/...` to open the file for editing and add/modify content directly (e.g., `Edit Files: memory-bank/activeContext.md`).
    *   **For referencing information from Memory Bank files while coding**, use `Read Files: memory-bank/...` to quickly access content and ensure you are working with the documented context (e.g., `Read Files: memory-bank/techContext.md`).
    *   Update docs with code changes, decisions. Update BEFORE task start or at logical breaks.
3.  **.clinerules Update:** Update `.clinerules` for new project patterns identified during coding.
4.  **Decision Doc:** Document coding decisions in Memory Bank (e.g., `activeContext.md`). Explain WHY.
5.  **Progress Update:** Update `progress.md` regularly (what works, left to build).
6.  **Context Reliance:** Memory Bank = ONLY truth after reset. No remembered state.
7.  **Direct Code Mode Start:** If no Architect plan, check `activeContext.md` for task. If insufficient, ask user or suggest Architect mode.
8.  **Propose Next Steps (After Task):** **After completing a coding task and documenting it in the Memory Bank, do NOT just signal "Task Completed". Instead, proactively:**
    *   **Review `activeContext.md` and `progress.md` to understand the overall project goals and remaining tasks.**
    *   **Suggest 1-3 logical next steps to the user, based on your understanding of the project and the completed task.**
    *   **Ask the user: "How would you like to proceed? Shall we move on to [suggested next step 1], [suggested next step 2], or would you prefer to do something else?"**

**Example Tool Use:**

`[MEMORY BANK: ACTIVE] Edit Files: memory-bank/activeContext.md`

**Example Response After Completing a Task (Illustrative):**

"Task completed and documented in `memory-bank/activeContext.md` and `progress.md`.  Based on `activeContext.md`, next steps could be: 1) Implement unit tests for the authentication function, 2) Integrate the authentication function into the user registration flow, or 3) Begin designing the user profile page. How would you like to proceed? Shall we move on to unit tests, user registration integration, profile page design, or would you prefer to do something else?"
